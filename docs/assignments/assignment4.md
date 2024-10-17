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
    roles: set User -> one Role
```

### Posting[Content,Categories]
```ts
    post: set (Content, quality_rating: int, category: Categories)
    user_posts: User -> set Posts
```

### Following[User]
```ts
    friendships: set (user, user)
    requests: set (from: User, to: User, status: "pending" | "rejected" | "accepted")
```

### Tracker-ing
```ts
    user_trackers: User -> set tracker
    tracker: (title: String, days, shared)
    days: set boolean
    shared: set User
```

### Collection-ing[Content]
```ts
    user_collections: User -> set collections
    collections: user_collections -> set collection
    collection -> set (Content, parentCollection)
    title: collection -> one String
    deadline: collection -> one Date
    shared: collection -> set Users
```

### Leveling[ExperienceSources]
```ts
    const s: ExperienceSources -> set int

    users: set User
    user: users -> set (exp: int, lvl: int)
```

### Summarizing[Categories]
```ts
    user_counts: set User
    user: user_counts -> set Categories
    category: Categories -> one int 
```

## ✅ App Definition
```ts
app Achievemint
    include Authenticating
    include Posting[String, Collectioning]
    include Following[User]
    include Trackering
    include Collectioning[Posting]
    include Leveling[Trackering, Collectioning]
    include Summarizing[Collectioning]
```
![](/diagram.jpg)

## ✅ Design Reflection

Originally, I intended for posts to be like Instagram posts, where a user could upload a short bit of text along with a set of images. After reflecting on the purpose of my app, which is productivity, I decided blog-type posts would be more appropriate, so posts now consist of a single piece of content (which will be a string), instead of a set of content.

I left the concept of friending/following kind of vague in A3 since I wasn't exactly sure how I wanted to relate them in the implementation. I decided that it would make the most sense for regular users to be able to friend each other as given in the friending starter code, but when users friend a content creator, it skips the intermediate requesting stage and just immediately follows them.

I also had to decide whether users could edit their role (in Authenticating), which allows user to backtrack on mistakes and give them more flexibility. I decided against allowing users to edit their role, since it would not make sense for a user to switch from one role to the other (their entire experience on the app would be changed).

For my collectioning concept, I considered having a set of owners instead of having an owner and a separate set of shared users, but decided to keep the original owner separate so that only the owner of the collection could share and unshare the collections for simplicity. Also, instead of allowing users to edit a collection that is shared with them, which may cause issues with the owner of the collection, users will be able to share collections with the same name (I removed the restriction that names have to be unique). This way, they can have their own collection with that name (that can be shared back to the other user), and on the frontend, the shared collection with the same name will also show up under that collection. This allows both users to see each other's collection, while being able to edit their own copies of the collection without fear of tampering by a shared user. Also, instead of deadlines being a Date object, I allowed it to be any String for more flexibility. Finally, I removed the nested hierarchy of collections (there will only be one level of nesting from the default collections) since having to track the amount of content and handle removals and additions of collections across highly nested levels of collections would become complicated.