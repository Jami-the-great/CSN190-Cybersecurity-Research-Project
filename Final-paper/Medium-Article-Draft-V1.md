
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
If it doesn’t launch? → reboot your VM and try again. Trust me.

Step 3 — Open Autopsy in Firefox

Copy/paste the server URL into Firefox:

http://localhost:9999/autopsy

Now the Autopsy dashboard appears. Here is where my confidence returned for 5 seconds

<img width="1400" height="900" alt="Screen Shot 2025-12-05 at 6 11 47 PM" src="https://github.com/user-attachments/assets/d88658ba-980a-404f-95d6-60a633a055d8" />

Step 4 — Autopsy requires a disk image to investigate.

I tried downloading sample forensic images from:

● DFIR datasets
● Autopsy documentation
● Random cyber blogs

Every. Single. Link. Failed.

Error examples:

NoSuchKey

File Not Found

That’s when ChatGPT came in clutch with a better idea: “Why not make your own forensic
image?”

Genius. Free. No broken links.

And I get to be the cyber criminal and investigator

Step 5 — Creating My Own Disk Image (.dd)

This is where I learned something BIG:

A .dd file is a bit for bit copy of an entire storage device including deleted files, slack space
and hidden metadata.

Meaning:

Even if someone deletes evidence..... The dd file keeps the ghost of the data.

Command I used:

sudo dd if=/dev/sda of=evidence.dd bs=1M count=1000

Breakdown:

| Flag | Meaning|
|-----:|--------|
|if=/dev/sda | Input file = whole VM disk |
|of=evidence.dd | Output file = forensic image|
| bs=1M | Copy in 1MB blocks |
| Count 1000 | Only first 1GB for fast testing |

<img width="1400" height="900" alt="Screen Shot 2025-12-05 at 6 21 44 PM" src="https://github.com/user-attachments/assets/2ee0cbdc-db52-44d3-a5a5-193aade2317a" />

Then I added a juicy clue inside the VM:

password.txt → “Thegreat1234.”

If future me ever denies it, the digital evidence will drag me.

