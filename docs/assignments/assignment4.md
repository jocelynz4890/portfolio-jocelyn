---
title: Assignment 4- Backend Design & Implementation
layout: doc
---
# Backend Design & Implementation

[Deployment](https://achievemint-app.vercel.app/)
<br>
[Repository](https://github.com/jocelynz4890/achievemint)

## ✅ Abstract Data Models

### Authenticating
```ts
    registered: set User
    username, password: registered -> one String
    roles: set User
    username, Role: registered -> one User
```

### Posting[Author]
```ts
    post: set (Content, quality_rating: int, category: Category)
    user_posts: User -> set Posts
    quality_ratings: set Ratings
```

### Following[User]
```ts
    user_followers: User -> set followers
    followers: set User
    follower: followers -> one User

    user_followings: User -> set followers
    followings: set User
    following: followings -> one User

    requests: set (user, user)
```

### Tracker-ing
```ts
    user_trackers: User -> set Tracker
    Tracker: (name, checked_days, shared)
    name: Subject -> one String
    checked_days: set boolean
    shared: set User
```

### Collection-ing[Content]
```ts
    user_collections: User -> set collection
    collections: user_collections -> one User
    default_collections: set Content
    default_subject: default_collections -> set collection
    collection: default_subject -> set collection
    name: collection -> one String
    deadline: collection -> one Date
    collectionContent: collection -> set Content
    collectionContentName: collectionContent -> one String
    shared: collection -> set Users
```

### Leveling[ExperienceSources]
```ts
    const s: ExperienceSources -> set int

    users_exp: set User
    user: users_exp -> one int

    users_lvl: set User
    user: users_lvl -> one int
```

### Summarizing[Categories]
```ts
    const counts: set Categories
    category: Categories -> one int 
```

## ✅ App Definition
```ts
app Achievemint
    include Authenticating
    include Posting[Author]
    include Following[User]
    include Trackering
    include Collectioning[String]
    include Leveling[Trackers, Collections]
    include Summarizing[DefaultCollections]
```
![](/diagram.jpg)

## Design Reflection
