---
title: Assignment 2- Divergent Design
layout: doc
---
# Divergent Design

## 🎯 Broad Application Goals

After reflecting on my report from the needfinding assignment and combining ideas from a few of the design opportunities I found, I've decided that the focus of my application will be to create an experience that allows the user to feel that it was productive. It will not feel "time wasting", in the words of my intended audience, who are people that don't have an interest in "putting stuff out there" on social media "to get praised", and are interested in self-improvement. This application will take the 'doom' out of 'doomscrolling' by de-emphasizing or separating different types of content. It will also emphasize accomplishments/goals in order to remove some of the "artificiality" that modern social media promote through features such as likes and follower count. Existing apps encourage users to use them daily and often, yet do not promote productivity by increasing the visibility of productivity-tracking features, which is what will make my application will solve.

I picked a fun name for the app: **AchieveMint**. 
::: details Just for fun
I was so into my idea that the front-end addict in me went ahead and picked out a color palette (from [Color Hunt](https://colorhunt.co/)) for both dark and light mode that fit the theme and name of the application. 

![](/Color_Hunt_Palette_0719520b666a35a29f97feed.png){:width='200'}

Notice how they are cool-toned and greenish (to symbolize growth and freshness), as the name of the app suggests!

![](/Color_Hunt_Palette_f7c8e0dfffd8b4e4ff95bdff.png){:width='200'}
:::

## 📔 Scrapbook of Comparables
::: details Instagram has a feature where a user can save posts to collections, which is a general concept that would be useful for my app since users could save posts as inspiration or learning material under different categories/goals.
![](/instagram-collections.jpg){:width='300'}
:::

::: details Instagram screen time limits could help to remind the user to get off the app and go back to the real world. A summary of how the user interacted with and spent time on the app could be adapted to showing what kind of content the user consumes for awareness of how much time they spend being productive vs having fun.
![](/timespent.webp){:width='300'}
:::

::: details Keywords could give users more control over the content-showing algorithm and what content they see. 
![](/keywords.png){:width='300'}
[Link](https://x.com/soren_iverson/status/1832438700959265048)
:::

::: details If the user sets a post to be reviewed daily (or by some other time measure, maybe could implement a system supporting spaced repetition), reminders to review it on the app could increase their visibility, blocking other features of the app, until the user reviews the posts.
![](/bignotifications.png){:width='300'}
[Link](https://x.com/soren_iverson/status/1825911263945236613)
::: 

::: details Seeing what percentage of your life you spend on social media browsing certain types of content could make users more aware and motivated to limit doomscrolling behavior.
![](/lifepercentage.png){:width='300'}
[Link](https://x.com/soren_iverson/status/1824814024493813920)
:::

::: details Instagram tags allow users to find posts about a specific topic. My app could use this concept to allow users to find content that they're interested in, and maybe even search for posts that answer a question they have, which is really different from the search capabilities that Instagram currently has (difficult to find an account if the topic of the account is not in their username).
![](/instatags.png){:width='400'}
:::

::: details Instagram's explore page allows users to see content that they wouldn't normally see, which could help users feel like they are being productive by learning/discovering new things.
![](/explore.png){:width='300'}
:::

::: details Instagram verification badge shows that a user has verified their identity, which could help fix the problem of bots impersonating people which would make the app feel safer.
![](/verified.png){:width='400'}
:::

::: details Slack is a productivity platform that has emoji statuses that users can create and assign to themselves to let others know how/what they are doing, which is something that my app could incorporate to remove a layer of anonymity and remind users that they are interacting with real people. This is important since gathering data about how other people are doing could feel productive to people.
![](/slackstatus.png){:width='400'}
:::

::: details Obsidian is a note-taking tool that allows users to link a note to others, creating a graph of interconnected notes that use markdown. This format could be used to organize saved posts to help users form connections between new posts and old posts they are saving to feel productive.
![](/obsidian.png){:width='400'}
:::

::: details Medium is a blog platform where users write blogs. Oftentimes, articles teach users something and use social media post embeds or include sketches to illustrate concepts. This could be something that is embedded in posts or even act as an alternative to posts. That way, users can create and share them so others can learn from them.
![](/medium.png){:width='400'}
:::

::: details Linkedin has connections that are two-way, rather than one-way follows. This could reduce the toxic social media dynamic caused by people looking to gather followers by following them, expecting them to follow them back, then unfollowing them afterwards, in order to maintain their follower:following ratio.
![](/linkedin.png){:width='400'}
:::

::: details This is a visual representation of the stat distribution of a character that I've upgraded and built in a game that I play. Video games often feel very rewarding because they make players feel that they are improving themselves, so in an effort to replicate that, my app could have different categories for users to improve themselves, and show how many posts under that category they've saved.
![](/stats.png){:width='300'}
[Link](https://www.scoremyrelic.com/)
:::

## 🧠💭 Brainstorming Feature Ideas

- **Roles**: separate content creators and regular users such that content creators have a follower count but cannot follow anyone, and regular users can follow both content creators and other users but don't have a follower count. That way, regular users do not feel any pressure from implicit popularity rankings caused by follow counts.
- **Friending**: following is directed on many platforms, but on this app it would be mutual between users (for content creators, it would still be one-sided since a user would follow a content creator but content creators cannot follow anyone).
- **Posting permission**: both users and content creators can post, but users' posts can only be seen by friends (or close friends). This would make posts about a user's life less about appealing to strangers, and instead emphasize sharing things with friends.
- **Kudos**: gives a friendlier name to the upvoting system. Only content creators would receive these on their posts, so that users can tell relatively how helpful they were. Removing methods of ranking users is helpful in reducing the social pressure that social media can cause. 
- **Scheduling reviews**: Posts can be scheduled to be reviewed on certain days/times, which is helpful if a post acts as a learning flashcard, for example, a post could explain how a specific word in a different language is used. This combats the problem where users see a post, learn something new, but forget it over time. Spaced repetition timing could also be supported as a timing option.
- **Mood tracker**: since users are on social media every day, they might as well use the opportunity to be able to track long-term patterns in their mood to better inform their lifestyle choices. They would assign each day a mood on a scale from 1-10, with higher numbers representing better moods, and they would be able to see a color mapping of their moods each day on a calendar. This could have the option of being public to friends or close friends, so that friends know when to support them (it could send them a notification if their mood falls below 3, for example).
- **Habit tracker**: users can create multiple habits they want to commit to. They would see a calendar showing each day that they stuck to their habit.
- **Learning paths**: content creators can create learning paths, which involve scheduling posts to be reviewed at certain times in a certain order. Users can subscribe to these learning paths.
- **Streaks**: when a user has consistently reviewed posts in their spaced repetition schedule, stuck to the habits they are trying to form, or followed a learning path's schedule, they can add to their streak, which encourages them to continue being consistent. After reaching a milestone, friends would receive a notification that would signal them to hype that person up and continue staying consistent with their goals. 
- **Diaries**: social media could be used as a place to record things that happen each day, like a scrapbook or a diary that people can reflect on. Each day, users could be reminded of a diary entry they made exactly a year ago from that day, encouraging them to reflect on their memories and lifestyle.
- **Recommendations**: friends can anonymously recommend posts to their friends or a subset of their friends so that it appears on their feed, without having a make a group chat to force a discussion about it, which may influence people's opinions. Viewing content individually may allow users to come to their own conclusions about it.
- **Collections**: users can create collections of saved posts around a specific topic for reference later, which could have subfolders/subcollections to make it easy to find a certain saved post for later reference. Users could also pin certain posts to the top of collections in order to be able to quickly find them. These collections can also be shared with friends.
- **Goals**: users can create collections with a deadline, which would be called goals. Like collections, users would be able to add posts to a goal and receive reminders that have timings based on how long-term the goal is.
- **Stat tracker**: based on the names of collections, there would be a visual representation of a stat distribution (see the last image in the Scrapbook of Comparables) consisting of the collection names. The distribution would be based off of the percentage of posts in each collection, out of the total number of saved posts. This way, users can easily see which topics they save posts from the most, and adjust keywords or tags that their algorithm suggests them as needed. 
- **Notes**: a type of post formatted as a blog, where users can write articles using markdown that can embed other posts. These can be shared on their profile, and content creators can also share these. This idea will encourage users to compile helpful posts as notes for their personal learning or inspiration board, and share them with others.
- **Network**: a visual representation of notes that link to other notes, like a spiderweb or graph with each node being a note. This can help users link their ideas together.
- **Leveling system**: In an effort to gamify the application, and make the user feel that they are constantly improving themselves, a leveling system could be implemented where xp is obtained based on streak count, number of learning paths completed, and notes written.
- **Reminders**: users can make reminders for themselves to do certain things like maintain their Duolingo streak, or talk to a certain person. Reminders would happen automatically at certain times of the day if the user has not yet tracked their mood/habits or are about to miss a deadline on their learning paths/goals/reviews. These reminders would visually grow bigger the more urgent it gets, until they block out the navbar of the app, forcing the user to go through with the necessary actions.
- **Status**: Like on Discord and Slack, a user could set their status so people know what they are currently doing, and know whether or not they want to be bothered. When a user sets a status so that they do not want to be bothered, they would not receive notifications. This would capture things that the mood tracker doesn't (statuses such as sick, on vacation, or walking their dog). Users could set status changes to occur at a certain time on certain days and receive reminders for it to help them enforce their schedules.
- **Categorize content creators**: content creators would have tags that categorize them under things like whether their content involves learning or 'brain rot'. They would be further subcategorized into subjects like 'math', 'language learning', or 'movie reviews'. This would make it easy for users to find content creators that routinely put out content they want to see, without content creators having to name their account something with relevant keywords in it.

## 🧐 Value Sensitive Design (VSD) Analysis

- **Stakeholders: Indirect stakeholders** include companies that sponsor influencers to advertise their products or services. Since users of the app will have an increased ability to filter out 'meaningless' content and content that doesn't allow them to learn something from it, such as videos of people dancing to promote a product that has nothing to do with dancing, and since quality control of content will be enforced through kudos (which is based on users' general consensus as to whether the content is worth your time), advertisements will have to be much more purposeful. Companies will likely have to target collaborating with content creators whose learning paths could benefit from including a company's product, which ultimately forces companies to make products that are less 'time wasting'.
- **Stakeholders:** To **consider children**, whose values and are easily shaped by their peers on social media early on in their lives, user posting should be limited to just friends so that they are not interacting directly with strangers, and friending could be facilitated through inputting friend codes/ids so that children cannot friend anyone who they don't know in person. Children are also more likely to fall victim to scams or bot impersonations since they have less experience with and awareness of the risks of social media, so moderation will be important. In addition, having ages be visible on profiles and flagging when a minor is contacted by someone much older than them could also prevent unwanted contact. Location sharing could also help parents track kids to keep them safe.
- **Time:** Some **long-term effects** of the social media application are that people could use social media too much since daily use will become normalized. In response to this, the app could track how long a user has been on it per day and provide summaries to enforce awareness, and could also support options to set a time limit on the app. When the time limit is up, the app could shut down (and not be able to be reopened) until a certain time the next day.
- **Pervasiveness**: if the design is broadly adopted by people of many different countries, in order to still be able to share ideas across different languages, the app will likely have to support automatic translation features, or a feature to change the default language of the app (which could also help people who are trying to learn a different language). In addition to this, the original language and country/location of the content that was posted in could be included with each post by default to provide more background contextualizing the content, since conflicts on social media often occur when one side does not have enough background information to understand the perspective of the other.
- **Values:** The app supports the **value** of productivity, but too much emphasis on productivity can be damaging to mental health. Fun will also be accounted for by including a 'fun' category as a default collection, to remind users that while it's good to be productive, it's just as important to use social media as a tool to have fun or be inspired to have fun. The goal of the app, to encourage a balanced rather than solely productive lifestyle, should be emphasized through a feature showing summaries of users' saved content distribution. Feedback could be given on the balance of the content that the user is consuming, for example, if the user's saved content is 95% posts about some academic subject, the app could display feedback such as 'You are learning a lot, don't forget to take a break and have fun every once in a while'.

## 🎨 Storyboarding and Sketching

![](/one.jpg){:width='600'}

![](/two.jpg){:width='600'}

![](/three.jpg){:width='600'}