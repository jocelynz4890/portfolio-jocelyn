---
title: Assignment 3- Convergent Design
layout: doc
---
# Convergent Design

## 📣 Pitch

Pitch. Write a succinct (100 to 300 word) product pitch for your app, that gives it a name, describes its intended audience, the value that it brings, and some of its key functionality. Feel free to build on what you wrote in the previous assignment, and to draw on the insights you gleaned from your interviews and introspection. Describe the functionality in terms of the central concepts. We recommend drafting this pitch and then returning to adjust and revise it after you have completed your conceptual design.

Have you ever wasted time doomscrolling on social media and hated yourself for it afterwards? Do you wish you could harness your social. Achievemint is social media app that will leave you guilt-free and sets you up for self-improvement. It's all about balance. Achievemint promotes this in a gamified way.

## ⚙️ Functional Design

Functional design. Design a collection of concepts that will embody the functionality of your app; you’ll probably want 5-7 concepts for an app that is sufficiently rich to be interesting but not so complex that it can’t be implemented in the time you have (4 weeks). In some cases, a feature will correspond directly to a concept; in others, you may need to coalesce or split features. Concepts should be semantic, serve a distinct purpose, and be mutually independent. Each concept should be described with the standard parts: name, purpose, operational principle, state, and actions. You can write the principle informally, so long as it’s clear which actions are being referred to. The state should be defined using sets and relations. The actions can be written informally, or using the set/relation syntax illustrated in class. Define the app-level actions as synchronizations of concept actions, and instantiate generic concepts with appropriate types. Draw a dependency diagram showing the possible subsets.

Remember that the goal of this personal project is not just to learn the basics of building a full-stack web app but also to practice innovative design. So your design should have some novel elements to it, such as new concepts (which are not familiar from existing apps), new enhancements of existing concepts (adding actions or state that makes the concept more powerful or flexible or perhaps easier to use), new uses of existing concepts, or new synchronizations between existing concepts.

Roles: separate content creators and regular users such that content creators have a follower count but cannot follow anyone, and regular users can follow both content creators and other users but don't have a follower count. That way, regular users do not feel any pressure from implicit popularity rankings caused by follow counts.
Friending: following is directed on many platforms, but on this app it would be mutual between users (for content creators, it would still be one-sided since a user would follow a content creator but content creators cannot follow anyone).
Posting permission: both users and content creators can post, but users' posts can only be seen by friends (or close friends). This would make posts about a user's life less about appealing to strangers, and instead emphasize sharing things with friends.
Kudos: gives a friendlier name to the upvoting system. Only content creators would receive these on their posts, so that users can tell relatively how helpful they were. Removing methods of ranking users is helpful in reducing the social pressure that social media can cause.
Scheduling reviews: Posts can be scheduled to be reviewed on certain days/times, which is helpful if a post acts as a learning flashcard, for example, a post could explain how a specific word in a different language is used. This combats the problem where users see a post, learn something new, but forget it over time. Spaced repetition timing could also be supported as a timing option.
Mood tracker: since users are on social media every day, they might as well use the opportunity to be able to track long-term patterns in their mood to better inform their lifestyle choices. They would assign each day a mood on a scale from 1-10, with higher numbers representing better moods, and they would be able to see a color mapping of their moods each day on a calendar. This could have the option of being public to friends or close friends, so that friends know when to support them (it could send them a notification if their mood falls below 3, for example).
Habit tracker: users can create multiple habits they want to commit to. They would see a calendar showing each day that they stuck to their habit.
Learning paths: content creators can create learning paths, which involve scheduling posts to be reviewed at certain times in a certain order. Users can subscribe to these learning paths.
Streaks: when a user has consistently reviewed posts in their spaced repetition schedule, stuck to the habits they are trying to form, or followed a learning path's schedule, they can add to their streak, which encourages them to continue being consistent. After reaching a milestone, friends would receive a notification that would signal them to hype that person up and continue staying consistent with their goals.

Collections: users can create collections of saved posts around a specific topic for reference later, which could have subfolders/subcollections to make it easy to find a certain saved post for later reference. Users could also pin certain posts to the top of collections in order to be able to quickly find them. These collections can also be shared with friends.
Goals: users can create collections with a deadline, which would be called goals. Like collections, users would be able to add posts to a goal and receive reminders that have timings based on how long-term the goal is.
Stat tracker: based on the names of collections, there would be a visual representation of a stat distribution (see the last image in the Scrapbook of Comparables) consisting of the collection names. The distribution would be based off of the percentage of posts in each collection, out of the total number of saved posts. This way, users can easily see which topics they save posts from the most, and adjust keywords or tags that their algorithm suggests them as needed.

Leveling system: In an effort to gamify the application, and make the user feel that they are constantly improving themselves, a leveling system could be implemented where xp is obtained based on streak count, number of learning paths completed, and notes written.
Reminders: users can make reminders for themselves to do certain things like maintain their Duolingo streak, or talk to a certain person. Reminders would happen automatically at certain times of the day if the user has not yet tracked their mood/habits or are about to miss a deadline on their learning paths/goals/reviews. These reminders would visually grow bigger the more urgent it gets, until they block out the navbar of the app, forcing the user to go through with the necessary actions.


**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** Radar chart
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

**Name:** 
**Purpose:**
**Operational Principle:** 
**State:**
**Actions:** 

## 🖼️ Wireframes

Wireframes. Construct a set of wireframes that shows the user interface elements and their layout, and includes some of the main flows. You can omit error handling and completely standard interactions (such as user registration), but your wireframes should otherwise be enough to cover all your concepts.

## ❌ Design Tradeoffs

Design iteration. As you work on your functional design and wireframes, you should simulate the execution in your mind, considering each step the user might take and how the app would react. You should also have in mind the social/ethical concerns that you considered in the last assignment, and how they might be impacted by the decisions you’re making. As you do this, you will encounter problems that you have to resolve and choices to make. Note down the issues as they arise, and the options you considered; you won’t hand these notes in, but they’ll be useful in the next step.

Design tradeoffs. Using the notes that you took during your design, pick at least 3 design decisions that you made in which you had to choose between multiple options. For each one, provide (a) a pithy title naming the issue; (b) an outline of what the various options were; (c) a rationale for why you chose one option over the others. Try to keep your analysis below 300 words in total (for all the tradeoffs).