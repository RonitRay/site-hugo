+++
title= "Don't FLoC with my Heart"
date= 2021-04-15
description= "Google's old wine in a new bottle form of tracking does not interest me. Quite the opposite."
[extra]
listed=true
+++

A couple of weeks ago, Google launched an initiative called [Federated Learning of Cohorts (FLoC for short)](https://blog.google/products/chrome/privacy-sustainability-and-the-importance-of-and/) in their Chrome browser. The idea (or the marketing copy, anyway) is that FLoC will allow Google to serve you targeted ads without explicitly releasing identifying data or using third-party cookies. Every website you visit will be used by Google's browser to train their classifiers and put you in buckets called cohorts, and members of each cohort can then be targeted based on their shared interests. Individual users will be "lost in the crowd" and only targeted based on the group they belong to rather than who they are exactly (birds of a feather...FLoC together, if you will). A user is assigned a cohort ID, and any site that requests it is only sent the ID instead of granular data. Google claim that this will allow them to continue serving ads without infringing upon user privacy. 

I think it isn't a controversial opinion to say that this is likely preferable over third party cookies, which have been a plague for longer than anyone would like. However, as stated in [this EFF article](https://www.eff.org/deeplinks/2021/03/googles-floc-terrible-idea), it isn't a binary choice. You don't *have* to choose between "bad" other people tracking and "good" Google tracking. To say that FLoC completely eliminates any scope for malicious surveillance is also incorrect, as displayed theoretically [here](https://github.com/WICG/floc/issues/100), not two weeks after the proposal has come up. Keeping track of a particular user's changing FLoC ID is a fairly trivial server-side operation, and even without other factors, makes for good fingerprinting. 

> [johnwilander's comment:](https://github.com/WICG/floc/issues/100#issuecomment-819248942)

> *To take this to the crowd metaphor: Before the pandemic and some time back, I attended a Mew concert, a Ghost concert, Disney on Ice, and a Def Leppard concert. At each of those events I was part of a large crowd. But I bet you I was the only one to attend all four.*

Of course, there is a host of [other factors](https://pixelprivacy.com/resources/browser-fingerprinting/#Test_Your_Browsers_Fingerprinting) exposed by your browser that are already used for fingerprinting, meaning FLoC will likely help improve those efforts rather than hinder them. Google attracts some of the best and brightest minds around the world, and as far as "solving" research problems go, they are not a bad horse to bet on. That said, any solution they come up with will be self-serving; looking to preserve, if not boost their bottom line. There cannot be a shred of doubt that Google is an advertising company. Pushing out third-party cookies is good- of course, they are probably the latest to the party considering Firefox and Safari have been looking to do this for a good couple of years now. However, shoehorning in a proprietary tracking solution instead is a harsh reminder that their interests remain in serving targeted manipulation and making money off users rather than being the protectors and liberators that they are positioning themselves to be. 

With Chrome's market share being what it is, it is not hard to imagine these two moves in tandem (tracking cookies OUT, FLoC IN) leading to Google further consolidating a monopoly in the online advertising market. Again, the question should not be "well, why not let Google serve me targeted ads based on purportedly less invasive tactics, instead of letting Google AND a bunch of other shady businesses serve me targeted ads based on more harmful data collection?" For us to have a realistic hope of a free and democratic internet, the question NEEDS to be "Why do we need to be tracked in whatever we do to be able to use the internet?"

Targeting is by nature profiling. As Big Tech enters arrangements with governments across the world and their business dealings grow murkier and less transparent, there is no telling what they will use the data they collect on you for. The same EFF article I quoted early in this post states:

> *The power to target is the power to discriminate. By definition, targeted ads allow advertisers to reach some kinds of people while excluding others. A targeting system may be used to decide who gets to see job postings or loan offers just as easily as it is to advertise shoes.*

Cathy O'Neil's book ["Weapons of Math Destruction: How Big Data Increases Inequality and Threatens Democracy"](https://en.wikipedia.org/wiki/Weapons_of_Math_Destruction) is a great read and illuminates how the systems that collect seemingly innocuous data about our lives are weaponized against us.

Personally, I feel no inclination to support Google in their noble conquest to save their bottom line, so I will not be using FLoC in any way, shape, or form as long as I can resist it. Here's how you can too.

### Stop Using Chrome

I honestly don't see the appeal that Chrome holds as a general purpose browser. Sure, it's fast enough, but so is every modern browser. [It's the websites that are slow](https://blog.codinghorror.com/an-exercise-program-for-the-fat-web/), and using content blockers will help address that problem no matter what browser you use. Firefox is an awesome browser, and has been since it grew out of the ashes of Netscape. Despite some of their more glaring managerial missteps of late, the browser remains pretty clean, pretty fast, and full of features. 

Firefox ships with ["Enhanced Tracking Protection"](https://support.mozilla.org/en-US/kb/enhanced-tracking-protection-firefox-desktop), that while not sharp enough, does offer a modicum of protection against malicious actors online. 

Most, if not all, Chrome WebExtensions have Firefox equivalents as well. In fact, some of the best Firefox extensions aren't offered by Chrome. [Multi-Account Containers](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/), [Temporary Containers](https://addons.mozilla.org/en-US/firefox/addon/temporary-containers/), and [Containerize](https://addons.mozilla.org/en-US/firefox/addon/containerise/) allow you to achieve next-level privacy gains using the principle of isolation. [Sideberry](https://addons.mozilla.org/en-US/firefox/addon/sidebery/) or [Tree-Style Tabs](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/) allow productivity gains for anyone juggling a boatload of tabs. Really, what's not to like?

The two issues I keep hearing about Firefox are as follows:

1. **Google services don't work well**: Okay, that's possible. We've seen news of Google crippling the experience on their services for browsers other than Chrome, and they continue to serve a completely different version of their site to Firefox Android users. 

    Personally (sample size of 1), on my Linux laptop, I've consistently found Firefox to deliver a better experience on Google services. YouTube, for instance, is marginally smoother on Firefox for me. 
 
    Chrom(ium) has just a bit more screen tearing for 60fps videos, and toggling full-screen freezes my system for a couple of seconds on Chromium or any derivative like Brave/Vivaldi, while it works perfectly on Firefox. I'm not trying to deny or belittle anyone's experiences, but perhaps a more tenable approach would be to use the Google browser for Google services only, and/or those sites that offer a markedly inferior experience on another browser.

1. **Chrome DevTools are unparallelled**: Chrome DevTools are great. I'm not a very heavy user (I've only been coding in Angular for a couple of months), so I haven't found many deficiencies in Firefox's DevTools either. That said, it's a matter of preference. And it's fine for you to use Chrome in a development environment if you'd like, but that is still no reason to use it as your primary browser for everything else.

I strongly recommend incorporating Firefox into the bulk of your internet activity. It is a great browser, has a very solid [encrypted sync functionality](https://www.mozilla.org/en-US/firefox/sync/) if you need it, and is also the only browser on Android that supports extensions. It also happens to be probably the last line of defense standing in the way of Google enjoying a controlling position for web standards forever.

If you really hate Firefox or it doesn't agree with your system, consider using a Chrome fork like [Brave](https://brave.com/). Brave blocks ads and trackers by default, is [fully open-source](https://github.com/brave) under MPL2.0, and has even attempted to implement an alternate monetization scheme([1](https://basicattentiontoken.org/) [2](https://brave.com/brave-rewards/) [3](https://brave.com/tips/)) to keep people paid while preserving privacy. Using a chromium fork does nothing to challenge the hegemony that Google's engine has on the internet, and I'm a bit ambigious on several aspects of their project (and the fact that the browser is funded and run by Brendan Eich). However, these differentiators are a net positive. It also helps that [Brave have committed to not implementing FLoC](https://brave.com/why-brave-disables-floc/) in their browser as well.

### Use Ad Blockers

This is tangential to FLoC, but if you want to send a message to advertisers that their garbage content is not welcome, consider using a content blocker. There are two varieties of content blockers:

1. **Host-Based (Domain-based) System-Wide Blocking:** These block outgoing requests to ad servers and known malicious domains from your browser and all apps running on your system. You can set this up one of three ways:
    * [**NextDNS**](https://nextdns.io/) is an alternative DNS provider that you can use instead of your ISP's or Google's DNS services. In addition to stopping them from spying on your traffic (at least reducing one vector anyway), NextDNS comes equipped with a number of great blocking lists that will block ad and tracking domains. 
    
       Their free tier allows a generous 300,000 queries per month from unlimited devices, and the paid tier is about $2/month for unlimited requests. I have been a happy paying customer for a year, and I definitely recommend it. It is easy to set up on all your devices using their apps/programs.
    
    * [**PiHole**](https://pi-hole.net/) is a nifty service that can be loaded onto a Raspberry Pi and hooked up to your home router. This way you only need to configure the device once, and any other device connecting to your WiFi will automatically reap the benefits without any extra setup.

    * **Hosts File** is a file on your system (`/etc/hosts` on Linux, `C:\Windows\System32\drivers\etc\hosts` on Windows, and so on.) You can use publicly available lists ([1](https://someonewhocares.org/hosts/) [2](https://github.com/StevenBlack/hosts/blob/master/hosts)) and paste them into this file to block outgoing requests from that particular device only. It needs to be configured on every device you have, and not all of them allow it (Android devices, for example, need to be rooted to edit the hosts file.) Still, it is a good low-level solution if you don't need it to scale.
2. **Browser-level Blocking:** These are browser extensions that do host-based blocking as well as more powerful blocking such as rule-based and cosmetic filtering. The only extension you need (and the only one I recommend) is [uBlock Origin](https://github.com/gorhill/uBlock). It is the safest and most comprehensive of the lot. They have also added a rule that will [reject any FLoC requests](https://github.com/uBlockOrigin/uBlock-issues/issues/1553) from websites. 

    There are several other options but I don't care for any of them. Each comes with its own issues, ranging from reports of [selling user data in the past](https://www.businessinsider.com/evidon-sells-ghostery-data-to-advertisers-2013-6?IR=T), to showing [preferential treatment to sites who paid them not to block ads on them](https://blog.wsi-emarketing.com/adblock-acceptable-ads-unacceptable-extortion/). Seriously. Stick to uBlock Origin.

### Opt Out of FLoC

You've got to love Google. They implement new standards overnight and then suddenly the onus is on you to opt-out of them. FLoC by default is enabled for every site you visit on Chrome unless the webmaster opts out of it specifically. 

Now, if you're operating a site like mine which has no ads and/or embedded scripts that might request the cohort ID from a user's device, opting out isn't as necessary and is probably only ceremonial right now. That said, if you aren't familiar with 100% of the code embedded in your site, opting out is a good idea. If you want to send a signal to Google that their hijinks are not welcome, opting out is a good idea. If you're unlikely to see any benefit or hindrance with or without FLoC, opting out is a good idea. As of now, opting out is pretty easy. You need to send the following HTTP response header with your site.

```
Permissions-Policy: interest-cohort=()
```

I use Netlify, which supports two ways of adding headers. You can either use the [netlify.toml](https://docs.netlify.com/routing/headers/#syntax-for-the-netlify-configuration-file) file, or a separate [_headers](https://docs.netlify.com/routing/headers/#syntax-for-the-headers-file) file in your output folder. I opted for the latter. This is what my _headers file looks like (you can use most of these for your own site, since I went for privacy-respecting recommended defaults as per [Mozilla Observatory's](https://observatory.mozilla.org/) web best practices).

```
  Content-Security-Policy: default-src 'none'; img-src 'self'; script-src 'self'; style-src 'self'; frame-ancestors 'none'
  Referrer-Policy: no-referrer, strict-origin-when-cross-origin
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  X-XSS-Protection: 1; mode=block
  Permissions-Policy: interest-cohort=() 
```

Paramdeo Singh has put up [a very useful post](https://paramdeo.com/blog/opting-your-website-out-of-googles-floc-network) stating how you can add this header on a variety of hosting solutions.

### Conclusion: Everything sucks

I don't like ads. I doubt that their purpose has, for a while (or ever), been to inform rather than to manipulate. However, the ugly truth of the modern internet is that a large portion of our use is subsidized or outright facilitated by advertising. Many of the sites we visit regularly are kept afloat only due to the ad revenue they bring in. Without this income (often the primary income for the site owner), the owners may be forced to shut down the sites that serve us such value, in pursuit of more lucrative ventures. If tomorrow the advertising industry were to blip out of existence, it is not unlikely that a huge portion of the internet will sink as well. 

An argument can be made that the lack of financial safety nets and the need to keep squeezing money out of unsuspecting users leads to the internet and the world in general becoming perverted and commercialized. We are forced to look at things and rework them to ensure they not only make money, but also please the powers that be so that your income stream isn't disrupted due to you getting deplatformed or shadow-banned, for example. Until an alternative model for subsistence comes up, this is the sorry state of the internet we frequent daily. 

Still, pushback against targeted advertising is needed. Contextual, non-targeted ads do work as demonstrated by DuckDuckGo and literally the entire industry before targeting and surveillance became a mainstay. We must do everything in our power to retain autonomy. If sending a signal is all that we can do, we must at least do that.