![EVIDENCE1](https://github.com/user-attachments/assets/01eae89c-baab-4728-8ee2-2889d1981bda)

Step 6 — Load Image into Autops

Autopsy → Add Data Source → Disk Image → choose evidence.dd

Autopsy begins indexing:

● File names

● Deleted files

● Metadata

● File system timeline

(Slow is normal — crime scenes take time )

<img width="1400" height="900" alt="Screen Shot 2025-12-05 at 6 29 18 PM" src="https://github.com/user-attachments/assets/83504cda-e1ff-49fb-8777-4210cb4abf19" />

Troubleshooting (Documented Fixes)

These errors tried to ruin my forensic dreams:

| Problem |why it happened|
|-----:|-------------------------|
|“File Analysis Disabled”|I accidentally added duplicate images | Restart case + Add image once |
|“Invalid Host”| Broken case directory| Delete case folder + create new|
|GUI wouldn’t appear|Autopsy wasn’t running in terminal | Relaunch sudo autopsy |

|fix| ..
|-----:|-------------------------|
| Restart case + Add image once |
| Delete case folder + create new|
| Relaunch sudo autopsy |

But honestly these problems taught me more than if everything worked perfectly.

# Section Summary

By the end of setup:

● Autopsy installed & running

● Browser UI accessible

● Real disk image created

● Evidence successfully ingested

● Investigator mode activated

● Using Autopsy to Uncover Hidden Credentials

(aka: Me exposing myself as my own cyber criminal)

Once my .dd image successfully loaded into Autopsy the real fun began...... Evidence
hunting. Autopsy instantly scanned the image and rebuilt the file system like a digital crime
scene. I could finally play the role of investigator and my first mission was simple:

Find proof of activity from the “suspect” (Spoiler: the suspect was me.)

Autopsy organizes everything beautifully..... Deleted files, user directories, metadata,
timestamps, all displayed like breadcrumbs left behind by someone who thought they were
being sneaky.

Step 1 — Navigating the Evidence Tree

The left side showed the full structure of my VM’s storage:

● Root filesystem

● Home folder

● System logs

● Deleted file category

● File metadata artifacts

This is where a forensic analyst starts connecting dots:

What files exist?

What changed recently?

What looks suspicious?

<img width="1400" height="900" alt="Screen Shot 2025-12-05 at 6 35 27 PM" src="https://github.com/user-attachments/assets/48006ffa-4a98-4132-bc8c-1f90d6f1b7a4" />

Step 2 — Locating the “Key Evidence”

Inside the home directory, Autopsy revealed a file:

password.txt

That familiar nervous feeling hit me.... Because I knew exactly what was inside. But seeing
it appear as evidence made the experience feel real.

Autopsy allows viewing files in different modes:

● Text/ASCII

● Hex view

● Metadata view (timestamps, permissions)

![EVIDENCE1](https://github.com/user-attachments/assets/01eae89c-baab-4728-8ee2-2889d1981bda)

What did the file reveal?

Thegreat1234.

Yep.

My own password.

Found. Flagged. Exposed.

Zero hacking skills required.

What This Shows in Real Forensics

Even simple text files can become critical evidence.

Credentials found on a disk can lead to:

● Account access

● Data exfiltration trails

● Attribution of the suspect

● And in real cases — courtroom proof

If that file had been deleted?

Autopsy still could’ve recovered it.

Because a .dd image captures:

● Deleted files

● Slack space

● Unallocated sectors

● All hidden metadata

So even if a suspect wipes evidence...

The drive remembers.

And Autopsy will snitch.

Step 3 — Verifying the Source

Autopsy metadata showed:

● When the file was created

● Modified timestamps

● User that made it (me)

● Where it lived before imaging

In forensics timestamps = truth.

They establish the “who, what, when” which builds the case narrative.

![EVIDENCE2](https://github.com/user-attachments/assets/04e87b3e-18b5-4469-a165-6e83914df5d2)

Results Recap

By the end of my investigation, I confirmed:

| Finding |Autopsy Results|
|-----:|-------------------------|
|Evidence image | loaded Successful|
|User directory | parsed Visible|
|password.txt |located Found |
|Content readable | “Thegreat1234.”|
|Metadata extracted |Timeline built|

This wasn’t a fake classroom dataset..... This was real user evidence from a real system.

This is Why This Was So important for Me

I wasn’t just looking at files.

I was uncovering digital behavior.

Something I created casually in the VM suddenly became:

● Traceable

● Documented

● Investigable

And if this were a real insider threat case?

That password could be the key to the entire compromise.

Forensics teaches one ultimate lesson:

There’s no such thing as “deleted.”

Research Insights - What the Experts Say vs. What I Experienced

To make sure my hands on experience lined up with real forensic standards, I analyzed two
professional sources: a NIST digital forensics report and a forensic encryption research paper.

Both, helped me understand the bigger picture behind the tiny clues I found inside my .dd
image.

Article 1:

National Institute of Standards and Technology (2022).

“Digital Investigations: Evidence Retention and Verification.”

https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8387.pdf

This is an official government publication, that helps define how digital evidence should be
preserved and validated during investigations. NIST emphasizes that the most important rule
in forensics is maintaining the integrity of the original data.... Meaning you should never
modify a suspect device during analysis. Instead investigators create a forensic disk image
that preserves:

● deleted data

● Slack space

● Metadata

● timestamps and file signatures

This connected directly to what I did in my project. By using the dd command to create a bit
for bit copy, I unknowingly followed a real world standard that actual forensic labs are legally
required to follow. NIST also stresses repeatability and documentation which explains why
Autopsy logged every scanned artifact and timestamp, those logs prove the evidence wasn’t
tampered with.

Key takeaway:
I didn’t just make a random .dd file, I created a legally defensible copy of evidence. My
process wasn’t just “school work” it was a valid investigative method.

Article 2:

S-Technolock (2023).

“Forensic Encryption & Discovering Hidden Data.”

https://www.stechnolock.com/article/Forensic-Encryption-Discovering.pdf

This article explores how encrypted files, hidden partitions and user deleted data can still be
uncovered through forensic imaging tools. It explains that even when a suspect uses
encryption or wipes files, fragments remain inside unallocated disk space, exactly where a
tool like Autopsy can dig.

The paper gave examples of investigators recovering:

● Passwords

● deleted chat logs

● concealed files

● metadata proving user behavior

This aligned perfectly with what happened when Autopsy exposed password.txt. Even though
the file wasn’t deleted in my experiment, the research showed that if I had deleted it Autopsy
still could have recovered it from unused space or metadata trails. The computer literally
snitches on you.

Key takeaway:

My discovery of a single plain text password might seem small but in real world cases? That
could be the key that unlocks everything else.

Practice + Research = Real Understanding

Hands on work taught me how Autopsy reveals data.

Research taught me why it matters in criminal investigations. Together they showed me that
digital forensics isn’t magic.... It’s science, process and a lot of tiny traces computers fail to
hide.

Challenges & Problem-Solving

I wish I could say this project went smoothly....

But the technical chaos taught me more than success ever could.

Here are the most painful (but valuable) lessons:

Failed Image Downloads

Problem:

Every official sample disk image I tried to download was broken — “NoSuchKey” “File Not
Found” or the links were just dead.

My Reaction:

Confusion → frustration → consideration of career change

Fix:

ChatGPT suggested making my own disk image, which turned out to be the best decision of
the project.

Lesson:

If the resources fail you.... Create your own.

Autopsy Wouldn’t Launch Like a Normal App

Problem:

Clicking the desktop launcher did nothing.

Fix:

Learned I must launch it manually:

sudo autopsy

Lesson:

Some cybersecurity tools aren’t “user friendly.”

They expect YOU to be command line friendly.

File Analysis Disabled” / “Invalid Host”

Problem:

I accidentally added the same disk image multiple times during a case.

Fixes:

● Delete corrupted case folder

● Create a fresh case

● Only attach evidence once

Lesson:

Autopsy is powerful.... But it will absolutely fight you back if you poke it wrong.

Big Skill Takeaway:

I didn’t just learn how to run Autopsy, I learned how to debug, adapt and keep going when
everything breaks. That’s the real skill in cybersecurity.

Conclusion & Future Applications

This project didn’t just teach me how to open a forensic tool.... It taught me how to think like
a digital investigator.

At the start I felt like a student clicking buttons and hoping for the best. By the end, I was
confidently analyzing a real disk image, interpreting timestamps and uncovering digital
behavior including my own terrible password choices

What I accomplished:

● Installed and ran Autopsy inside Linux

● Created a legitimate forensic .dd image using dd

● Loaded and analyzed real user evidence

● Identified artifacts & metadata like a real examiner

● Documented errors and learned how to fix them

What surprised me the most?

How easy it is for a “normal” file to become forensic gold.

One little password.txt file revealed:

● Who created it

● When it was written

● Evidence of user activity

● A possible starting point for a cyber investigation

In the real world, that could be the thread that unravels an entire insider threat case or solves
a crime.

How This Changes My Path in Cybersecurity

Before this assignment:

Digital forensics felt like movie magic.

After this assignment:

I am the digital detective.

I gained both technical skills:

● Command-line tooling

● Disk imaging

● Artifact analysis

● Metadata interpretation

And soft skills that matter just as much:

● Troubleshooting when everything breaks

● Researching best practices

● Clear documentation

● Patience (lots of it)

What’s Next for Me

Now that I can properly analyze a disk image, I want to expand my forensics toolkit:

Learn memory forensics with Volatility

Practice network forensics using Wireshark

Try a mobile forensics platform like Cellebrite or IPED

Explore encrypted drive investigations And eventually..... I’d love to be part of an incident
response or DFIR team where uncovering the “invisible truth” is the job.

Final Reflection

Digital forensics taught me that computers never forgets and investigators must learn to listen
to the evidence.

If you’re curious about this field, try Autopsy yourself. Break things. Fix them. Investigate
your own digital footprints. Trust me..... It’s way more fun than watching cybercrime shows.

And hey..... You even get to be the one wearing the sunglasses this time.

Resources & Links

Here are all the tools, sources, and references that supported my investigation:

Tools Used

Autopsy — The Sleuth Kit UI

Official Download: https://www.sleuthkit.org/autopsy/

Digital-Forensics-Guide Repository (Referenced for learning)

https://github.com/mikeroyal/Digital-Forensics-Guide

Ubuntu Linux

https://ubuntu.com/download

Research Sources

NIST Digital Forensics Report (2022)

https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8387.pdf

S-Technolock: Forensic Encryption & Data Recovery

https://www.stechnolock.com/article/Forensic-Encryption-Discovering.pdf

ChatGPT Assistance for troubleshooting & guidance

Self-Assessment

What I’m Most Proud Of:

How much hands on learning this article represents. I didn’t just follow instructions, I
researched, struggled, fixed and documented real forensic methods.

What Still Needs Work:

Better screenshot annotations and adding more investigation examples (like deleted file
recovery or keyword search results).

Feedback I’m Looking For:

Do my explanations feel clear and helpful for beginners? Are there any places where I should
expand technical details further?

How This Article Shows My Skills:

● Technical execution

● Problem solving and adaptability

● Ability to explain complex concepts clearly

● Professional writing and documentation
● Real cybersecurity passion
