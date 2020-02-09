---
title: Stdy QRp
summary: Helping students to find peers for a study group
date: "2019-05-10T00:00:00Z"
share: false
profile: false
type: project

# Optional external URL for project (replaces project detail page).
external_link:

image:
  preview_only: true
  focal_point: Smart

---

Throughout their studies, students may encounter problems in their courses where they need help from their teachers or from their peers but lectures and other contact teaching sessions can be at unsuitable times. Even though many courses have their own communication channels for seeking help, there are situations where the subjective experience of learning is better when done in collaboration with peers. This brings us to the three things needed for successfully studying together: shared location, time and a common subject. In Stdy QRp, we evaluate how do we make it easy for students to arrange and participate in impromptu study groups and present an application which combines space, time and problem into creating an ad hoc study group. Our testing concentrated on determining the best way for creator to communicate the subject of the group to other students in order to reach and match with as many potential peers as possible. Users were asked to use the application with two different interfaces and messages, and then fill in a survey about their experience. It was found that for the group creator, it is easier to express their problem in their own words, but group participants may find messages with predetermined and more generic subjects easier to understand and thus they are potentially more likely to participate in these study groups. Application is [here](http://qrp.herokuapp.com/)

In detail, we investigate _the effort to find peers at the ‘right time’ by creating an impromptu study group and how likely are people to join the group_.

# Needfinding
Our study followed human-centered design process (Norman, 2013, Ch. 6): _"Make observations on the intended target population, generate ideas, produce prototypes and test them."_

Stakeholder map represents all the people involved and is an additional verification that the student is at the core of the study, and thus students are the population we interviewed and the persona we based the PACT analysis.

{{< figure src="/img/stdy-qrp-stakeholder-map.svg" caption="Stakeholder map of people who gain or deliver value" >}}

***
**Person**: Student, 20-50 years
***

 - University level degree
 - She can be either a new student from lower education or someone with experience from previous degrees or work etc.
 - Most likely able to communicate in English
 - Studies full-time or part-time while working, taking care of children for example

***
**Activity**: Learning & Information Seeking ⇔ Information Giving
***

Based on the initial observation, people study couple of hours and take a break hourly. Lot of people are also short on time. Therefore the lecture and workshop schedules might conflict with other duties.

It’s essentially social activity: a student helps peer who is then receiving information. The purpose is to keep the group small, ideally between two people.

They can study the same course but basically they share knowledge of a common subject so that, for example, the information receiver is able to continue to finish her assignments.

***
**Context**: UbiKampus (co-working space)
***

 - Since it’s a library, people have to behave accordingly
 - People have roles but they are equal
 - Within the library opening hours

***
**Technology**: Web / Mobile App (interface)
***

 - Location: QR code
 - Peers: Chat

## Interview & Observation findings
The interview was done for five participants—three women and two men. They all study different things, one Bachelor’s student and four Master’s students. Their library use varies from daily to _"not that often"_. All participants study also in other libraries, such as Kaisa.

Interview and observation focused mainly on library use and study environment and the combined findings suggest that people study, seek information and use computers. Finding a place to study or other students happens primarily by visually browsing the space and walking around, causing noises—even though it’s a library and speaking out loud is discouraged, it’s not as quiet as one would expect. People also don’t take breaks (leave their place) as regularly as they said in the interviews. It looks like that, in the evening in Kaisa house, group rooms could be utilized more efficiently, so ad hoc study groups could be potentially created there, in addition to Kumpula campus.

## Brainstorming, Design critique & More Brainstorming

Even though the main idea and motivation for the system are simple, the end product is in many ways very different from the draft produced after brainstorming sessions—the goal for the sessions were to develop ideas without technical restrictions and time limitations, which were then converged into the end product.

Major design difference between the draft and end product related to connecting the system to physical space (via UbiKampus) and creating profiles for students. UbiKampus connection was intended to use bluetooth indoor navigation and message bus. Users were envisioned to have two profiles: information seeker and receiver, both profiles sharing same pool of predetermined topics of interest (i.e. in the context of Full Stack web development) in order to trivialize the complexity of matchmaking. In case of a match, the system would have notified users and potentially suggested free group study room.

Based on the aforementioned features and after feedback from design critique and re-thinking of the concept, we implemented a system with same idea but with a more feasible approach.

# The implementation (Stdy QRp)
Our proposed solution is based on the idea of facilitating the room booking by leveraging QR codes and chat-based interaction. The rationale is that 1) QR codes placed at campus would allow people to access a smartphone application and to tie the group to the location; and that 2) A chat reach those students who likely have similar knowledge and ongoing courses. Student is asked to fill in a few details, and the time starts when the group is created. The subject of the group is then published on the Telegram channel of a course the student is attending. The solution could be integrated to existing course channels in Telegram.

