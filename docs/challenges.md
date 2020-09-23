---
cover: assets/img/headers/AutoRemediation_Challenges.png
description: The introduction of automation comes with some challenges on many teams.
---
![Challenges](../assets/img/headers/AutoRemediation_Challenges.png)

Automation has quite a history, starting in the early days of the Industrial Revolution. When weavers and textile workers were faced with the realities of new machinery, they worried that their hard-won skills and craftsmanship would no longer be needed, and some banded together to destroy machines. We still use their name, Luddites, to refer to people who are reluctant to use or are hesitant around technology. For more than 200 years, processes and human work have become increasingly automated in many industries, from electrical power generating, to aerospace, to shipping, to IT.

Making use of automation creates its own set of challenges. Researchers in human behavior, human-computer interaction, neuropsychology and other intersecting fields have been looking at the effects of automation on workers for decades.

While not all the findings in these areas are applicable to IT, there are a few that we might find interesting; in particular, a set of “ironies” presented by Lisanne Bainbridge in a 1983 paper entitled *Ironies of Automation*. This paper is short, only a few pages, but it has had a significant impact on the field of automation research. Automation research often focuses on industries in which failures create spectacular or catastrophic results, such as aviation, power generation, or healthcare. The downstream learnings can help us work with the automation in our systems as well.

The *Ironies*, as presented by Bainbridge, focus on the impact automation has on the behavior and readiness of human operators. Two in particular are related to how the operator feels about their engagement with their work. In a heavily automated system, a human operator may not feel ownership of the performance of the system. Operator detachment from many of the activities the system performs also contributes to a question of the value of their work. An operator watching automated processes for feedback can find that work incredibly boring, but the level of responsibility on that operator if they are needed by an anomalous situation creates an odd dichotomy. This also contributes to a problematic balance between boredom and vigilance that is still being studied, especially in the field of autonomous vehicles.

One place that might impact your team’s overall performance after deploying automation at scale is the potential degradation of skill of the operator. Bainbridge discusses this a bit, but a follow-up paper by Barry Strauch in 2017, *Ironies of Automation, Still Unresolved After All These Years*, investigates in more depth, especially in relation to aviation. Operators stepping into an incident in the middle of some automated action may not have the knowledge required to solve the problem or may not have a full accounting of what the automation has already done. In the worst cases, the operators may have never had sufficient training to repair a system that has had some kind of automation failure because they trained only with the automation in place.

When we look to apply this foundational idea to IT automation, we might find that operators become rusty over time when they aren’t constantly exposed to the system. We ask the folks responding to an incident to be more knowledgeable about the system than they were before the automation—they will only be stepping in when the incident is more complex than the automation can take care of. At PagerDuty, senior staff may be well prepared for this kind of lifecycle, but it presents new challenges when training junior staff.

Catastrophic failures attributed to automation, as they get reported in the press, also make our automation tasks more difficult from an organizational standpoint. When folks express reluctance or trepidation around automation, it’s often down to several common concerns:

* Fear of the automation creating a larger problem
* Fear of the automation just being wrong or doing nothing
* Fear of losing their job

Any unplanned work on a system might cause more errors or have no positive effect on an alert, whether a human is responding or the system has an automated response. While no effect is better than increasing the scope of a problem, it also delays the time to recover from the incident.

Part of keeping the automation “trustworthy” is maintaining a narrow functional scope. This contains the potential blast radius if anything does go wrong. The automation we build should focus on one particular function and should report back if something doesn’t work as expected.

Think about our earlier example of installing a software package. There are a couple of checks we’d want to employ inside the automation, such as not continuing if the package can’t be accessed. We also want to keep the focus narrow; the installation of the package doesn’t necessarily mean we also want the service started immediately on all platforms, so we might leave that out of the automation component. Similarly for tasks like clearing disk space. Our human responders might first log into the system and double check that the “usual” culprit is responsible for the issue before taking any action. Our automation should also run these commands and act accordingly.

Job loss or recategorization is a real issue in organizations applying automation to many parts of their workflow. As with increased automation in many industries, the types of jobs that are available will change. If your team chooses to use more cloud-based infrastructure via automation and APIs, you’ll have less need for someone on your team to spend their day performing tasks like imaging machines or building virtual hosts. These are repetitive tasks more [aptly] performed by automation; we want to save the human time for solving problems. So part of your automation journey will likely require you to spend some time and attention on helping some of your staff retrain and learn new tasks.

It’s unlikely, as you automate, that you’ll have less work to do. Once organizations start reaping the benefits of faster time to market and higher quality output, their ability to innovate also increases. More innovation creates more projects for your technical teams to work on as well.
