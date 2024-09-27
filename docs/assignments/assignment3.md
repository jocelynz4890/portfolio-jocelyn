---
title: Assignment 3- Convergent Design
layout: doc
---
# Convergent Design

## 📣 Pitch

Have you ever regretted wasted time doomscrolling or comparing yourself to others on social media? Do you wish you could incorporate more productive and healthy habits into your life? Achievemint is social media app that will leave you guilt-free by setting you up for self-improvement. Achievemint divides users into two roles: content creators, who can post and have a follower count, and regular users, whose posts are only visible to friends and do not have a follower count. This way, users do not feel pressured to post or gain followers. In addition, 'likes' only exist on content creators' posts as a form of quality control. The removal of follower and 'like' counts for regular users reduces the social pressure that social media can cause. Lastly, only regular users can follow other users: following a content creator is a one-way relationship, while friending another regular user is a two-way relationship, which encourages users to only friend people they are comfortable with as a safety measure, while simultaneously discouraging the behavior of trading follows, only for one person to later secretly unfriend the other.

Achievemint is for those who could use more balance in their lives: the app allows users to save posts in shareable/collaborative collections and sub-collections classified under six categories: **Lifestyle**, **Health & Fitness**, **Entertainment**, **Food & Cooking**, **Fashion & Beauty**, and **Education & DIY (Do It Yourself)**. The app displays a summary of the user's amount of activity in each category. The app also aids users in achieving their goals by allowing for collections to have deadlines, which have increased visbility to the user as the deadline approaches. Achievemint also tracks daily habits a user is working on through a tracker feature with a heatmap view. These trackers can be shared among multiple users in order to enforce accountability. Finally, Achievemint also incorporates gamification through a leveling system to motivate users to keep up with their goals and maintain healthy habits.

## ⚙️ Functional Design

![](/dependencies.jpg){:width='600'}  

:::details Authenticating 
**Purpose:** authenticate users so that each user of the app is a person
<br>

**Operational Principle:** Authorize a user to access their profile given the correct username and password that was set when they registered and picked a role.


**State:** 
```ts
    registered: set User
    username, password: registered -> one String
    roles: set User
    username, Role: registered -> one User
```
**Actions:** 
```ts
    register(username, password: String, role: RoleOptions, out user: User)
        require username not in registered
        set new username, password pair in registered
        set new username, role pair in roles

    getUserRole(username: String, out: Role)
        require username in registered
        return Role associated with username

    getAllUsersWithRole(r: Role, out: set User)
        return users in registered with role === r

    authenticate(username, password: String, out user: User)
        require username in registered
        check if username, password pair is in registered
```
:::

:::details Posting[Content]
**Purpose:** create/share content so that others can see it and upvote it to improve its quality rating
<br>

**Operational Principle:** After posting a post, other users can see the post, and the original poster can remove or update the post. Each post has a quality rating, which 

**State:**
```ts
    post: set (Content, quality_rating: int)
    user_posts: User -> set Posts
    quality_ratings: set Ratings
```
**Actions:** 
```ts
    post(u: User, c: Content)
        post := (c, quality_rating=0)
        user_posts[u] += post

    removePost(u: User, p: post)
        require p in user_posts[u]
        user_posts[u] -= p

    updatePost(u: User, p: post, c: Content)
        require p in user_posts[u]
        p := c

    getPosts(u: User, out: Posts)
        return user_posts[u]

    incrementQualityRating(p: post)
        post.quality_rating += 1

    getPostOwner(p: Post, out: User)
        for user in user_posts
            if p in user.posts
                return user
```
:::

:::details Following[User]
**Purpose:** allow users to see information associated with another user
<br>

**Operational Principle:** If a user is not following another user, the user can request to follow the other user. After the request is accepted, the user is following the other user. If a user is following another user, the user can unfollow the other user.

**State:**
```ts
    user_followers: User -> set followers
    followers: set User
    follower: followers -> one User

    user_followings: User -> set followers
    followings: set User
    following: followings -> one User

    requests: set (user, user)
```
**Actions:** 
```ts
    addFollower(u: User, v: User)
        user_followers[u] += v

    addFollowing(u: User, v: User)
        user_followings[u] += v

    addRequest(u: User, v: User)
        requests += (u, v)

    removeRequest(u: User, v: User)
        requests -= (u, v)

    acceptRequest(u: User, v: User)
        addFollower(u, v)
        removeRequest(u, v)

    getFollowers(u: User, out: set User)
        return user_followers[u]

    getFollowings(u: User, out: set User)
        return user_followings[u]
```
:::

