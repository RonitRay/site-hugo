+++
title= "How I Handle My Passwords"
date= 2021-02-21
description= "My only-slightly eccentric and perhaps unnecessary password workflow."
[extra]
listed=true
+++

This post comes in soon after [LastPass announced](https://blog.lastpass.com/2021/02/changes-to-lastpass-free/) that they are restructuring their free tier to only allow access from one category of devices, i.e. only desktops or only mobile devices. I assume this will be a no-go for many users, and given the high (~$36/year) subscription costs, several people will be unwilling to upgrade to their premium offering.

If you're not using a password manager, you're just asking for trouble, and/or putting in a lot of unnecessary effort memorizing several passwords when you could just remember one. My recommendation to anyone who is starting out or looking to switch from LastPass and wants a very similar experience is the excellent [Bitwarden](https://bitwarden.com/), a free and open source offering that offers most of the features you would need in their free tier and also a few premium options at roughly $10 a year. It is far from the only option though, there are several very good recommendations a simple web search will get you.

### What Password Manager Do I Use?
I've been meaning to document the slightly eccentric way I manage my passwords for a while, so here goes. My password manager of choice is [**KeepassXC**](https://keepassxc.org/). What do I like about it?

- It is **offline**. You don't need to be connected to the internet to access your passwords or check secure notes.

- Everything is on a **single file**. While an argument can be made that it is a single point of failure and if the file is corrupted you lose all your passwords, I haven't really experienced or encountered any such issues in the few years I've been following news on password managers. Having the entire database be a single file is great for portability purposes.

- The option to use a **keyfile** alongside your password is great for security, and since any file can be a keyfile, it's a pretty good foil for someone who gains access to your computer by chance.

- It is **open-source**, audited, and has been around for years. This is, for me, a good enough marker of trust. Further, it's not a SaaS product so even if development on one KeePass client stops tomorrow, I lose essentially nothing. I can continue using the present version of the client indefinitely, or switch to a new client without changing much because the underlying standard remains the same. 

### How Do I Store My Passwords?

I have a keepass .kdbx database and a 128bit keyfile. These lie in an encrypted [Veracrypt](https://www.veracrypt.fr/en/Home.html) container on my PC that is dismounted until I need it. 

That would be the end of it if I only stuck to my PC, but I have a bad habit of using my phone for certain online accounts, and I also needed the security of having my passwords backed up in case my computer failed or was lost/stolen, or if I needed access to them in a pinch on some other device. Here's what I did to get around that.

**For mobile**, I use [**Syncthing**](https://syncthing.net/). The password database is synced over Syncthing every once in a while, either manually when I add or update a password, or periodically to be safe. The keyfile doesn't go over Syncthing, I had transferred it offline over USB. Probably unnecessary, but I did it anyway. The Android client I use is [**KeePassDX**](https://www.keepassdx.com/), although [KeePass2Android](https://github.com/PhilippC/keepass2android) is a very good option too. Both have essentially the same feature set and are open-source and reliable. They support Android's native autofill, but since this is hit and miss on my current phone (a major pain point when I used to use LastPass,and then Bitwarden), I've taken to using the **virtual keyboard** provided by both these apps. Essentially, when you want to login, you select the entry from your vault and load the virtual keyboard. It will then fill in whatever field you want from your vault without using the clipboard or any nasty shenanigans. Clipboard hijacking is among the easiest ways to grab someone's password, and it is a nightmare on Android since [a ton of applications have been caught snooping on clipboard contents indiscriminately in the past.](https://www.aol.com/video/view/5f024c3f3092ab5c5b6f0441/)

**Cloud** backups have undeniable advantages, and the convenience factor for SaaS password vaults like LastPass, Dashlane etc is undeniable. Now, KeePass databases are encrypted using AES, so you should be good to go by just backing up said database over a cloud storage provider of your choice. Because I thrive on paranoia and I don't like making things easy for myself, I took this a step further and instead back up the veracrypt container rather than the database. This is presently done over Git but it can be replaced by pretty much any cloud storage provider. This way there are at least two layers of one of the most reliable encryption schemes we know that stand guard before my passwords. Of course, none of this matters if AES is broken in the near or distant future, but that is well outside my threat model at the moment.

All this takes a good while to set up at first, but once you're set, I've found that you can pretty much go about your life painlessly and without any issues. Whether you go as far as I have or further is entirely dependent upon your threat model, but at the very least I definitely recommend using a password manager for everyone, from yourself to your grandparents. I'd always say an open-source option is the way to go, but mainstream proprietary products that have been around for a while, are unlikely to suddenly disappear, and have been audited are certainly much better than using no password manager at all.