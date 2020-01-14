---
title: "Organizational Structure at Pivotal"
date: 2020-01-13T13:57:17+09:00
author: "Dylan Lau"
tags: ["Pivotal"]
keywords: ["Pivotal", "Organization", "Anchor", "XP"]
description: "An in depth explanation of Cloud Foundry organizational structure at Pivotal, the development methodology, and how everyone fits in."
draft: true
---

# Pivotal

I worked at Pivotal twice - once as an intern and again as a full time. Pivotal used Extreme Programming for development. This involves daily standups, weekly retros and pair programming. Teams were structured as working on a particular component or add-on to Cloud Foundry, with some teams managing multiple add-ons that fall under a general category. Each team had one or more Project Managers, a team Anchor and engineers.

# Team Structure

The project manager was responsible for contacting customers, gathering feedback, prioritizing work and creating product roadmaps. They did not need to have any technical background and were rarely writing code. Instead, they mostly set up meetings with customers, wrote documentation, release notes and presentations. As a result, they needed to have a high level understanding of the main product (Pivotal Cloud Foundry) and a thorough understanding of what the team's product is, how it works and why it exists.

The Anchor is an engineer who serves as the technical leader of the team. They have a strong technical background but also serves as a team leader and is involved in some executive decisions involving the team. As a result, they need a similar level of understanding of the team's product as the project manager, but they are not the primary point of contact for customers.

The remaining members are Engineers, who are responsible for doing the technical work. They have a strong technical background who should understand the main product, the team's product, how it works and why it exists, but are not involved in any executive decisions.

So to quickly recap, in a team there is:

- 1 or more Project Managers
- 1 Team Anchor
- 1 or more Engineers

# Organizational Structure

You might be wondering, there's a project manager and anchor, who do the engineers report to, and who do the project manager and anchor report to? Well, there are engineering managers who serve as managers at the organizational level, but are simply engineers in the scope of a team. The engineering manager is unrelated to the members of the team - that is, each team member can have a different engineering manager, but two team members can have the same engineering manager. However, the engineering manager for each member must be on a different team than the team that the member is on. Say, team Alpha has members A, B and C. A and B's engineering manager is X and C's manager is Y. However, X and Y must not be members of team Alpha. By the way, project managers and anchors are considered engineers for this case, and have their own engineering managers as well.

So once again, in a team there is:

- 1 or more Project Managers
- 1 Team Anchor
- 1 or more Engineers

And at the organizational level each member is considered an Engineer and has their own Engineering Manager, who is an Engineer on another team.

# Extreme Programming

Let's go in depth about Extreme Programming. At Pivotal, we had daily stand-ups, weekly retrospectives, weekly iteration planning meetings (IPM) and pair programming all the time. These are at the team level - there is also similar events at office (physical location) level and organization level. There's also something at the organization level called a "drumbeat". I'll talk about each part separately.

## Daily Stand-Up

Daily standup is a daily synchronization that occurs at team level and office level. For teams, this would involve introductions for any new members, followed by what members did the previous day and what they plan to do today, and anything that they may be stuck or blocked on, and then any announcements. At office level, stand-ups would start with introductions of any new members, any interesting events in the form of tech news or local events, and anything that anyone may be stuck or blocked on, and then any announcements.

## Weekly Retrospectives

