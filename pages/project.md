---
layout: default
title: 8420 Project
description: CYBR 8420 Software Assurance Project
---

# Team Semester Project

This class strives to encourage learning by doing and making a real difference in the practice of building software. To turn this spirit into reality, you will work on a semester-long project with an open-source software project. Five students will select a unique open-source software project and examine opportunities for security-related improvements.

The project will have the following deliverables:

1. **Project Proposal**: A markdown report that describes the following:
  * Choose an open-source software project. From here on, I will refer to it as "software."
  * Describe a fictional operational environment (e.g., home, office, enterprise, bank, government, etc.) for your software.
  	- Describe threats (at least five) in this environment. If there are none or very few, then re-evaluate your software or environment selection.
    - Develop a list of security features (at least five) in the software that users will expect from the software to counter the threats.
  * Describe the open-source project (What is it?, Contributors, Activity, Use, Popularity, Languages used, platform, documentation sources, etc.)
  * [Discuss License, procedures for making contributions, and contributor agreements](https://opensource.guide/how-to-contribute/#orienting-yourself-to-a-new-project)
  * Summary of security-related history for the software (E.g., known vulnerabilities, security-related engineering decisions, security feature additions/removal, etc.)
  * Include a link to your team GitHub repository that shows your task assignments and collaborations to finish this deliverable.
    - [Use Github Project Boards to track your tasks with To do, In progress, and Done columns in a basic kanban style](https://docs.github.com/en/github/managing-your-work-on-github/creating-a-project-board)
  	- Use Github issues to track task assignments, discussions, and related commits. [Add issues to the project board](https://docs.github.com/en/github/managing-your-work-on-github/adding-issues-and-pull-requests-to-a-project-board)
  * Include a summary of your team reflection meeting. What issues occurred? What did you plan to change moving forward?
1. **Requirements for Software Security Engineering**: A markdown report that describes the following:
  * Identify five data flows (input-processing-output) through the software protected by the security features identified in the project proposal. Develop a separate use-case diagram for each data flow.
  * Derive security requirements for the use-cases using misuse-case diagrams. Misuse-cases should exhibit multiple rounds of refinement to refine security requirements.
  * Assess the alignment of the identified security requirements with advertised features of the software—review OSS project documentation and codebase to support your observations.
  * Review OSS project documentation for security-related configuration and unsafe installation practices. Summarize your observations.
  * Include a link to your team GitHub repository that shows your task assignments and collaborations to finish this deliverable.
  * Include a summary of your team reflection meeting. What issues occurred? What did you plan to change moving forward?
1. **Assurance Cases Software Security Engineering**: A markdown report that includes the following:
  * Identify five assurance claims about critical properties of the software. Focus on the outcomes you are interested in, i.e., What are the Goals/Claims about security to be proven? Operational tasks may not focus on outcomes. Security requirements from the last assignment should help.
  * Prepare an argument in support of the claims that would be convincing in your fictional environment. Document this argument and the needed evidence using a separate assurance case for each of the five claims.
  * Assess the alignment of the planned evidence with that available (or can be made available) from the OSS project. Highlight the gaps.
  * Include a link to your team GitHub repository that shows your task assignments and collaborations to finish this deliverable.
  * Include a summary of your team reflection meeting. What issues occurred? What did you plan to change moving forward?
1. **Designing for Software Security Engineering**: A markdown report that describes the following:
  * Develop threat models for critical data-flows through the software. Misuse and assurance cases will provide starting points for examination. Include threat model diagrams and threat analysis. For details see [slides](https://robinagandhi.github.io/swa/slides/lecture-4/design-for-software-se.html#66).
  * Using threat model analysis, review OSS project for design related issues. Summarize your observations.
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
  * Include a summary of your team reflection meeting. What issues occurred? What did you plan to change moving forward?
1. **Code analysis for Software Security Engineering**: A markdown report that describes the following:
  * Your code review strategy
  * Findings from manual code review of critical security functions identified in misuse cases, assurance cases, and threat models.
  * Findings from automated code scanning (if available). Include links to full reports.
  * Summary of key findings from manual and automated scanning. This summary may include categorization, mappings to CWEs, CAPECs, Risk Levels, etc. If the number of raw tool findings is large, analyze a smaller sample of findings.
  * Links to any pull requests, issues, discussion, etc. from the team to the original project and any follow-up interactions.
  * Include a link to your team GitHub repository that shows your task assignments and collaborations to finish this deliverable.
  * Include a summary of your team reflection meeting. What issues occurred? What did you plan to change moving forward?
1. **Class Presentation**: 10-15 minute recorded video presentation that highlights the following:
  * Project description
  * Gaps in security requirements and design of the original project
  * Assurance claims
  * Findings from manual code review and automated software scanning
  * Any contributions to the original project (documentation, design changes, code changes, communications)

## Project Hall of Fame
* [List of successful contributions to OSS projects from student teams](https://robinagandhi.github.io/swa/pages/halloffame.html)  

## Project Inspiration
* [Github guide for contributing to Open Source Projects](https://opensource.guide/how-to-contribute)
* [Openhub](https://www.openhub.net) by Synopsys/Black Duck Software
* Github [search](https://github.com/search) and [trends](https://github.com/trending).
* [Code Triage](https://www.codetriage.com). Open source projects on GitHub that need your help.
* Some blogs to consider. [blog 1](http://blog.teamtreehouse.com/getting-involved-open-source-projects), [blog 2](https://help.github.com/articles/where-can-i-find-open-source-projects-to-work-on/), [blog 3](http://www.firsttimersonly.com)

## Projects to **Avoid**
* In-active projects (no recent contributions, no activity on forums, lack of wiki or documentation)
* Old vulnerable project versions
* Mobile Apps. We have other classes that do that.
* Projects with languages that do not have a lot of tool support
* Project with little or no security requirements. As surprising as it may sound, not all software has security needs!
* Projects not accepting contributions

## Project Deadlines*

1. Teams formed &ndash; **September 4th**
1. Project Proposal &ndash; **September 11th**
1. Requirements for Software Security Engineering &ndash; **September 25th**
1. Assurance Cases Software Security Engineering &ndash; **October 9th**
1. Designing for Software Security Engineering &ndash; **November 6th**
1. Code analysis for Software Security Engineering &ndash; **November 20th**
1. Class presentations &ndash; **December 4th**

\* Dates subject to changes

## Teams Project for Fall 2020
TBD

## Past Teams Project Repositories

While these can act as examples, there is no guarantee that they did it right! They may also be following different assignment instructions.

* [Teams 2019](https://robinagandhi.github.io/swa/slides/teams-2019/teams.html)
* [Teams 2018](https://robinagandhi.github.io/swa/slides/teams-2018/teams.html)
* [Teams 2017](https://robinagandhi.github.io/swa/slides/teams-2017/teams.html)
* [Teams 2016](https://robinagandhi.github.io/swa/slides/teams-2016/teams.html)
