---
title: Shared Understanding of the User Experience
subtitle: A Case Study of Collaboration Between Developers and Designers
summary: A Case Study of Collaboration Between Developers and Designers
date: "2015-10-30T00:00:00Z"
share: false
profile: false

# Optional external URL for project (replaces project detail page).
external_link:

# image:
#   preview_only: true
#   focal_point: Smart

---

Software engineering is inherently social profession and implementing software depends on collaboration between group members. Requirements do not necessarily originate from cutting edge high technology but from customer’s business needs, which brings a new set of problems to be solved—problems that are sociological, not technical. (Whitehead 2007; Fagerholm 2015; Fox, Sillito, & Maurer 2008; DeMarco & Lister 2013, p. 4) Additionally, the goal for many projects is to develop complex systems and design good user experience (UX). Responding to the changed demands for system quality attributes by incorporating design thinking, such as User-Centered Design (UCD), into iterative development is applicable to these circumstances but clear guidelines have not yet surfaced. (Ralph 2015; Fox, Sillito, & Maurer 2008; Kuusinen 2015; Magües, Castro, & Acuña 2016)

Software systems are built by people. The cross-functional interdisciplinary group is a heterogeneous set of people from different backgrounds and initially they may have different—atomistic instead of holistic—perspective of what is important in the system under development (Holtzblatt & Beyer 2016, p. 82; Gothelf & Seiden 2016, p. 41). Software system is more than the sum of its parts, it has emergent properties, so the group that is implementing the system has to form a shared understanding to achieve conceptual integrity and ultimately a satisfactory UX.

This study examines how developers and designers form a shared understanding of the UX with collaboration. In this study, collaboration is defined as communication and producing artifacts. Collaboration is needed for problem solving and information sharing. Communication and the artifacts they produce are means to form a shared understanding among the group. The group switches freely between the activities of exploring the problem and solution space throughout the process and produces artifacts to represent the design intent.

## Research questions

The objective of this study is to examine how UX is acknowledged in product development—how a group of people is able to solve relevant problems in terms of the system’s life cycle and evolution so that they achieve satisfactory UX. This study targets iterative development, and how well it is applied in the context of user needs and requirements elicitation. The central theme is collaboration between developers and designers: what are the methods (e.g. UCD, Agile), how are those applied in practice and how do they acknowledge the term "user experience".

Specifically, the focus of this study is collaborative software engineering, design thinking and UX. The main research problem addressed in this study is:
What kind of knowledge is shared between developers and designers?

**RQ1**: How do developers and designers form a shared understanding of the software system UX under development?

**RQ2**: What are the artifacts utilized in their collaboration?

# Results
The results are reported as follows: (1) Problem Conceptualization in Up-Front Design; (2) UX Confluences Between Developers and Designers; and (3) Artifacts Utilized in the Collaboration Between Developers and Designers. Section (1) will present the phase in the studied case where the UX was conceptualized. This section will describe the problem, users and their needs the participants identified and decided to converge to. This section will outline which quality attributes of the system are important for particular users (for example, learnability is important for the staff members). Sections (2) and (3) build upon the contents of section (1) will provide an answer to the research questions. The sections (2) and (3) will present the process followed and the artifacts utilized in the studied case as well as the phases within the process which are essential to achieve satisfactory UX.

## Problem Conceptualization in Up-Front Design
People’s needs are somewhat static. Therefore they remain largely unchanged throughout the system’s lifecycle. The employees who were part of this phase spent substantial time to understand the needs of their customers. Once they were accumulated enough knowledge about the needs, they had the necessary data to understand what kind of user experience they are able to design for, that is, how to provide satisfactory user experience meanwhile the customer fulfills her need by using the system. They do it by reflecting the user experience in the system’s quality attributes

## UX Confluences Between Developers and Designers
Three distinct phases within the process in the studied case were identified that are relevant for how developers and designers form shared understanding of the system UX under development: (1) Design Intent; (2) Design Handoff; and (3) Implementation. This chapter will decipher what happens in the process during these phases as well as what artifacts are used in collaboration between developers and designers during them. Some key artifacts are introduced here but a more in-depth analysis ir in the next chapter.

{{< figure src="/img/ux-confluences.svg" caption="UX Confluences Between Developers and Designers" >}}

It was found that developers and designers form shared understanding of the system UX under development by UX confluences illustrated in the figure. They are "meeting points" within the process, so to say, where developers and designers should collaborate in order to achieve satisfactory UX. Next, the confluences are briefly presented, followed by rationale why are they important for the shared understanding of the UX.

The first confluence is called "Design intent" and it happens at the start of an iterative cycle. The company in the studied case is design-oriented and the team involves customers in the process as much as possible. In this confluence, the team tries to reflect customers’ needs in the system’s quality attributes and they do this by simulating customers’ behaviour with paper prototypes. In this confluence, the team tries to include as many diverse opinions as possible to think about the problem and then to converge into single solution.

The second confluence is "Design handoff" and at this point, the team has written use cases for this cycle and conclude that the design is "finished". Design is represented as an interactive prototype in Zeplin tool.

"Implementation" is the last confluence and it is at the end of the cycle. But instead of releasing, the developers will do quality assurance first by peer reviews and by demoing both internally within the team and externally to some customers to receive feedback.

What makes these confluences important for UX? During "Design intent" lot of prioritizing happens. The team narrows down the scope and converge into solution which is represented as interactive prototype. This means that some of the essential knowledge about the UX is not documented anywhere and just gets lost. On the other hand, the developers should aim to represent the design intent with their implementation, not just the prototype and use cases they receive. And this is the key in this case. The developers are to a large extent responsible for the quality assurance. And, obviously, it’s the implementation, not the design intent the customers will use. And when the developers are part of "Design intent" confluence, they are able to draw the distinction between the core and peripheral functions of the solution so they can start writing automated tests for the core functionality instead of being unaware of the customers’ needs before they will provide feedback for the finished implementation. Because prioritizing and converging in this case means that they will implement some of the ideas now and others later which means that there will be changes. And by testing the core functionality, the developers are more prepared for changes and can also avoid the need for longer re-iteration but instead "build the thing right" at the first time.

But. Not every developer is design-oriented or interested in design and they are generally only part of the design handoff, which is perfectly fine but not necessarily good for the shared understanding of the UX.

