
## My First Digital Autopsy: How I Created & Investigated My Own Disk Image (Chaos Included :/ )

# Introduction

If there’s one thing, I learned in digital forensics..... It’s that nothing works the first time.
When I decided to analyze a disk image using Autopsy (a real forensic investigation tool) I
thought “Cool!!!! This will be quick.”

# ***dramatic music***

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