Weekly retrospectives, or weekly retros, was something that occured at team level and organization office level. Specifically, we had a weekly team retro, and a Cloud Foundry Toronto retro every 2 months. We used [Postfacto](https://github.com/pivotal/postfacto) as the retro platform, and everyone would write whatever is on their minds in the appropriate column. Someone would facilitate the retro and go through each item for a maximum of 5 minutes, and everyone would have a discussion about it. There is also an "action items" section, for if there is anything to be done about a particular retro item. For example, if there is a retro item about someone wondering where the next team offsite is, an action item can be created to decide on the next team offsite.

## Weekly Iteration Planning Meeting (IPM)

Iteration / Sprint Planning Meetings were held on a weekly basis and was facilitated by the Project Manager. The development process is largely feedback based at Pivotal - features are developed when a customer asks for it. When a customer asks for a feature, or at the Project Manager's discretion, the Project Manager would create a unit of work called a "Story".

A key responsibility of the Project Manager was to write great Stories that are clear and concise for the Engineers to understand. A story had a Title, Description, Acceptance Criteria and Resources. Acceptance Criteria strictly followed a "Given, When, Then" format. This is explicit context, action and expected result that is used as the definition of a story being "done". For example:

- **Given** that I am on the "Account" page
- **When** I click the "Log Out" button
- **Then** I am logged out of my account and returned to the "Home" page.

This acceptance criteria is to be strictly followed. The "Given" is the context of the story, in which case is the "Account" page. The rest of the story is irrelevant if the user is not on the "Account" page. Then "When" is the action of the story, in which case is clicking the "Log Out" button. The rest of the story does not apply if any other button is clicked. "Then" is the expected result - the expected result and only the expected result should happen.

Over the course of a week, a Project Manager would create stories. IPM is a team wide meeting where the team would go over the newly created stories. Engineers would discuss the content of the story regarding the technical implementation, and the Project Manager would answer any questions related to the story. After covering the story, everyone would assign a value to the story corresponding to the difficulty. This process is known as "Pointing", and is done at the same time with a short countdown and then Engineers indicating a number value with their fingers. The process is done like this to prevent Engineers from changing their value depending on the value suggested by others.

## Pair Programming

At Pivotal, we did pair programming whenever possible. It is a fundamental aspect of Extreme Programming as a way to provide constant code reviews. With pair programming, one person is the "driver" and the other person is the "navigator", and these 2 people would form the "pair", and they would use the same computer at the same time, with each person having their own mouse and keyboard. The "navigator" would do the thinking and talk out loud while telling the "driver" what to write, while the "driver" would do the typing and use the mouse.

## Drumbeats

Drumbeats are emails sent out by a team's project manager to the entire organization on a weekly basis outlining what the team is currently working on, their progress, what's on the roadmap and any current challenges that the team is facing. Usually, a drumbeat is created using release notes or the team's daily standup over a week duration. Another way to think of a drumbeat is an organization level pub/sub system where a team routinely publishes information and anyone who wants context on a particular team at some point in time can subscribe to that team.

# Does Pivotal's Organizational Structure Work?

Now with all the facts out of the way, we can get to the discussion. Let's start with the team level first. The first thing to note is that a team is **relatively balanced**, with the Project Manager doing the majority of the organizational work and roadmapping. When it comes to who writes documentations and release notes, it depends on the team itself - for my team, the Engineers wrote the release notes, but the Project Manager made the release notes presentable.

The anchor acts as a key link between organization directors, the project manager and engineers. While they primarily do the same work as an Engineer, they are a key resource for everyone else on the team and directors regarding technical and non-technical issues. On top of this, they are also responsible for ensuring code quality and act as a lead engineer in a team.

Engineers on a team don't actually belong to the particular team. To be specific, all the Engineers in the organization belong to a pool of people called Pivots. Pivots are then assigned to a team based on their interests, location, etc. Pivots are free to change teams after a small process. **It is much harder for Project Managers and Anchors to change teams, but Pivots can change teams easily.** In fact, for the part of Pivotal that works on client projects, the "project", or "team", that a Pivot was assigned to would change every week.

## Engineering Managers

Engineering Managers are organizational managers for all Engineers and are on different teams than the Engineers that report to them (who I will refer to as an Engineering Manager's "reports" from here on). This means that the Engineering Managers themselves are not biased toward particular Engineers, but makes evaluating their reports significantly more difficult.

At Pivotal, the development process is largely feedback based, and performance evaluations are also feedback based. It is the responsibility of the Engineering Manager to gather feedback for their reports, but an Engineer is encouraged to get their peers to send their Engineering Manager feedback for them. Each Engineering Manager has their preferred format of feedback, and it is their responsibility to pass that feedback onto their reports and quantify the feedback into performance and compensation. Generally, Engineering Managers get feedback for their reports from other Engineers in the same team as their report - most notably, the Engineer that their report has done Pair Programming with the most, and the team anchor.

Engineering Managers are similar to an Anchor - they primarily work as an Engineer on their team, but also perform people management responsibilities on the side. Regular 1 on 1's with their reports, gathering feedback and transforming it into quantitative values, managing a team transfer request for their reports, all while still functioning as an Engineer on their team, is a very demanding job. In Toronto, each Engineering Manager was responsible for at least 6 Pivots, and there's often a call for more Engineering Managers.