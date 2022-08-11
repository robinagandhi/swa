---
layout: default
title: 8420 Project
description: CYBR 8420 Software Assurance Project
---

# Team Semester Project

You might ask why have a team project? To that I have to say that today we build and analyze things that are so complex that no one person can fully make or comprehend them —naturally, engineering activities to manage complexity are team-based—for example, open-source software development. Team members could be in different time zones, have competing priorities, and different skill levels. Experiencing such teamwork is essential for a course on software assurance. So, we will form five-person teams that will work together on a class project.

This class strives to encourage learning by doing and making a real difference in the practice of building software. To turn this spirit into reality, you will work on a semester-long project with an open-source software project. Each team will select a unique open-source software project and examine opportunities for security-related improvements.

The project will have the following major deliverables. Not surprisingly, they coincide with the major topics in the course.

1. Project Proposal
1. Requirements for Software Security Engineering
1. Assurance Cases Software Security Engineering
1. Designing for Software Security Engineering
1. Code analysis for Software Security Engineering
1. Recorded Presentation

## Project Inspiration
If you have never worked with open source project communities, your heart is probably racing at this time. Don't worry. They are not that scary. Also, we will have the right preparation in the course that will allow you to have purposeful interactions with these communities. For now, I want you to read through these blogs to understand what it is like to engage with an open source project: [blog 1](https://opensource.guide/how-to-contribute), [blog 2](http://blog.teamtreehouse.com/getting-involved-open-source-projects), [blog 3](http://www.firsttimersonly.com).

These blogs probably helped address some of your anxiety. Another source of anxiety can be related to what open source project to select. As you think about joining a team, use the links below to explore impactful open source projects and have some ideas about the projects you want to engage with.

* [Github Guide for finding an Open Source Project to work on](https://help.github.com/articles/where-can-i-find-open-source-projects-to-work-on/)  

Openhub has a lot of meta-information about open source projects that can help you better explore and understand your selection. Github search and Code Triage are also good resources to find projects.

* [Openhub](https://www.openhub.net) by Synopsys/Black Duck Software
* Github [trends](https://github.com/trending).
* [Code Triage](https://www.codetriage.com). Open source projects on GitHub that need your help.

## Projects to **Avoid**
The software assurance methods in this course apply quite broadly. Codebases based on C, C++ and Java generally have a better support of free tools for security analysis. But just the language used in the codebase should not limit your choices. What you should avoid are projects that fall into the categories below:
* In-active projects (no recent contributions, no activity on forums, lack of wiki or documentation)
* Old vulnerable project versions
* Mobile Apps. We have other classes that do that.
* Projects with less-widely used languages that lack tool support for automated analysis
* Project with little or no security requirements. As surprising as it may sound, not all software has security needs!
* Projects not accepting contributions

As you form your teams, prior familiarity with languages or platforms may play in to your choice. But keep in mind that Software Security Assessors are often called in to analyze the security of software that is built using languages that they are not familiar with.

## Project Hall of Fame
To give you some motivation, here are teams from prior semesters that have engaged with the communities of their selected open source projects. Your team should aspire to get listed in this repo. After all, this course made it to the Arctic Code Vault!
* [List of successful contributions to OSS projects from student teams](https://robinagandhi.github.io/swa/pages/halloffame.html)  

## Past Teams Project Repositories
The deliverables from the class project are posted in a public repository. You can find the artifacts from prior semester teams below. While these can act as examples, there is no guarantee that they did it right! They may also be following different assignment instructions.


* [Teams 2021](https://robinagandhi.github.io/swa/slides/teams-2021/teams.html)
* [Teams 2020](https://robinagandhi.github.io/swa/slides/teams-2020/teams.html)
* [Teams 2019](https://robinagandhi.github.io/swa/slides/teams-2019/teams.html)
* [Teams 2018](https://robinagandhi.github.io/swa/slides/teams-2018/teams.html)
* [Teams 2017](https://robinagandhi.github.io/swa/slides/teams-2017/teams.html)
* [Teams 2016](https://robinagandhi.github.io/swa/slides/teams-2016/teams.html)

## Teams Project for Fall 2022

* Coming soon!

## Project Grading
* The project accounts for 40% of the total course grade.
* 20% of your project grade will be based on peer feedback throughout the semester and attendance at weekly project meetings. So strive to be an active contributor and volunteer for project tasks in your teams. Avoid being a [social loafer](https://www.verywellmind.com/what-is-social-loafing-2795883) at all costs!


<!--
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
  * Any contributions to the original project (documentation, design changes, code changes, communications)-->
