# Awesome devops ru
- [Введение]()
- [Что такое DevOps]()
- [Что он решает]()
- [Capabilities DevOps]()
  - [Техники]()
    - [Version control]()
    - [Continuous integration]()
    - [Deployment automation]()
    - [Trunk-based development]()
    - [Test automation]()
    - [Architecture]()
    - [Empowering teams to choose tools]()
    - [Test data management]()
    - [Shifting left on security]()
  - [Процессы]()
    - [Team experimentation]()
    - [Streamlining change approval]()
    - [Customer feedback]()
    - [Visibility of work in the value stream]()
    - [Working in small batches]()
  - [Измерения]()
    - [Monitoring systems to inform business decisions]()
    - [Proactive failure notification]()
    - [Work in process limits]()
    - [Visual management capabilities]()
  - [Культура]()
    - [Job satisfaction]()
    - [Westrum organizational culture]()
    - [Learning culture]()
- [ЧаВо]()
- [Доп. материалы]()

## Вводная про этот репозиторий

## DevOps (Что такое DevOps)
DevOps is an organizational and cultural movement that aims to increase software delivery velocity, improve service reliability, and build shared ownership among software stakeholders. Learn how to improve the speed, stability, availability, and security of your software delivery capability.

## DevOps capabilities (Что он решает)
Improve your performance and become a high performer by improving capabilities shown to drive performance improvements. DevOps Research and Assessment (DORA’s) six-year research program has validated a number of technical, process, measurement, and cultural capabilities to drive higher software delivery and organizational performance. Below, you’ll find links to articles on these capabilities, how to implement them, and how to overcome common obstacles.

![schema](schema.png)

### Техники
####  Version control
Системы контроля версий, такие как Git, Subversion, и Mercurial предоставляют системы для организации файлов и координировании их создания, обновления и удаления для команд. Эти системы плотно связаны с автоматизацией. Часто, автоматизация и continuous integration построены на этих системах. Для улучшения доставки ПО командам необходимо использовать контроль версий для исходного кода, тестов, скриптов деплоя, конфигураций инстраструктуры и приложений. В системе контроля версий коммманды должны иметь возможность запрашивать текущее (и историческое) состояние своих сред. СКВ также предлагает прямые преимущества, такие как аварийное восстановление и возможность аудита  
#### материал по теме:
 - git-book https://git-scm.com/book/ru/v2
---
#### Continuous integration
Software systems are complex, and an apparently simple, self-contained change to a single file can have unintended side effects on the overall system. When a large number of developers work on related systems, coordinating code updates is a hard problem, and changes from different developers can be incompatible.  
  
The practice of continuous integration (CI) was created to address these problems. CI follows the principle that if something takes a lot of time and energy, you should do it more often, forcing you to make it less painful. By creating rapid feedback loops and ensuring that developers work in small batches, CI enables teams to produce high quality software, to reduce the cost of ongoing software development and maintenance, and to increase the productivity of the teams.

##### материал по теме:
---
#### Deployment automation

Deployment automation is what enables you to deploy your software to testing and production environments with the push of a button. Automation is essential to reduce the risk of production deployments. It's also essential for providing fast feedback on the quality of your software by allowing teams to do comprehensive testing as soon as possible after changes.  
  
An automated deployment process has the following inputs:  
  
  - Packages created by the continuous integration (CI) process (these packages should be deployable to any environment, including production).
  - Scripts to configure the environment, deploy the packages, and perform a deployment test (sometimes known as a smoke test).
  - Environment-specific configuration information.
  
