+++
title = "Leaving Note-Taking Applications"
date = 2020-10-15
description = "In which I attempt to simplify the way I take notes."
[extra]
listed=true
+++

One of the books I'm reading this week, _Make Time: How to Focus on what Matters Every Day_ by Jake Knapp and John Zeratsky, which is, by the way, the least self-helpy self-help book I've read in a while, maybe ever, had this passage that really resonated with me:

>_I’ve been burned by fancy tools. Back in 2006, I discovered the perfect productivity software: a simple but powerful app called Mori that allowed for infinitely customizable note taking and filing. I was elated, and spent countless hours configuring Mori on my laptop and loading all my projects into it. And I was right: It was perfect. Mori became an extension of my brain._

>_But after a few months, things started breaking down. I upgraded my computer’s operating system, only to find that Mori wasn’t compatible with the new version. I’d want to look at my notes at home but realize I had left my laptop at work. And then the developer shut down Mori altogether. I was distraught._

>_That’s the other problem with fancy tools: they’re fragile. Anything from a technical glitch to my own forgetfulness could keep me from getting into Laser mode and spending time on my Highlight. After Mori vanished, I started using simple, readily available tools to manage my work: text files on my computer, notes on my phone, basic Post-its, free hotel pens, that sort of thing. More than ten years later, my everyday tools work as well as ever. And whenever I get tempted by a new fancy tool, I just remember Mori._

Now I've never used Mori, but as I have been getting acquainted with the online productivity/self-improvement scene over the last few months, there has been a lot of talk about note-taking tools, workflows, and techniques. I've been drawn to it partly out of an appreciation for new technology as well as a desire to integrate note-taking into my life with some level of seriousness.

I'd like to think I value privacy more than most other things, and try to consider the privacy-convenience tradeoff for everything I do or adopt. So my findings about existing note-taking platforms were a little underwhelming:

- [Evernote](www.evernote.com) is encrypted "in-transit", which is a nice to-have, but not really useful against anything other than MITM attacks. My understanding is my notes would be stored in plaintext or some kind of basic encoding on their servers, that is fully accessible and decryptable by them. I can encrypt individual notes but there's no way I'd do it manually for every single note. It's not convenient.
- [OneNote](https://www.onenote.com/) claims to be encrypted at rest, which is not bad, but the keys are still generated, owned and controlled by Microsoft. I'd be trusting them with my data.
- [Notion](https://www.notion.so/) doesn't even bother to talk of encryption, their privacy policy is a little invasive-sounding to my paranoid brain, and essentially boils down to _trust us_, which I suppose is fair for this kind of service but I have no reason to trust them, any more than Microsoft for example.
- [Standard Notes](https://standardnotes.org/) is end-to-end encrypted and really awesome, I stuck with it for the longest time but it doesn't support Markdown on the free tier and the premium tier is a little expensive for my working-class Indian wallet that only started earning last year.
- [Joplin](https://joplinapp.org/) is very usable and was finally what I landed upon. Markdown is really easy to use, and it supported E2EE, with the caveat that I had to use another cloud storage service like Dropbox/OneDrive to store the encrypted notes on the cloud. Which means I am trusting at least two parties (Joplin and the cloud storage provider) to handle my data safely and really stay afloat.

This comes down to the passage from _Make Time._ I was already using Markdown in Joplin, and exporting my notes to a folder structure was trivial. I figured there's really no reason for my workflow to have to rely on either Joplin or a cloud provider for sync. Here's what I did:

1. "Notebooks" and nested notebooks/sections are just simple folders in a directory structure. Zero restrictions and it makes sense everywhere.
1. Notes are markdown files that are readable as-is as well as convertable to a prettier form, supporting web formatting for things like lists, tables, code snippets and blockquotes which I needed.
1. Full text search with grep is the easiest thing ever.
1. I edit notes in Vim, my text editor of choice on Linux desktop. There's no reason I wouldn't be able to edit them in any other editor, because they're text files.
1. I also use the [vim-markdown-preview add-on](https://github.com/JamshedVesuna/vim-markdown-preview) because it's very minimal, and doesn't need me to install NodeJS or some other bloated framework. Sure, no live preview, but rendering the note in a browser window beside the editor takes milliseconds and is just a hotkey away at any point in time.
1. I use [Syncthing](https://syncthing.net/) to locally sync my entire notes folder with my Android phone. It uses my local network so my files never travel over the internet (you can literally disconnect your ethernet cable to be sure). It is very easy to use once set up, and since the files themselves are really light (again, text files, woo-freaking-hoo!) sync is a matter of seconds even at scale.
1. On my android phone, my notes viewer/editor of choice is the very powerful and versatile open-source [Markor](https://play.google.com/store/apps/details?id=net.gsantner.markor&hl=en_US&gl=US), which has no internet permissions (and I've blocked from accessing the internet anyway via a firewall, just in case) and offers a great Markdown viewer as well as WYSIWYG editor if I need to write notes on the phone.

This is pretty much everything I needed, brought down to established open-source components and standards where possible. It is widely compatible, very portable, and easy enough to replace any one component if I need to, which is great. I'll figure out a redundancy solution eventually, but I reckon it's just a matter of setting up a backup script on a crontab or adding the notes folder to an rsync/Timeshift backup if I so desire.

I'm going to slug it out with this setup for a while at least, and see if it fits the bill. There might be parts of it I revisit in the future to improve usability/convenience/security, but time will tell. For now, I'm happy. Which is rare these days.
