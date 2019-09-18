---
layout: default
title: 8420 Project
description: CYBR 8420 Software Assurance Project
---

# Team Semester Project

This class strives to encourage learning by doing and making a real difference in the practice of building software. To turn this spirit into reality, you will work on a semester-long project with an open source software project. A group of three to four students will select a unique open source software project and contribute security-related improvements.

The project will have the following deliverables:

1. **Project Proposal**: 2-3 page markdown document that describes the following:
  * An open-source software project your team has chosen. From here on, it will be referred to as "software".
  * An assumed/hypothetical operational environment (e.g., home, office, enterprise, bank, government, etc.) where the users will expect security functionality from the software in its intended use.
  * What are the security needs of users from this software in its intended threat environment ? If there are none or very few, then re-evaluate your selection.
  * Develop a list of security features in the software. Again, if there are none or very few, then re-evaluate your choice.
  * Motivation for selecting this project
  * Open source project description (What is it?, Contributors, Activity, Use, Popularity, Languages used, platform, documentation sources, etc.)
  * [Discuss License, procedures for making contributions, and contributor agreements](https://opensource.guide/how-to-contribute/#orienting-yourself-to-a-new-project)
  * Summary of security-related history for the software (E.g., known vulnerabilities, security-related engineering decisions, security feature additions/removal, etc. )
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
     - [Github Project Boards](https://help.github.com/articles/about-project-boards/)
     - [Kanban boards](https://en.wikipedia.org/wiki/Kanban_board)
1. **Requirements for Software Security Engineering**: A markdown report that describes the following:
  * Identify five essential data flows (source-transformations-sink) through the software. Develop use-cases diagrams related to these data flows.
    * Make sure you have a back story in your operational environment. Where is this system being used? What is its criticality? Who are the stakeholders?
    * Ideally, the dataflows need to be spread across different external interactors (humans or systems) of your software. Once different external interactors have been identified, the use cases can focus on the most sensitive features used by the external interactor.
  * Derive security requirements for the use cases using misuse case diagrams. Briefly describe the analysis in each misuse case diagram.
    * The misusers should be contextualized in your environment of operation and relevant to the dataflows identified above. Use names that help the reader understand their motives, resources, attack of choice, and the available access to the system to carry out their attack.
  * Assess alignment of security requirements with advertised features of the software. Review OSS project documentation and codebase to support your observations.
  * Review OSS project documentation for security-related configuration and installation issues. Summarize your observations.
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
1. **Assurance Cases Software Security Engineering**: A markdown report that includes the following:
  * Using security requirements, identify five assurance claims
  * Prepare an argument in support of the claims that would be convincing in your assumed/hypothetical operational environment. Document this argument and the needed evidence using an assurance case for each of the claims.
  * Assess the alignment of the planned evidence with that available (or can be made available) from the OSS project. Highlight the gaps.
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
1. **Designing for Software Security Engineering**: A markdown report that describes the following:
  * Develop threat models for critical data-flows through the software. Misuse and assurance cases will provide starting points for examination. Include threat model diagrams and threat analysis.
  * Using threat model analysis, review OSS project for design related issues. Summarize your observations.
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
1. **Code analysis for Software Security Engineering**: A markdown report that describes the following:
  * Code review strategy
  * Findings from manual code review of critical security functions identified in misuse cases, assurance cases and threat models.
  * Findings from automated code scanning (if available). Include links to full reports.
  * Summary of key findings from manual and/or automated scanning. This summary may include categorization, mappings to CWEs, CAPECs, Risk Levels, etc.
  * Links to any pull requests, issues, discussion, etc. from the team to the original project and any follow-up interactions.
  * Link to your team GitHub repository that shows your internal project task assignments and collaborations to finish this task.
1. **Class Presentation**: 10-minute class presentation that highlights the following:
  * Project description
  * Gaps in security requirements and design of the original project
  * Assurance claims
  * Findings from manual code review and automated software scanning
  * Any contributions to the original project (documentation, design changes, code changes, communications)

## Project Hall of Fame
* [List of successful contributions to OSS projects from student teams](https://robinagandhi.github.io/swa/pages/halloffame.html)  

## Project Inspiration
* [Github guide for contributing to Open Source Projects](https://opensource.guide/how-to-contribute)
* [Openhub](https://www.openhub.net) by Black Duck Software
* Github [search](https://github.com/search) and [trends](https://github.com/trending).
* DHS SWAMP listing for [public software packages](https://www.mir-swamp.org/#packages/public).
* [Code Triage](https://www.codetriage.com)
* Some blogs to consider. [blog 1](http://blog.teamtreehouse.com/getting-involved-open-source-projects), [blog 2](https://help.github.com/articles/where-can-i-find-open-source-projects-to-work-on/), [blog 3](http://www.firsttimersonly.com)

## Projects to **Avoid**
* In-active projects (no recent contributions, no activity on forums, lack of wiki or documentation)
* Old vulnerable project versions
* Mobile Apps
* Projects with languages that do not have a lot of tool support
* Project with little or no security requirements. As surprising as it may sound, not all software has security needs!
* Projects not accepting contributions

## Project Deadlines*

1. Teams formed &ndash; **September 4th, 2019**
1. Project Proposal &ndash; **September 11, 2019**
1. Requirements for Software Security Engineering &ndash; **September 25th, 2019.**
1. Assurance Cases Software Security Engineering &ndash; **October 9th, 2019.**
1. Designing for Software Security Engineering &ndash; **November 6th, 2019.**
1. Code analysis for Software Security Engineering &ndash; **November 20, 2019.**
1. Class presentations &ndash; **December 4th, 2019.**

\* All dates are subject to change as the course progresses

## Teams Project for Fall 2019
[Teams 2019](https://robinagandhi.github.io/swa/slides/teams-2019/teams.html)

## Past Teams

## Teams Project for Fall 2018
[Teams 2018](https://robinagandhi.github.io/swa/slides/teams-2018/teams.html)

## Teams Project for Fall 2017
[Teams 2017](https://robinagandhi.github.io/swa/slides/teams-2017/teams.html)

### Teams Project for Fall 2016
[Teams 2016](https://robinagandhi.github.io/swa/slides/teams-2016/teams.html)
