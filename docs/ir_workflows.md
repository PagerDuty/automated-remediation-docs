![Workflows](../assets/img/headers/AR_Workflows.png)

When an incident occurs, everyone wants to be able to call the expert, but your experts might be elsewhere—on vacation, commuting, or just unavailable. When that happens, you can use automation to borrow their expertise. Team SMEs (subject matter experts) who create automation are building artifacts for the rest of the team to use when they’re not around; their knowledge goes into some code instead of staying locked away in their heads. Encouraging your experts to automate the tasks they would use in response to incidents means they can be alerted less frequently, and more members of the team will have the tools they need to solve issues appropriately.

Your workflows for responding to incidents and unplanned work will contain some of the tasks that your regular, planned work incorporates. When you find parts of your workflow that can be automated, consider using automation to reduce mean time to recover (MTTR), alert fatigue, and toil.

When considering automating these workflows, we find many team automation projects follow these **five** phases:
![automationevolution image](../assets/img/automation_evolution.png)

You’ll still want to automate the tasks that happen the most often so your automation development is giving you the best return on investment. Determining what steps are valuable to automate might be challenging at first if your team doesn’t have a mature set of monitors and alerts to draw from. Your long-term alert and incident trends will lead you to the best candidates for automated remediation.

In this section, we’ll break down the incident response process into four sections:

1. **Team alerting and orchestration**: Automating the process of getting the right people in the right place at the right time.
1. **Triage and state analysis**: Collecting ecosystem and timeline data for the whole team
1. **Business communication**: Keeping stakeholders informed in a timely manner
1. **Automation of remediation**: Fixing the things that can be fixed automatically