The basic use case begins with reading the QR code of the room. The application tells the user that she is in a certain room.

{{< figure src="/img/stdy-qrp-room.png" class="figure_img" caption="The application shows the selected room" >}}

Then the user fills the required information: subject or description of the group, user name and the course channel where the message (subject, time and place) will be published. Screenshots illustrate the two versions used in the evaluation.

{{< figure src="/img/stdy-qrp-create-a.png" class="figure_img" caption="Group creation: variant A" >}}

{{< figure src="/img/stdy-qrp-create-b.jpg" class="figure_img" caption="Group creation: variant B" >}}

{{< figure src="/img/stdy-qrp-created.png" class="figure_img" caption="The appearance of the messages depends on the form in which the group was created" >}}

# User Study
In this chapter, we describe the purpose and procedure of the study and what do we measure; participants, how we recruited them and the instructions and tasks that we gave them. We implemented the system with an assumption that it would make easier for students to arrange and participate impromptu study groups, and a laboratory experiment was designed to get preliminary insights on the research questions about matchmaking and user experience.

## Procedure
The experiment followed a within-subjects design with one independent variable (IV) being the way the group is created and it is designed to understand and measure to what extent the system really makes it easier and more likely for students to arrange and join impromptu study groups. We modified IV based on two questions: (1) Which kind of notification text would be more effective when creating impromptu study groups with a chat-based system; (2) Is matchmaking more efficient with specific than with generic subject description?

We recruited three (1M, 2F) Helsinki University students that were willing to use the app and were suitable for the study, based on the inclusion criterion: _"Students of Full Stack course"_. After the experiment, the participants were instructed to answer comparative questions about what are the advantages and disadvantages of using the system as opposed to other ways to find last minute help with their studies such as course chat. We also asked them to report their overall impressions of the system because collecting subjective feedback about _"Your feelings about the study group"_ in combination with the comparative questions will provide more reliable answers.

The experiment investigates creating a group with two different ways: selecting best closest match for creator’s problem from predefined subjects (drop-down menu) vs. letting the creator express the subject of the group by her own words (free-text field). Then, the tone and content of the notification text sent by the IM bot is chosen to be either more terse or verbose. The participants are asked how well does the bot message and the subject of the group—that is, implicit or explicit description and notification—correspond with the given problem and what would increase the odds to match and reach as many relevant peers as possible.

# Results

## Effort to create a group
The creator understood what the application is for and how to use it to achieve her goal.  Group creation was also reported to be easy. Right selection for the problem was not as easy to find from predetermined list of group subjects as it was to describe it in own words.

## Likelihood to participate a group
Peers are likely to join a study group set up by another person, no matter if they don’t know the creator or whether the creator is a student or a teacher. The group message was generally well understood but the predetermined subject of the group was preferred over the creator’s own description. The responses suggest that our system is an easy way to get to know about study groups, although the answers are not unanimous.

## Subjective feedback
All participants believe technology can help in finding people to study with and that studying in a group affects positively to their study experience. They all have encountered a need to solve study problems with peers and have been in situations where they would have liked to find peers to study with, or as was written in one participant’s answer:

_"Many times when I get stuck, it would be better to discuss it with someone, many times it takes a lot more time to solve the problem while continuing working alone."_

It was found that the right selection for the problem the creator was facing was not as easy to find from predetermined list of group subjects as it was to describe it in own words, which presumably means that when people are stuck with specific problem, they are looking for specific answers. On the other hand, peers preferred predetermined subject of the group over the creator’s own description, which presumably means that people with accumulated knowledge about a subject are willing to help in a broad area of problems whereas explicit problem is not as relatable. Subjective feedback also indicate that the predetermined subject helps in recollecting what was done in a particular course. It’s arguably meaningful to describe problem explicitly in own words but the tradeoff is that chances to reach potential peers and matchmaking diminishes.

