---
layout: project
title: Project
subtitle: Dashboard Application
icon: fa-gear
projectNum: 3
---

The team I worked with at *Absolute Software* was the hosting operations team, and one of the problems we had was that there were so many dashboards showing us details and statistics about our various systems, we often couldn't keep up. Switching between these dashboards and refreshing them took time from our day, especially if there wasn't much to report. If there ever was an issue, it sometimes got hidden by other email alerts, or we would forget to check it. To solve this my manager tasked me with designing a simple application that would load up all the dashboards, rotate through them on a set timer, and refresh them regularily. 

At first I used a tool called *AutoIt* It was based off of *Visual Basic* and allows users to control windows, their mouse, and HTML fields. However the more I coded into it, the more unreliable it became. I made the decision then to use a combination of *C#*, *AutoIt for .Net*, and *Selenium* to make my new program. I used *C#* because it gave me the modularity of object oriented design and I had used it before. *AutoIt* was used again, this time as a plug in for *C#* because it was still the most reliable way to swap between windows, although I didn't use it any more beyond that. *Selenium* was a plug in for *C#* that hooked into *Google Chrome* and was able, to some extent, to access the HTML fields, in this case the username/password fields to log in to various dashboards. 

this application went through many iterations as dashboards were added, bugs were fixed, and features were planned. The switch from basic *AutoIt* to *C#* was a hesitant one, as we knew it would take some time to begin again from scratch, however as the bugs from *AutoIt* piled on, we knew we couldn't stay with it if we wanted the application to be reliable. The *C#* version was made late into my co-op term but finished a lot faster than the previous version thanks to my experience, and extra features were added to give my team control, such as pausing, skipping a dashboard, going back, and restarting the whole application. It was a challenging beast, but I'm glad I was able to leave my mark at *Absolute* with it.