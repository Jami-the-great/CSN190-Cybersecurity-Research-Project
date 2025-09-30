# Topic 1 – Digital Evidence Collection for Mobile Devices

**Resource 1** 

**Citation**: FOUNDATIONS OF MOBILE FORENSICS: AN ACADEMIC APPROACH. (2024). Issues in Information Systems. https://doi.org/10.48009/3_iis_2024_108 


**Type**: Academic Article 


**Synopsis:** Anyone who wants to start learning about mobile forensics should read this article!!! It talks about the types of data that phones store, the multiple ways to get it (logical vs. physical) and why you need to keep track of everything you do. It’s a little formal but I like that it gives me the “why” behind the steps I’ll be practicing. 


**Link:** https://iacis.org/iis/2024/3_iis_2024_94-108.pdf 


**Relevance:5/5** - Perfect starting point, I need a map before I start exploring. This gives me the basics so I won’t feel lost once I’m actually using tools. 

**Resource 2** 

**Citation:** Guttman, B., White, D. R., Software & Systems Division, & Walraven, T. (2022). Digital Evidence Preservation: Considerations for Evidence Handlers. In U.S. Department of Commerce, National Institute of Standards and Technology, G. M. Raimondo, & L. E. Locascio, NIST Interagency Report. https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8387.pdf 

**Type:** Government Technical Report 

**Synopsis:** What happens when you have the evidence ? That's what this one is about… It talks about, safe handling, hashing and the chain of custody. Basically how to make sure the data you collected doesn’t get tossed out in court. It’s less about “how to grab the data” and more about “how to protect it once you have it”. 

**Link:** https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8387.pdf 

**Relevance: 5/5** – Super helpful because collecting evidence is only half the battle. This shows me how to protect what I find so it actually counts if anyone questions it later. 

**Resource 3**

**Citation:** Peter Brockie. (2018, February 2). Cellebrite UFED Cellphone Forensic Extraction Device teardown YouTube. https://www.youtube.com/watch?v=7LLGGCXH9MQ 

**Type:** Webinar/Technical Video 

**Synopsis:** This webinar digs into Cellebrite UFED which is basically the tool investigators use in the field. It shows what the device can do and how it works and talk through how it connects to phones. Seeing the device in action connects the dots between theory and the physical process of extraction.

**Link:** https://www.youtube.com/watch?v=7LLGGCXH9MQ

**Relevance: 5/5** — Honestly this video helped everything click. Seeing the UFED in action made the whole extraction process feel way more real. It’s one thing to read about how data gets pulled from phones…. It’s another to actually watch the tool do its thing. This is the kind of tech I’d be working with so yeah super relevant. 

**Resource 4**

**Citation:** Mobile forensics - iOS and Android. (n.d.). YouTube. https://m.youtube.com/watch?v=TFjEg6g2bW4 

**Type:** Educational Video 

**Synopsis:** This video, doesn’t just talk about mobile forensics. It actually shows it happening on iOS and Android. You can see each steps, the tools and the differences between the two systems. To be honest It’s super beginner friendly and easy to follow.  

**Link:** https://m.youtube.com/watch?v=TFjEg6g2bW4 

**Relevance: 5/5** – I’m a visual learner so watching someone do it, helps me picture my own first run through instead of just guessing from text. 

# Topic 2 – Static vs Dynamic Malware Analysis  

**Resource 1** 

**Citation:** Ijaz, M., Durad, M. H., & Ismail, M. (n.d.). Static and Dynamic Malware Analysis Using Machine Learning. Retrieved from https://www.researchgate.net/profile/Muhammad-Ijaz-25/publication/331941089_Static_and_ Dynamic_Malware_Analysis_Using_Machine_Learning/links/5ce36dc5a6fdccc9ddc14c1f/St atic-and-Dynamic-Malware-Analysis-Using-Machine-Learning.pdf 

**Type:** Academic / Research Article

**Synopsis:** This paper experiments by pulling ~92 static features from executable binaries and ~2,300 dynamic features from malware run in a Cuckoo sandbox. Then the authors trained machine learning models on both sets to see which gave better results. Static analysis surprisingly performed slightly better (around 99% accuracy) because some malware was smart enough to notice it was in a sandbox and hid its real behavior. It’s technical but easy enough to follow and gives real numbers that show the strengths and weaknesses of each approach. 