If your team is just getting started with incident response, you’ll find more detailed documentation in our other Ops Guides, [Incident Response](https://response.pagerduty.com) and [Stakeholder Communications](https://stakeholders.pagerduty.com).

### Team Alerting and Orchestration
If your organization has been operating in a more traditional model with a Network Operations Center (NOC) staffed by technicians around the clock, the task of notifying and coordinating responders may fall to that team. When technical systems expand and become more complex, the job of finding and notifying responders can slow down as the NOC technicians search for the right teams, the on-call responder for those teams, and that person’s contact information.

Automating this part of the alert process is a first step toward reducing response and mobilization times. When an alert is triggered in your monitoring systems that needs intervention from a human responder, automation will link the alerting service to the owning team and that team’s on-call responder. To learn how to accomplish this in PagerDuty, visit this [Knowledge Base Checklist](https://pagerduty.influitive.com/forum/t/the-onboarding-checklist/1522) and follow the walkthrough for setting up responders, teams, schedules, and services.  

Once your responders have been alerted, they will need a place to communicate. This might be over SMS, phone, video conference, or a chat tool. The creation of a communications hub during an incident can also be automated so when the incident is started, all team members and potential responders will know where to go and how to access the communication channels. If your work platforms provide APIs, your incident response workflow can also include the creation of the channels or calls that your team will need to coordinate the incident response. Automating this step alleviates the risk that someone will have or be given the wrong information, delay their response time, or that the person creating the channel won’t have the appropriate account or permissions.

!!! tip
    See our knowledge base for more on how PagerDuty handles incidents.

Effectively deploying automation for team alerting requires some pre-work to clearly establish which teams own what services. With a human notifier, they might call around to various folks until they eventually find the right person, but they are wasting time and prolonging any service alerts. Creating a clear relationship between your responder teams and their services eliminates these delays, but this can take some time to set up properly.

When your team has completed a responder-to-service map, your next step could be “human-initiated automation, which might be a button or bot for your NOC to interact with to notify responders. Eventually, your response plan could be completely automated, allowing the error alerts themselves to notify your responders and run automation to create communication channels. You can get an idea of how PagerDuty implements this workflow in our knowledge base under [Mobilize a Coordinated Response](https://support.pagerduty.com/docs/mobilize-a-coordinated-response).

### Triage and State Analysis
Once your responders are online and investigating an incident, they will be collecting data and state information from services that are experiencing issues and general information about what is going on. This might be in the form of log files, status pages, monitoring reports, command output, or other data produced by your infrastructure.

During this step of your response process, there may also be external data that can be collected from the application ecosystem. Your automation might query a build or deploy pipeline to determine if there were any deploys prior to the alerts triggering. A list of recently updated packages on the systems running your services could be helpful in determining if a security update impacted your service. You might also want to add a report of past issues on the service that could be related to the current alert.

When any of your responders collect the same information, it makes sense to create some automation that will perform this task automatically for the benefit of everyone involved in the incident. These resources can be compiled to a central location or attached to the outage channel. This also helps establish timelines and informs next steps. If this information is already available when the responders log in, then triage can start even faster.

Automating tasks in this step of your incident response process gives your team a leg up in responding to common alerts and problems. Even for uncommon or novel incidents, automated triage can help responders narrow down potential causes and solutions by eliminating the first set of questions your responders might ask. It will also help newer members of your team be more effective if they don’t have to determine which machines to access, the preferred commands to run in your environment, or be knowledgeable in all the service dependencies.

### Business Communication
Hopefully your team is incorporating stakeholder updates in your incident response process. For incidents that impact externally facing services, keeping customers up to date is an important step in reputation management and customer service. For services that only impact internal users, keeping users updated is still important. This work can be distracting and challenging for teams to work into their incident response workflow, so we’ve already written some guidance for you in our other [Ops Guides](https://pagerduty.com/ops-guides).

Automating aspects of your stakeholder communications during an incident can alleviate the stress of these kinds of administrative and indirect tasks. Hopefully your team already has a communications position as part of your incident response. If you don’t, consider implementing one so your teams know there is a plan in place or person in charge of dealing with communications during an incident.

Your team can automate various pieces of your communications plan, including:

* Setting up automated reminders or timers to provide updates
* Sending an automatic update if there is no change to the status of the incident via a bot or other automated function
* Adding a function to your communications channel to send updates without having to log into specific accounts directly

Any of these automated actions will improve your team’s response practices and help you keep your users and stakeholders informed during an incident. Various tools exist to integrate with your workflow. Your team might already be using similar methods for what has been termed “ChatOps” — using shortcuts to send instructions to APIs and other tools. You could be halfway to automated communications already.

!!! tip
    How you keep stakeholders informed is an important component of your incident response. Learn more about how [Smartsheet](https://www.smartsheet.com/) evolved their communications in an episode of our podcast, [Page it to the Limit](https://www.pageittothelimit.com/incident-communications-with-alina-anderson/).


Streamlining communications with automation keeps all of your responders engaged in solving problems rather than dealing with answering questions. To further help your team manage communications, consider creating [customer liaisons](https://response.pagerduty.com/training/customer_liaison/) and [internal liaisons](https://response.pagerduty.com/training/internal_liaison/) to be responsible for updates.

### Automation of Remediation
As your team’s incident response process improves, you will likely find that some of the issues that arise require the same steps to recover from. As trends start to emerge, you can look at removing human intervention completely and automating the remediation phase of common alerts.

#### Self Healing Systems
You may have heard the term “self-healing” applied to technology systems. Self-healing refers to the ability of a system to discover errors and fix them without external intervention. At the most basic level, a self-healing environment will include three core components:

* The running service, application, or other component that is expected to be always-on
* A monitoring system that periodically checks the running system to determine whether or not it is performing as expected
* A set of software components that can restore the running service if the monitoring system finds it in a bad state

These three components come in a vast array of different structures and tools, so any one environment is unlikely to be exactly the same as another. Regardless of the specific tools employed, the goal is the same: to preserve the running services with as little external intervention — and potential downtime — as possible. No matter how fast and efficient your team’s incident response process is, it won’t be as fast as the system fixing itself.

Getting to this state of self-healing will include working through the steps in the diagram above. It’s unlikely that your team will have all the scripts and automation components at hand to fix all of the errors and alerts that arise on your systems, so it will require taking some time to learn the common alerts and fixes. From there, you and your team can discover the best path to automate those fixes to the extent that your team will trust them to run themselves. Eventually, you will have a library of components that can cure common issues without having to alert any of your team members.

!!! tip
    For a more in-depth intro to self-healing systems, see this article at [Mindtree](https://www.mindtree.com/blog/self-healing-it-systems-less-choice-more-mandatory-requirement#:~:text=In%20the%20IT%20world%2C%20self,restore%20itself%20to%20normal%20operation%E2%80%9D).


#### Runbooks
Before your systems are ready to begin healing themselves, there are some practices you can employ to make systems management easier that speeds up incident response. One of those is runbooks, which are a type of technical documentation dedicated to listing the steps to take to perform a specific task.

[Runbooks](https://www.pagerduty.com/resources/learn/what-is-a-runbook/) allow your team to preserve knowledge in a sharable format. The subject matter experts on your team can write runbooks for the systems they know best, and that knowledge is then available for your junior team members to use. They’re also helpful for legacy systems that were not designed with automation in mind. Early generations of  web server software was built to be manually configured—with heavy GUIs and no text configurations. Having runbooks for these systems is imperative to keeping them running while you still need them.

> “We have legacy systems from 10 years ago that aren’t as easy to automate as modern technologies. We have invested some time in automating our runbooks so we can move faster.”  - Andrew Rundle, Claranet, PagerDuty Summit 2020

The use of runbooks in your environment gives your team the advantage of having expert knowledge always available—even when the expert isn’t the on-call responder. By creating runbooks and other automation artifacts, your experts can document their best practices in a way that makes them safe to execute for the other members of your team. Depending on the toolset you use for your runbooks and other automation, you might also have access to sophisticated permissions and privilege management tools so your team can designate certain people to run certain tasks on certain systems. To see an example of this kind of tooling in action, check out [PagerDuty Rundeck](https://www.rundeck.com/).