We recommend that you store the scripts and configuration information in [version contro](version-controll)l. Your deployment process should download the packages from an artifact repository (for example, Container Registry, Nexus, Artifactory, or your CI tool's built-in repository).  

The scripts usually perform the following tasks:

  - Prepare the target environment, perhaps by installing and configuring any necessary software, or by starting up a virtual host from a pre-prepared image in a cloud provider.
  - Deploy the packages.
  - Perform any deployment-related tasks such as running database migration scripts.
  - Perform any required configuration.
  - Perform a deployment test to make sure that any necessary external services are reachable, and that the system is functioning.

##### материал по теме:
---
#### Trunk-based development

  There are two main patterns for developer teams to work together using version control. One is to use feature branches, where either a developer or a group of developers create a branch usually from trunk (also known as master or mainline) and then work in isolation on that branch until the feature they are building is complete. When the team considers the feature ready to go, they merge the feature branch back to trunk.  
  
The second pattern is known as trunk-based development, where each developer divides their own work into small batches and merges that work into trunk at least once (and potentially several times) a day. The key difference between these approaches is scope. Feature branches typically involve multiple developers and take days or even weeks of work. In contrast, branches in trunk-based development typically last no more than a few hours, with many developers merging their individual changes into trunk frequently.
##### материал по теме:
---
#### Test automation

The key to building quality into software is getting fast feedback on the impact of changes. Traditionally, teams used manual code inspection and testing to verify systems' correctness. These inspections and tests occurred after "dev complete," and had the following drawbacks:
  - Manual regression testing is time-consuming to execute and expensive to perform, which makes it a bottleneck in the process. Software can't be released frequently and developers can't get quick feedback.
  - Manual tests and inspections are not reliable, because people are poor at repetitive tasks like manual regression tests, and it is hard to predict the impact of changes on a complex software system through inspection.
  - For systems that evolve over time, keeping test documentation up to date requires a considerable effort.  
To speed up feedback, the agile development community proposed a set of test automation techniques in the early 2000s. These techniques evolved and are now used in continuous delivery pipelines to provide quick developer feedback, reduce lead time for changes, reduce failure rate, and more.
##### материал по теме:
---
#### Architecture

Research from the DevOps Research and Assessment (DORA) team shows that architecture is an important predictor for achieving continuous delivery. Whether you're using Kubernetes or mainframes, your architecture enables teams to adopt practices that foster higher levels of software delivery performance.  
  
When teams adopt continuous delivery practices, adopting the following architectural practices drives successful outcomes:
  - Teams can make large-scale changes to the design of their systems without the permission of somebody outside the team or depending on other teams.
  - Teams are able to complete work without needing fine-grained communication and coordination with people outside the team.
  - Teams deploy and release their product or service on demand, independently of the services it depends on or of other services that depend on it.
  - Teams do most of their testing on demand, without requiring an integrated test environment.
  - Teams can deploy during normal business hours with negligible downtime.  

It's possible to achieve these outcomes with mainframe technologies. It's also possible to fail to achieve them even when using the latest, most trendy technologies. Many organizations invest lots of time and effort in adopting technologies, but fail to achieve critical software delivery outcomes, due to limitations imposed by architecture.  
  
When the architecture of the system is designed to enable teams to test, deploy, and change systems without dependencies on other teams, teams require little communication to get work done. In other words, both the architecture and the teams are loosely coupled.  
  
This connection between communication bandwidth and systems architecture was first discussed by Melvin Conway, who said, "organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations." To counteract tightly-coupled architectures and help support better communication patterns, teams and organizations can use the [Inverse Conway Maneuver](https://medium.com/better-practices/how-to-dissolve-communication-barriers-in-your-api-development-organization-3347179b4ecc), whereby team structures and patterns are designed to promote the expected architectural state. In this way, team communication patterns support and enforce the architectural patterns that are built.  
  
With a tightly coupled architecture, small changes can result in large-scale, cascading failures. As a result, anyone working in one part of the system must constantly coordinate with anyone else working in another part of the system, including navigating complex and bureaucratic change management processes.  
  
Microservices architectures are supposed to enable these outcomes, as should any true service-oriented architecture. In practice, many so-called service-oriented architectures don't permit testing and deploying services independently of each other, and thus won’t let teams achieve higher software delivery performance. It's essential to be strict about these outcomes when implementing service-oriented and microservice architectures.
##### материал по теме:
---
#### Empowering teams to choose tools

If you want to achieve higher software delivery performance and increase the job satisfaction of your technical staff, you should empower them to make informed choices about the tools and technologies they use to do their work. Research (PDF) from the DevOps Research and Assessment (DORA) team shows this contributes to better continuous delivery and higher software delivery performance. Teams that can choose their own tools are able to make these choices based on how they work and the tasks they need to perform. No one knows better than practitioners what they need to be effective, so it's not surprising that practitioner tool choice helps to drive better outcomes.  
  
Allowing teams to choose tools doesn't mean each team is given free rein to select any tool they want. Introducing technologies without any constraints can increase technical debt and fragility. However, when you combine tool choice with other capabilities—for example, a full view of the system, fast feedback, and the understanding that they are responsible for the code that they write—it helps your technologists make wise decisions about tools they will use and need to support. This pattern has been observed at companies like Google and Netflix, where a preferred technical stack is supported by default. But if a team feels strongly that a different tool or technology is best for their case, they are free to choose it. Teams understand that their choice comes with the understanding that they must also do the work of supporting this new technical stack.
##### материал по теме:
---
#### Test data management

[Automated testing](Test automation) is a key component of modern software delivery practices. The ability to execute a comprehensive set of unit, integration, and system tests is essential to verify that your app or service behaves as expected, and can be safely deployed to production. To ensure that your tests are validating realistic scenarios, it's critical to supply the tests with realistic data.  
  
Test data is important because it's required by all kinds of tests throughout your test suite, including manual and automated tests. Good test data lets you validate common or high value user journeys, test for edge cases, reproduce defects, and simulate errors.  
  
However, it's hard to use and manage test data effectively. Over-reliance on data defined outside of test scope can make your tests brittle and increase maintenance costs. Dependencies on external data sources can introduce delays and impact test performance. Copying production data introduces risk because it might contain sensitive information. To address these challenges, you need to manage your test data carefully and strategically.
##### материал по теме:
---
#### Shifting left on security

Security is everyone's responsibility. The 2016 State of DevOps Report (PDF) research shows that high-performing teams spend 50 percent less time remediating security issues than low-performing teams. By better integrating information security (InfoSec) objectives into daily work, teams can achieve higher levels of software delivery performance and build more secure systems. This idea is also known as shifting left, because concerns, including security concerns, are addressed earlier in the software development lifecycle (that is, left in a left-to-right schedule diagram).  
  
In software development, there are at least these four activities: design, develop, test, and release. In a traditional software development cycle, testing (including security testing), happens after development is complete. This typically means that a team discovers significant problems, including architectural flaws, that are expensive to fix.  
  
After defects are discovered, developers must then find the contributing factors and how to fix them. In complex production systems, it's not usually a single cause; instead, it's often a series of factors that interact to cause a defect. Defects involving security, performance, and availability are expensive and time-consuming to remedy; they often require architectural changes. The time required to find the defect, develop a solution, and fully test the fix are unpredictable. This can further push out delivery dates.  
  
Continuous delivery borrows from lean thinking the concept of building quality into the product throughout the process. As W. Edwards Deming says in his Fourteen Points for the Transformation of Management, "Cease dependence on inspection to achieve quality. Eliminate the need for inspection on a mass basis by building quality into the product in the first place." In this model, rather than taking a purely phased approach, developers work with security and testing experts to design and deliver work in small batches throughout the product lifecycle.  
  
Research from DevOps Research and Assessment (DORA) (PDF) shows that teams can achieve better outcomes by making security a part of everyone's daily work instead of testing for security concerns at the end of the process. This means integrating security testing and controls into the daily work of development, QA, and operations. Ideally, much of this work can be automated and put into your deployment pipeline. By automating these activities, you can generate evidence on demand to demonstrate that your controls are operating effectively; this information is useful to auditors, assessors, and anyone else working in the value stream.
##### материал по теме:
---
### Процессы
#### Team experimentation

##### материал по теме:
---
#### Streamlining change approval

##### материал по теме:
---
#### Customer feedback

##### материал по теме:
#### Visibility of work in the value stream

##### материал по теме:
---
#### Working in small batches

##### материал по теме:
---
### Измерения
#### Monitoring systems to inform business decisions

##### материал по теме:
---
#### Proactive failure notification

##### материал по теме:
---
#### Work in process limits

##### материал по теме:
#### Visual management capabilities

##### материал по теме:
---
### Культура
#### Job satisfaction

##### материал по теме:
---
#### Westrum organizational culture

##### материал по теме:
#### Learning culture

##### материал по теме:
---
### Часто задаваемые вопросы
### Доп. материалы
(Материал ненашедший себе места в вышеописанных статьях)
