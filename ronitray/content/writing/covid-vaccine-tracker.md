+++
title= "Let's Build: COVID-19 Vaccination Tracker (for India)"
date= 2021-05-05
description= "I grew sick of manually searching for vaccine slots, so I built my own tracker."
[extra]
listed=true
+++

It's that time of the year. Birds are chirping, people are dying, your government has chosen to ignore a massive supply-side vaccine shortage, allowed manufacturers to set their own prices and opened up vaccine bookings for all citizens, thus shifting the onus to get vaccinated entirely upon you... perfectly normal and rather wonderful.

The number of vaccines available in my city is extremely low at the moment. Hospitals declare stocks on the [government portal](https://cowin.gov.in/) as they please, and then it is pretty much a game of fastest finger first to grab a booking. There are no notifications, and it takes a while to go from the login page to a page where you can actually make a booking. If traffic is high, this takes longer since the one-time password takes forever to arrive.

At this rate, it would take forever to get vaccinated, and the process of checking for slots a billion times a day was driving me crazy. To their credit, however, the government provides a [very simple API](https://apisetu.gov.in/public/api/cowin) for checking vaccine availability. With  a little code smarts, we should be able to knock up a simple tracker to automate the lookup process and give us an alert when a slot is available near us.

### What We Have

The Co-Win API exposes the following data through REST web services:

1. [A list of Indian states,](https://apisetu.gov.in/public/api/cowin#/Metadata%20APIs/states) from which we can grab the state ID we want to query.
2. [A list of districts in a particular state,](https://apisetu.gov.in/public/api/cowin#/Metadata%20APIs/districts) from which we can grab the district ID we want to query. 
3. [A list of vaccination sessions in the next 7 days in a particular district,](https://apisetu.gov.in/public/api/cowin#/Appointment%20Availability%20APIs/calendarByDistrict) which is what we need and are going to use.

It is worth noting that there is a web service to find vaccination sessions in the next week for a particular pincode, but the shortage is so bad that it's likely there won't be a vaccination center in your pincode for quite a while. You're probably better off driving to a center near you, which is what the above will help us identify.

### What We Are Going to Do

We will:

1. **Query the API at a regular interval**, say every half an hour, to find all slots in the next week.
2. We filter the results to find slots that are **available**, and **open to our age group**
3. If such an open slot is found, we must **issue an alert** somehow. 

My demo code will be in Python, but if you have the logic down, it is really easy to adapt to whatever language or framework you are comfortable in. I am a CLI person myself, but you can also extend this into a simple GUI for convenience. Some great projects in this vein are:

1. [VaccinateMe](https://www.vaccinateme.in/covid/?type=district)
2. [GetJab](https://getjab.in/)
3. [FindMySlots](https://findmyslots.com/)

Hell, I might do so myself... my GitHub is awfully barren. 

A small note: the APIs only allow you to find open slots. Any action to actually reserve a vaccination booking for yourself is something you must do manually, as the web services to do so are protected and for authorized (not public) use only.

Less talk, more code.

### Step 1: Inputs
To query for slots, we need two input parameters:

1. The DISTRICT ID in which we are looking for slots.
2. The DATE from which we will be looking for slots.

We first set up a BASE_DOMAIN for the service URL.

```python
BASE_DOMAIN = 'https://cdn-api.co-vin.in/api/v2/appointment/sessions/public/calendarByDistrict'
```

Following which, we define the district ID. Remember, there is a web service provided to find the district ID for your district.

```python
DISTRICT_ID = '500' 
//pick any from the list
```

The date is needed in DD-MM-YYYY format as per the API specification. I'm more of an [ISO-8601](https://kirby.kevinson.org/blog/iso-8601-the-better-date-format/) man myself, but we can't all be perfect. The standard way to deal with date-time formats is the [datetime](https://docs.python.org/3/library/datetime.html) module.

```python
import datetime
.
.
.
date = datetime.datetime.now().strftime("%d-%m-%Y") 
//the format expected by the API is DD-MM-YYYY
```

### Step 2: GET request
We must now form the URL and send an [HTTP GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) request to it to fetch the available slots. Python handles HTTP stuff with the [requests](https://pypi.org/project/requests/) library.

```python
import requests
.
.
.
url = BASE_DOMAIN + '?' + 'district_id=' + DISTRICT_ID + '&' + 'date=' + today_date

service_response = requests.get(url)
```

What this does is pretty simple, it sends a GET request to the URL, and whatever response received is stored in the service_response variable.

When dealing with HTTP requests, it's important to account for errors and exceptions. A request that is successfully handled by the server is marked by an HTTP code of **200** in the response. Any code other than that signifies a different type of error (404 is Not Found (maybe the URL was malformed or has changed), 403 is Forbidden (access denied for some reason), 405 is method not allowed (GET expected but POST sent or vice versa) and so on).

Further, there could be other errors in the pipeline. Say your internet connection isn't working- your request will not really go anywhere and your program will be looking for a response that won't arrive. This kind of unexpected behavior is called an Exception and can be handled in python.

The sys module has a number of useful methods to deal with interpreter variables like exceptions. We can handle all exceptions in one fell swoop and also account for HTTP errors like this:

```python
import sys
.
.
.
try:
    service_response = requests.get(url)              
        if service_response.status_code == 200:
            //handle successful response
        else : 
           print("ERROR: " + str(service_response.status_code) + ":" + service_response.text)
except:
    print("Unexpected error:", sys.exc_info()[0] + " at " + str(sys.exc_info()[2]))                 
```

### Step 3: Handling Response JSON
The sample response JSON for the calendarByDistrict web service is:

```json
{
  "centers": [
    {
      "center_id": 1234,
      "name": "District General Hostpital",
      "name_l": "",
      "address": "45 M G Road",
      "address_l": "",
      "state_name": "Maharashtra",
      "state_name_l": "",
      "district_name": "Satara",
      "district_name_l": "",
      "block_name": "Jaoli",
      "block_name_l": "",
      "pincode": "413608",
      "lat": 28.7,
      "long": 77.1,
      "from": "09:00:00",
      "to": "18:00:00",
      "fee_type": "Free",
      "vaccine_fees": [
        {
          "vaccine": "COVISHIELD",
          "fee": "250"
        }
      ],
      "sessions": [
        {
          "session_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
          "date": "31-05-2021",
          "available_capacity": 50,
          "min_age_limit": 18,
          "vaccine": "COVISHIELD",
          "slots": [
            "FORENOON",
            "AFTERNOON"
          ]
        }
      ]
    }
  ]
}
```

The top-level object is an array of `center` objects. Each center object has specific details like the name, address, type of vaccine, cost etc. The attribute we need is called `sessions`, and it is an array of objects, each describing the vaccine sessions a center has open in the next week. Each session has the age limit and slots specified.

We get the response JSON and filter it as follows:

```python
AGE_BRACKET = 45 //for ages 45-60
found_flag = False //set to true if valid sessions are found
.
.
.
json_body = service_response.json()            
for center in json_body["centers"]:
    sessions = center["sessions"]
    for session in sessions:
        if (session["min_age_limit"] == AGE_BRACKET and session["available_capacity"] > 0):
            found_flag = True
            print("FOUND!!! UwU \n")
            print("on"+ session["date"] + ", Available: " + str(session["available_capacity"]) + "\n")
            print(center["name"] + '\n' + center["address"] + '\n' + session["vaccine"])
            print('\n')
```

### Step 4: Alert If Valid Slots are Found
As mentioned earlier, if a slot is found, the system needs to issue an alert so we can go and grab a booking as soon as possible. This can be through an email, a telegram message, changing the color of the RGB lights in your room... the sky is the limit. I'll just be playing  a beep noise thrice for demonstration purposes.
The simplest way to do this is with the [playsound](https://pypi.org/project/playsound/) module. This minimalist module has no dependencies and does only one thing- it plays a sound. You can grab a royalty free track of anything online, like a [beep](https://www.soundjay.com/beep-sounds-1.html), and go ham.

```python
from playsound import playsound
.
.
.
if found_flag == True:
	//beep thrice!
    playsound('beep.mp3')
    playsound('beep.mp3')
    playsound('beep.mp3')
else:
    print("not found :( ")
```

### Step 5: Running this job at regular intervals
Now that we have a routine to check for available slots, all that is left is automating the process so it runs at a defined interval. Python has a library for literally everything, so it's no surprise that the [schedule](https://schedule.readthedocs.io/en/stable/) library is here to save the day.

The first thing you do is to put the entire logic (generating the URL to sending the request, handling the response, and the alert) in a method of its own. This method will be the job that our scheduler runs.

Once this method, say `search()` is ready, we can schedule it to run at our desired frequency as follows:

```python
schedule.every(30).minutes.do(search)

while True:
    schedule.run_pending()
    time.sleep(1)
```

Remember to be gentle... if you query this too often, the CDN will likely rate-limit you or block you from accessing the API for a while (returning 403 for every request). Aaaand, we're all wrapped up. You can find the complete program on my Github [here](https://github.com/RonitRay/vaxscene-cli).

### A Disclaimer Before We Go
The idea behind this program is to use publicly available APIs and data provided by the Indian government to expedite the slot booking process and reduce the friction overall. I don't encourage or condone any untoward behavior including abuse of the public APIs, using bots beyond the alert process (eg. for automating bookings and so on) or any other illegal or immoral activity. If any objections are brought forward or if someone brings to my notice that it is wrong to use such a program, I will take the post and the git repository down. I encourage everyone undertaking something like this project to deal in good faith only and ensure we, as a population, do everything in our capacity to get vaccinated as soon as possible and push back against the pandemic.