:::details Tracker-ing[Subject]
**Purpose:** users can make a daily tracker for a particular subject that can be shared with other users so that others can see their progress
<br>

**Operational Principle:** Users specify a subject for a tracker by naming it, and can share and remove other users from being able to see it. Each day on the tracker can be checked off by the user, which the user can see an accumulated view of through a 360-day heat map.

**State:**
```ts
    user_trackers: User -> set Tracker
    Tracker: (name, checked_days, shared)
    name: Subject -> one String
    checked_days: set boolean
    shared: set User
```
**Actions:** 
```ts
    makeTracker(u: User, name: name, shared: shared, out: Tracker)
        user_trackers[u] += new Tracker(name, set FALSE, shared)

    getTrackers(u: User, out: set Tracker)
        user_trackers[u]

    getTrackersNames(u: User, out: set Tracker)
        for tracker in getTrackers(u):
            get tracker.name

    getTrackerByName(u: User, n: name, out: String)
        user_trackers[u].n

    getCheckedDays(u: User, n: name, out: String)
        getTrackerByName(u, n).checked_days

    shareTracker(u: User, n: name, v: User)
        getTrackerByName(u, n).shared += v

    unshareTracker(u: User, n: name, v: User)
        getTrackerByName(u, n).shared -= v

    deleteTracker(u: user, n: name)
        user_trackers[u] -= getTrackerByName(u, n)

    checkDay(u: User, n:name)
        getTrackerByName(u, n).checked_days.today = true

    uncheckDay(u: User, n:name)
        getTrackerByName(u, n).checked_days.today = false

    getTotalCheckedDays(u: User, n: name)
        count = 0
        for day in getTrackerByName(u, n).checked_days
            if day === true
                count += 1
        return count
```
:::

:::details Collection-ing[Subject]
**Purpose:** users can create collections of saved content to look back on later, that can have subcollections for further levels of organization, and that can be collaborative and have deadlines.
<br>

**Operational Principle:** Users can save content under several umbrella categories. Users can add collections consisting of content and other collections. Collections can have other contributors, and can be assigned a deadline that can later be modified.

**State:**
```ts
    user_collections: User -> set collection
    collections: user_collections -> one User
    default_collections: set Subjects
    default_subject: default_collections -> set collection
    collection: default_subject -> set collection
    name: collection -> one String
    deadline: collection -> one Date
    collectionContent: collection -> set Content
    collectionContentName: collectionContent -> one String
    shared: collection -> set Users
```
**Actions:** 
```ts
    getUserCollections(u: User, out: set Collection)
        return users_collections[u]

    getCollectionByName(u: User, n: String, out: Collection)
        return getUserCollections(u) if getUserCollections(u).name === n

    newCollectionWithDeadline(u: User, parent: String, deadline: Date, n: String)
        for collection in user_collections[u]
            if user_collections[u].collection.name === parent
                newCollection = new user_collections[u].collection
                newCollection.deadline = deadline
                newCollection.name = n

    newCollectionWithoutDeadline(u: User, parent: String, n: String)
        for collection in user_collections[u]
            if user_collections[u].collection.name === parent
                newCollection = new user_collections[u].collection
                newCollection.name = n

    addToCollection(u: User, n: String, c: collectionContent)
        getCollectionByName(u, n).collectionContent += c

    removeFromCollection(u: User, n: String, cn: collectionContentName)
        require u can access the collection
        for content in getCollectionByName(u, n).collectionContent
            if content.collectionContentName === cn
                getCollectionByName(u, n).collectionContent -= content

    deleteCollection(u: User, n: String)
        require u can access the collection
        for collection in user_collections[u]
            if user_collections[u].collection.name === n
                user_collections[u] -= collection

    getCollectionDeadlines(u: User, out: set Date)
        for collection in user_collections[u]
            return collection.deadline

    shareCollection(u: User, n: String, v: User)
        require u can access the collection
        access collection with name n
        share collection with v if (v cannot currently access collection) and (v does not have a collection named n) by adding v to shared

    unshareCollection(u: User, n: String, v: User)
        require u can access the collection
        access collection with name n
        unshare collection with v if v can currently access collection by removing v from shared

    updateCollectionDeadline(u: User, n: String, d: Date)
        require u can access the collection
        access collection with name n
        set new collection deadline to d

    getAccessibleCollections(u: User, out: set Collection)
        sharedWithUser = set Collection
        for user in user_collections
            for collection in user.collections
                if collection.shared contains user
                    sharedWithUser += collection
        return sharedWithUser

    getUserNumCollections(u: User)
        return users_collections[u].size

    getUserDefaultCollectionsSizes(u: User, out: set int)
        counts: set int
        for collection in default_collections[u]
            counts[collection] = collection.size
        return counts
```
:::

