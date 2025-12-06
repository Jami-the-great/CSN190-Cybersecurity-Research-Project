
## My First Digital Autopsy: How I Created & Investigated My Own Disk Image (Chaos Included :/ )

# Introduction

If there’s one thing, I learned in digital forensics..... It’s that nothing works the first time.
When I decided to analyze a disk image using Autopsy (a real forensic investigation tool) I
thought “Cool!!!! This will be quick.”

 ***dramatic music***

Downloads failed.

Autopsy broke.

My VM judged me.

Before this project, digital forensics felt like something only FBI agents with sunglasses
do.... Kicking down doors and recovering deleted evidence, in 5 minutes like on TV. But
then I installed Autopsy inside a Linux virtual machine and suddenly I was the investigator,
digging into a real disk image and uncovering files that thought they were deleted forever.
including my own password, which was both hilarious and slightly concerning.

In this article I’ll take you through my first real forensic lab experience, using Autopsy inside
a Linux virtual machine. By the end you’ll know how to set up your own forensic
environment and analyze a suspicious drive just like the pros (no badge required).

# Why Autopsy? (Purpose & Background)

(aka: Why I decided to become a digital detective for a week)

I chose Autopsy because digital forensics, is the field I want to grow into..... Where every
file, timestamp and deleted selfie can become evidence. Autopsy is used by cyber
investigators in:

● Law Enforcement

● Corporate security & insider threat teams

● Digital Forensics & Incident Response units (DFIR)

Why? Because Autopsy can do things your Recycle Bin could never dream of:

● Recover deleted files

● Reconstruct user activity

● Analyze web browsing & downloads

● Extract metadata (the secret details files leave behind)

● Build timelines of what happened, when and by who

It’s like a time machine for digital evidence and I wanted to learn how to drive it.

# My goals:

I wanted to go beyond “reading the documentation” and actually do the work of a forensic
analyst:

● Create a real disk image (.dd)

● Mount it inside Autopsy as evidence

● Explore the file structure like a detective

● Look for “artifacts” (files, logs, passwords)

● Understand how analysts build cases from tiny clues

This tool is used after an attack when it’s time to trace the damage and find out:

What happened?

Who did it?

And what did they try to hide?

# Personal Motivation

To be honest.... Part of this was me living out my inner Penelope Garcia from Criminal
Minds

But the bigger reason ?

Digital forensics isn’t just about technology.

It’s about truth..... Recovering what someone thought they erased forever. Even when a user
tries to delete evidence, rename things, or wipe logs the computer still remembers.

And with tools like Autopsy.... So can I.

Installation & Setup Tutorial

(aka: Me vs. The VM)

This was the part, where I realized Autopsy doesn’t just open like a normal app, you have to
fight for it a little first.

Here is everything I used to set up my digital autopsy lab:

What You’ll Need (Prerequisites)

● Ubuntu Linux (in VirtualBox)

● Autopsy 2.24 (browser version) the one that actually worked

● Firefox browser

● Terminal access

● Basic Linux command knowledge

● Patience (Autopsy WILL break at least once... or 20 times)

# Official tool links:

● GitHub Repo I referenced: https://github.com/mikeroyal/Digital-Forensics-Guide

● Autopsy Download: https://www.sleuthkit.org/autopsy/

Step-by-Step Setup

Step 1 — Install Autopsy/ Forensic Dependencies

To prepare the VM for digital forensics I installed core packages Autopsy depends on:

sudo apt-get update

sudo apt-get install sleuthkit

Why this matters: SleuthKit contains the backend tools, Autopsy uses to extract artifacts.

If dependencies are missing → Autopsy will launch but nothing will analyze.

Step 2 — Launch Autopsy from Terminal

Autopsy doesn’t open as a normal desktop application, It must be launched like this:

Sudo autopsy

What should happen:

● The terminal starts a server

● It shows a URL like:

http:/localhost:9999/autopsy
<img width="1400" height="900" alt="Screen Shot 2025-12-03 at 7 29 48 PM" src="https://github.com/user-attachments/assets/adb2e1cc-f338-447d-94b3-b6c2e124b180" />