**Link:** https://www.researchgate.net/profile/Muhammad-Ijaz-25/publication/331941089_Static _and_Dynamic_Malware_Analysis_Using_Machine_Learning/links/5ce36dc5a6fdccc9ddc14 c1f/Static-and-Dynamic-Malware-Analysis-Using-Machine-Learning.pdf 

**Relevance: 5/5** – I really like this paper because it doesn’t just talk theory. It shows real numbers on how static and dynamic analysis actually perform. I like that it proves static can sometimes beat dynamic when malware tries to hide in a sandbox. That’s the kind of insight I want !!!  real numbers that help me understand what’s actually happening and make my project feel backed in real testing not just theory. 

**Resource 2** 

**Citation:** Coan, J. (2022, June 14). Cybersecurity skills: dynamic and static malware analysis. CyberMaxx. https://www.cybermaxx.com/resources/dynamic-and-static-malware-analysis/ 

**Type:** Industry Blog / Technical Article 

**Synopsis:** This article breaks things down in a straightforward way, It explains what each method really means. Like how static is all about looking at the code without running it and how dynamic is about watching what the malware does in a safe space. It even points out that some malware can tell when it’s being watched and hide its bad side.

**Link:** https://www.cybermaxx.com/resources/dynamic-and-static-malware-analysis/ 

**Relevance: 4/5** – This article breaks things down in a straightforward way. Explaining what each method really means and how they’re used to understand and investigate malware. 

**Resource 3** 

**Citation:** Shijo, P., & Salim, A. (2015). Integrated static and dynamic analysis for malware detection. Procedia Computer Science, 46, 804–811. https://doi.org/10.1016/j.procs.2015.02.149 

**Type:** Academic Article

**Synopsis:** This paper talks about catching brand new malware by looking at the API calls it makes. The authors collect data from both static and dynamic analysis and use machine learning to predict if something’s malicious. It’s definitely technical but still understandable and shows how the two methods, can work together. 

**Link:** https://doi.org/10.1016/j.procs.2015.02.149 

**Relevance: 5/5** – I like this because it shows a smart way to combine static and dynamic analysis to catch even unknown threats. Giving me ideas I can use. 

**Resource 4** 

**Citation:** Malware Analysis Masterclass 2025 | Static + Dynamic Tricks. (n.d.). YouTube. Retrieved September 27, 2025, from https://m.youtube.com/watch?v=QYq_DzLJJng 

**Synopsis:** This masterclass walks through how analysts actually use both static and dynamic techniques side by side. The presenter first shows how to inspect malware without running it, looking at file headers, strings and other tell tale artifacts and then moves into a sandbox to watch the malware’s behavior when it actually runs. You get to see the tools in action and understand why some malware will even try to hide when it detects a sandbox. 

**Link:** https://m.youtube.com/watch?v=QYq_DzLJJng 

**Relevance: 5/5** – I love this because it makes the process feel real. You literally get to sit back and watch someone pull apart the malware file and inspect its signatures and headers. Then you see it run in a sandbox to catch its live behaviour.  




# GitHub Project 1 — Digital-Forensics-Guide

Citation: mikeroyal. (n.d.). GitHub - mikeroyal/Digital-Forensics-Guide: Digital Forensics Guide. Learn all about Digital Forensics, Computer Forensics, Mobile device Forensics, Network Forensics, and Database Forensics. GitHub. Retrieved September 26, 2025, from https://github.com/mikeroyal/Digital-Forensics-Guide

Type: Educational / Reference Guide

Synopsis: This repo feels like a cheat sheet. It doesn’t do the work for you but it lines up all the big concepts, tools and links so you’re not lost in the air. Mobile device forensics, computer forensics, network forensics and database forensics is all in here. I see it as the “GPS” before you start driving… The only catch, it’s more guide than hands on so you still need to bring your own tools.

Stars/forks: 2.3k stars, 252 forks (active popularity)

Activity: 81 commits, includes “Getting Started with Digital Forensics” scripts and a glossary.  