:::details Leveling[ExperienceSources]
**Purpose:** users can reflect quantitatively on the amount of progress they've made from various sources of experience
<br>

**Operational Principle:** The level of a user is calculated based on the number of experience points acquired by the user, which is calculated from a fixed set of experience sources. The amount of experience points required to reach the next level doubles each time and starts at 5 exp required to go from level 1 to 2.

**State:**
```ts
    const s: ExperienceSources -> set int

    users_exp: set User
    user: users_exp -> one int

    users_lvl: set User
    user: users_lvl -> one int
```
**Actions:** 
```ts
    calculateUserTotalExp(u: user, s: ExperienceSources, out: int)
        totalexp = 0
        for exp in s:
            totalexp += s
        return totalexp

    updateUserExp(u: User)
        users_exp[u] = calculateUserTotalExp(u, s: ExperienceSources)

    calculateLevel(i: int, out: int)
        return floor(log_2_(i/5))

    updateLevel(u: User)
        updateUserExp(u)
        users_lvl = calculateLevel(users_exp[u])

    isLevelChanged(out: boolean)
        return old users_lvl !== new users_lvl
```
:::

:::details Summarizing/Balancing[Categories]
**Purpose:** users can reflect quantitatively on the amounts of relative contribution that they have made to several categories, and get recommended content of categories with lower activity levels in order to create more balance among the different category activity levels
<br>

**Operational Principle:** From a fixed set of categories, generates a summary of relative activity levels of the user in each category. Updates based on changes in number of interactions accumulated in each category. Finds category with current lowest activity level, which will be recommended to the user more often, until there is a new category with the lowest activity level.

**State:**
```ts
    const counts: set Categories
    category: Categories -> one int 
```
**Actions:** 
```ts
    isDataChanged(c: set categories, out: boolean)
        return old categories !== c

    updateSummaries(c: set categories, out: set int)
        for category in counts
            counts = c[category]

    updateIfDataChanged(c: set categories, out: set int)
        if isDataChanged(c)
            return updateSummaries(c)

    findLowActivityCategory(c: set categories, out: category)
        for category in c
            return lowest int category
```
:::

### App-level Actions as Synchronizations

