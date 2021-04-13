
![Use Cases](/assets/images/headers/AR_UseCases.png)

With the spread of DevOps as a framework for overhauling IT workloads and the increasing popularity of public clouds, the automation of various work has become key to a successful digital transformation. Cloud platforms offer opportunities for flexibility and developer autonomy, along with complexity, scale, and speed that is difficult to maintain with manual processes.  As more and more technology teams find themselves at the intersection of traditional, manual practices and modern, API-driven practices, it is necessary to not only build the skills needed for automation, but also to embrace the mindset that automation is a benefit to the overall health of the systems.

Automation for IT processes has many of the same goals as automation does in any other industry. We strive to deliver consistent, reliable results, no matter who the practitioner is, or which machine or service is involved. Automating repetitive, low-value tasks reduces toil and allows people to perform higher-value, more rewarding work.

Many teams will find that a variety of tools will help them alleviate the issues related to incorrect documentation, mistakes, and toil that plague teams using manual processes. As systems have increased in number and complexity, the need for automation has also increased. Safe, reliable automation gives IT teams a place to abstract their processes so they don’t have to be memorized or exposed to the risk of manual work. Manual workflows like cutting-and-pasting carry heavy risks for mistakes. Outdated documentation can slow down task completion or cause errors on its own. And the toil of repetitive, manual tasks can have negative impacts on employee productivity, satisfaction, and engagement.

Automation can be applied to many facets of a technical project, from building and testing software, to creating the runtime environments, to responding to error conditions and incidents. Various stages of the software development lifecycle include tasks that are candidates for automation, as well as tasks that are done repeatedly that require little or no input from humans and have consistent end states. Creating and maintaining automation, whether in the form of scripts or libraries or other components, comes with a cost, so we want to find the tasks that will have the most impact on team resources when they are performed by the automation.

When we perform tasks or otherwise make changes to any part of a system, there are some goals we should keep in mind. In *Architecting for Scale*, Lee Atchison has categorized these goals as the following:

* The procedure should be testable
* The procedure should be flexible and implemented for future improvements
* The procedure should be reviewable by someone else as a check
* The procedure should be put under version control
* The procedure should be applicable to related resources, “one-off” changes should be discouraged, and it should be applied to all related resources in the same way
* The procedure should be repeatable and auditable

While we can potentially satisfy these goals with manual processes, automation codifies the tasks into repeatable processes and ensures they are performed the same way each time they are needed.

If we keep these goals in mind when we are thinking about every change that will be made to our systems, we establish practices that prioritize the reliability of our systems in all phases of the life cycle, including when we are responding to incidents. Let’s look at some of the ways your team is already using automation.

### Build and Deploy
Building and packaging software applications is inherently a form of automation. Different types of languages and runtimes have different requirements, but the tasks are well defined and repetitive. Whether an application requires compilation and linking or the organizing of external dependencies, the developer can employ automation to perform these tasks reliably. Application builds can be run as part of a pipeline of processes where the entire workflow is created and stored for repeated use, ensuring that steps aren’t forgotten or run incorrectly.

For technical and organizational reasons, automated deployments are not as ubiquitous as automated builds.

For example, organizations utilizing rigid change management programs are reluctant to authorize automated deployments of new builds to production, though they may deploy into shared development environments or a staging environment for testing and integration purposes. Even in loosely coupled environments, services may have a dependency on changes to data schemas that require more manual intervention, such as a full backup to be taken before the update. Automated deployment often comes at the end of a long modernization journey, after teams have successfully changed a number of other development practices. This includes small, incremental changes and employing methods like feature flagging and dark launching.

Automated builds and deployments are often combined into a set of practices known as continuous integration and continuous deployment, or CI/CD. The challenges presented by automated deployments have expanded the definition of CI/CD to also be defined as continuous delivery. Delivery places the software in a repository for later use, while deployment installs the software into a specific environment. Tools that perform CI/CD tasks help teams create pipelines or workflows to build, test, package, and deploy or deliver software.

Automated deployment isn’t possible for all software. Software that wasn’t designed for automated installs or upgrades might require the acceptance of a license agreement with no option to pre-populate metadata, settings file, or registry entry. It might still require the installer to make selections manually without the aid of a pre-populated inventory or other aid. These installs fail the goal of repeatability and are incredibly difficult to reproduce effectively, making them harder to repair or rebuild when needed.

### Software Testing
Automated testing is a different topic all on its own. It’s beyond our scope in this guide however, it’s part of the application lifecycle, so we’ve included it here for completeness.

Various programming languages and frameworks have specific testing paradigms and tooling, but overall, manual testing is a tedious process. With the increasing complexity and volume of software components used in many organizations, manual testing is simply no longer sustainable or time efficient.

Automated testing can start from the first time a developer saves a file in their text editor or when the editor itself initiates a syntax checker or linter. As a change proceeds through the build process, more tests can be performed. This includes unit tests and integration tests, depending on the features or services impacted by the change. There’s zero chance that a test step will be forgotten if they are all automated.

### Environment Provisioning
The building and maintenance of environments on full systems, virtualized systems, and containers is another area that has been highly automated. For new projects, no one will ever put a warm coat on, walk into a highly air-conditioned data center, roll a “crash cart” with keyboard and mouse up to a rack of servers, install the OS on them from a CD or DVD, and click through options and package selections manually like we did 10 or 15 years ago.

Building infrastructure is susceptible to the challenges we outlined in the introduction. Documentation of the process will rapidly become out of date, mistakes are easy to make, and the repeated tasks required to build out a large environment are tiresome. But automation for the base layers beneath your applications is key to maintaining large-scale production environments and for the maintenance of smaller environments.

Automating the provisioning of infrastructure ensures that:

* All the systems in the environment are identical, even if they aren’t built at the same time.
* All the systems in the environment will have all the components required in the correct versions.
* The systems can be rebuilt to the correct specifications in case of disaster or catastrophic loss.

When services run in cloud or Infrastructure as a Service environments, the APIs provided by the vendor also give teams a strong starting point for automated management of services and systems. Tools like [HashiCorp’s Terraform](https://www.terraform.io/), combined with configuration management tools like Chef, Puppet, or Ansible, provide an automated path from first provisioning through preparation for services to actively managing and maintaining services. This path for making planned changes is fairly well understood, and also has a set of testing tools like [Test Kitchen](https://kitchen.ci/) and [ansible-test](https://docs.ansible.com/ansible/latest/dev_guide/testing.html) to help achieve our goals for testing changes before they are applied to our environments.
