+++
title= "Fix the Dock on PopOS for Productivity and Profit"
date= 2021-08-07
description= "PopOS is a superb distro, but the new dock could do with some changes. Here's how."
[extra]
listed=true
+++

After years on KDE and then a variety of minimal window managers, I installed [System76's PopOS](https://pop.system76.com/) on my personal laptop a few months ago. GNOME has, historically, really not been my thing, but I've come to really appreciate the way Pop does things.

In many ways Pop has provided a very sane, quick set of defaults that gets out of my way and doesn't need me to tweak much to get started and go about my work. The new [COSMIC desktop](https://blog.system76.com/post/655369428109869056/popos-2104-a-release-of-cosmic-proportions), which is what they call their collection of tweaks on top of GNOME, brings quite a few usability improvements. One of these is the [Cosmic Dock](https://github.com/pop-os/cosmic-dock/), which seems to be some kind of fork of the GNOME extension [Dash to Dock](https://github.com/micheleg/dash-to-dock).

This is pretty cool for laptop users who don't always want to be using keyboard shortcuts to open up applications or switch between them. Using my thumb to navigate while typing with my fingers has been pretty good for me. That said, the default behaviour of the dock is a bit unnatural to me: you can't click on an icon to minimize the window, and if you have multiple instances of the program open, you click on the icon to cycle through the open instances. I would like this to bring up a preview and let me pick which instance to go to directly, which is what panels on KDE and the like usually do.

Turns out this is fully possible, with a little tinkering under the hood. Here's how:

1. Install `dconf-editor` from apt or your package manager
2. In `dconf-editor`
    1. Navigate to `org.gnome.shell.extensions.dash-to-dock`
    2. Set the `click-action` to `minimize-or-previews`. This does:
	    1. Single app in background, focus it.
	    2. Multiple apps in background, show the previews so you can pick the app you want.
	    3. App already focused, minimize it.

This works about as well as I want it to now. Thanks to Nathanael Anderson for providing [the solution](https://github.com/pop-os/cosmic-dock/issues/21) on GitHub.