```js
app Achievemint
    include Authenticating
    include Posting[Content]
    include Following[User]
    include Tracker-ing[String]
    include Collection-ing[[Lifestyle, Health&Fitness, Entertainment, Food&Cooking, Fashion&Beauty, Education&DIY]]
    include Leveling[Trackers, Collections]
    include Summarizing[NumSavedContent]

    sync register(username, password: String, out user: User)
        Authenticating.register(username, password, user)

    sync login(username, password: String, out user: User, out session: Session)
        Authenticating.authenticate(username, password, user)

    sync post(user: User, content: Content)
        Posting.post(user, content)

    sync editPost(user: User, p: Post, content: Content)
        Posting.updatePost(user, p, content)

    sync removePost(user: User, p: Post)
        Posting.removePost(user, p)

    sync getPosts(user: User, p: Post, content: Content, out: set Post)
        return Posting.getPosts(user)

    sync qualityRatePost(user: User, p: Post)
        if Authenticating.getUserRole((Posting.getPostOwner(p)).username) === ContentCreator
            Posting.incrementQualityRating(p)

    sync follow(user: User, otheruser: User)
        if Authenticating.getUserRole(user.username) === RegularUser
            if Authenticating.getUserRole(otheruser.username) === ContentCreator
                Following.addFollower(user, otheruser)
            else
                Following.addRequest(user, otheruser)

    sync rejectRequest(user: User, otheruser: User)
        Following.removeRequest(user, otheruser)

    sync acceptRequest(user: User, otheruser: User)
        Following.acceptRequest(user, otheruser)
        if Authenticating.getUserRole(user.username) === RegularUser and Authenticating.getUserRole(otheruser.username) === RegularUser
            Following.addFollower(otheruser, user)

    sync createTracker(user: User, name: String, shared: set User, out: Tracker)
        if Authenticating.getUserRole(user.username) === RegularUser
            return Tracker-ing.makeTracker(user, name, shared)

    sync createCollection(user: User, parent: String, d: deadline, name: String)
        if d
            Collection-ing.newCollectionWithDeadline(user, parent, d, name)
        if not d
            Collection-ing.newCollectionWithoutDeadline(user, parent, name)

    sync shareTracker(user: User, name: String, otheruser: User)
        if Authenticating.getUserRole(user.username) === RegularUser
            Tracker-ing.shareTracker(user, name, otheruser)

    sync shareCollection(user: User, otheruser: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Collection-ing.shareCollection(user, name, otheruser)

    sync unshareTracker(user: User, name: String, otheruser: User)
        if Authenticating.getUserRole(user.username) === RegularUser
            Tracker-ing.unshareTracker(user, name, otheruser)

    sync unshareCollection(user: User, otheruser: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Collection-ing.unshareCollection(user, name, otheruser)

    sync deleteTracker(user: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Tracker-ing.deleteTracker(user, name)
            Leveling.updateLevel(user)

    sync deleteCollection(user: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Collection-ing.deleteCollection(user, name)

    sync checkTracker(user: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Tracker-ing.checkDay(user, name)
            Leveling.updateLevel(user)

    sync uncheckTracker(user: User, name: String)
        if Authenticating.getUserRole(user.username) === RegularUser
            Tracker-ing.uncheckDay(user, name)
            Leveling.updateLevel(user)

    sync addToCollection(user: User, name: String, p: Post)
        if Authenticating.getUserRole(user.username) === RegularUser
            Collection-ing.addToCollection(User, name, p)
            Summarizing.updateSummaries(Collection-ing.getUserDefaultCollectionSizes(user))
            Leveling.updateLevel(user)

    sync updateCollectionDeadline(user: User, name: String, d: Date)
        if Authenticating.getUserRole(user.username) === RegularUser
            Collection-ing.updateCollectionDeadline(user, name, d)

    sync getAllContentCreators(user: User, out: set User)
        return Authenticating.getAllUsersWithRole(ContentCreator)
    
    sync getFollowers(user: User)
        if Authenticating.getUserRole(user.username) === ContentCreator
            Following.getFollowers(user)

    sync getFollowings(user: User)
        if Authenticating.getUserRole(user.username) === RegularUser
            Following.getFollowings(user)

    sync recommendContent(user: User, out: [Lifestyle, Health&Fitness, Entertainment, Food&Cooking, Fashion&Beauty, Education&DIY])
        if Authenticating.getUserRole(user.username) === RegularUser
            Summarizing.updateIfDataChanged(Collection-ing.getUserDefaultCollectionSizes(user))
            return findLowActivityCategory(Collection-ing.getUserDefaultCollectionSizes(user))
```

## 🖼️ Wireframe

[Link to Figma wireframe](https://www.figma.com/proto/OwRyA1ZzjOUoE2wWJJgKPn/Achievemint?node-id=2-3&t=P4YdxyhPfY946OWp-1)

## ❌ Design Tradeoffs

### User-defined summary categories
My options for creating a summary of user's behavior on the app were to select specific categories to group different types of behavior, allow users to create their own categories, or have a mix of both, where I would provide specific categories but allow users to create their own by assigning a collection to be included as a main category in the summary.

I chose the first option since the app supports the value of productivity, but too much emphasis on productivity can be damaging to mental health. Over time, the user may feel pressured to create categories that focus more and more on productivity, but to emphasize balance, I decided to preselect all of the categories, including an entertainment category to remind users that while it's good to be productive, it's just as important to use social media as a tool to have fun or be inspired to have fun.


### User-created reminders
In order to make the app more useful, I had to decide whether to allow users to create their own reminders in addition to the default reminders that come with daily trackers and collections with deadlines. I decided against the concept of allowing users to create custom reminders after reflecting on the long-term effects of the app. A reminder system would cause the app to become similar to a daily to-do list, that encourages the user to constantly check it. This app, while encouraging productivity, also encourages the consumption of different types of content. Constant notifications would likely contribute to normalizing social media overuse, which contradicts the app's goal to encourage balance. It would be better for users to just use a reminder focused app, without any of the distractions of social media. The one advantage that a social media based reminder system would offer is the ability to have group reminders, but any more sources of reminders outside of the default reminders (which already have shared reminders) would cause the app to become distracting.


### Searching to find users
In order to friend other users on the app, I had to decide between allowing regular users to search for other users by username or only find other users by a code/user ID, while keeping content creators searchable. Each option varies in their degree of being able to find strangers on the app. I ultimately decided on using an ID to find other users after considering children or younger people who might use the app, trading off flexibility for safety. Friending facilitated through inputting user IDs forces children to only be able to friend people they know in-person. 