Strengths: Excellent for learning for finding tools you didn’t know and for linking out to other repos. It’s a strong “first stop” when exploring the field.

Link: https://github.com/mikeroyal/Digital-Forensics-Guide

Relevance: 4/5 — Perfect for orientation but not enough by itself. You’ll need other tools in play to actually collect and preserve evidence.

# GitHub Project 2 — SleuthKit

Citation: sleuthkit. (2025). The Sleuth Kit (TSK). GitHub. https://github.com/sleuthkit/sleuthkit

Type: Forensic Toolkit

Synopsis: SleuthKit is the old reliable of digital forensics. It lets you dig into disk images, partitions, file systems, uncovering deleted files, hidden metadata and activity trails. It’s the kind of tool investigators quietly rely on when they need solid, defensible evidence. It doesn’t hold your hand or wow you with a flashy interface, but that’s kind of the point ( it’s serious, raw, and respected in the field).

Link: https://github.com/sleuthkit/sleuthkit

Relevance Rating: 5/5 — Exactly what evidence work requires, depth, reliability and credibility in court.



# Topic 2: Static vs Dynamic Malware Analysis

GitHub Project 3 — MobSF

Citation: MobSF. (n.d.). GitHub - MobSF/Mobile-Security-Framework-MobSF: Mobile Security Framework (MobSF) is an automated, all-in-one mobile application (Android/iOS/Windows) pen-testing, malware analysis and security assessment framework capable of performing static and dynamic analysis. GitHub. Retrieved September 26, 2025, from https://github.com/MobSF/Mobile-Security-Framework-MobSF

Type: Static + Dynamic Analysis Framework

Synopsis: MobSF is an awesome all in one tool for mobile app security. It can perform static analysis (code, manifest, binaries), dynamic analysis (behavior/runtime) and even malware scanning for Android, iOS and Windows mobile platforms. It includes dashboards, reporting, hooks for instrumenting apps, etc.

Stars/forks: high community use and visibility.  

Activity: actively maintained with updates and issue tracking ongoing.  

Strengths: covers static and dynamic views, rich UI and good for experimentation.

Limitations: setup may be complicated (emulators, dependencies) possibly heavy resource usage. Also not strictly “evidence collection” in the legal sense more toward app security/malware screening.

Link: https://github.com/MobSF/Mobile-Security-Framework-MobSF

Relevance: 5/5 — This one ties both of my topics together(mobile devices + malware behavior). Definitely demo worthy.



# GitHub Project 4 — malwareHunter

Citation: Abdesslem. (n.d.). GitHub - abdesslem/malwareHunter: Static and automated/dynamic malware analysis. GitHub. https://github.com/abdesslem/malwareHunter

Type: Malware Static/Dynamic Analysis Utility / Tool

Synopsis: malwareHunter is designed to automate parts of malware analysis (static and dynamic) aspects. It helps in identifying malware signatures, behaviors and runs certain analysis modules. It reminds me of starting out in Python…. Short scripts that do one thing well. It keeps things simple enough that you can actually focus on learning instead of wrestling with the setup.

Limitation: it’s not as deep as Cuckoo or MobSF but easier to digest.

Link: https://github.com/abdesslem/malwareHunter

Relevance: 4/5 — Not the star of the show but a great sidekick for learning and experimenting.



# Comparison Notes

Forensics Tools: Digital Forensics Guide is the map while SleuthKit is the shovel. They balance each other out…. One shows you what’s out there and the other lets you actually dig. 

Malware Side: MobSF is the big lab setup that gives you both static and dynamic views in one place. While malwareHunter is the smaller toolkit you keep in your pocket… Together they make a good balance, one teaches you the deep stuff and the other lets you practice without getting buried in complexity.

# Questions That Emerged

1. How do I go from messing around with smaller tools like malwareHunter, to feeling confident with bigger ones like SleuthKit and MobSF when it comes to real investigations?

2. How can I practice with these tools now, in a way that actually prepares me for the kind of cases I want to work on in the future?

3. What I’m noticing is every tool teaches me something different, so how do I pull all those lessons together into one clear path toward becoming a digital forensic examiner?
