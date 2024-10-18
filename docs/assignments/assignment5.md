---
title: Assignment 5- Frontend Design & Implementation
layout: doc
---
# Frontend Design & Implementation

[Deployment](https://achieve-mint.vercel.app/)
<br>
[Repository](https://github.com/jocelynz4890/achievemint)

## ✅ Heuristic Evaluation
### 🔴 Usability Criteria
#### Error tolerance
- Trackers have the ability to check and also uncheck (in the tracker editing screen)
- Trackers, collections, and posts can be edited
- Content creators and friends can be followed and unfollowed
- Wherever sharing is an option, unsharing is also an option
- A back button or exit button should be clearly visible on every popup and page
- Adding an "undo" option after an action (e.g., deleting a tracker) can be more user-friendly than showing a confirmation prompt every time (which is the current design), but it may increase the risk of accidental actions going unnoticed if users are not aware of the undo feature.

#### Accessibility
- Color is not used as the sole indicator for anything.
- Contrast is maintained between 
- People should be able to access the app regardless of the device they access it on, so the UI should be able to adapt to any screen size. The current design, with the ability to scroll down the page, is fitting for mobile users, but desktop users should not have to scroll past the large visuals and texts when their screens are bigger and are capable of fitting the information in without having to scroll so much.

### 🔴 Physical Heuristics
#### Gestalt Principles
- The collections page makes heavy use of the principles of proximity/similarity/symmetry to display groups of posts in a collection.
- The hamburger menu and navbar make use of similarity to indicate to the user that they are a group of clickable options. 
- Something that the UI could improve on is the large spacing/typography of each page, which forces the user to have to scroll a lot. To allow them to take in information faster, I could make each element on the page smaller and divide the page into grids of similar content (principle of similarity) to fit more information on the page without being visually confusing. For example, the level display could be in a grid in the top left corner, with a list (rows) of trackers underneath. On the right half of the page, there could be a square grid of collections.
- Reducing the spacing and dividing content into grids allows users to take in more information quickly, but it could also lead to a cluttered interface, making it harder to focus on individual elements.
- While using similar designs across UI elements helps users recognize clickable options, making every element look similar could reduce the distinctiveness of individual features, leading to confusion about where an element leads, so distinction between collections/trackers/posts should be maintained.

#### Accelerators
- Quickly accessible navbar at the top of every page for common actions
- Also a hamburger menu in the top left corner for easy navigation
- Collections page should have a way of multi-selecting multiple collections or posts within a collection to perform a common action on all of them at the same time.

### 🔴 Linguistic Heuristics
#### Consistency
- Use of icons is consistent across pages (posts look the same, user icons look the same, share icon is the same)
- Action icons (such as the action confirmation icon) are the same on every page
- UI element for creating new posts/collections/trackers have the same visual layout
- Use of terminology is consistent (names of concepts, such as collections and trackers)
- Since trackers and collections share some actions (such as creating/editing/deleting), it makes sense to have the UI for those actions look the same for consistency, which is upheld in my wireframe.
- Using consistent terminology throughout the app helps users understand and predict features, but some terms might not be as intuitive or user-friendly, especially for new users who may not be familiar with the app's jargon, so they should be defined on the collections/trackers page as a short description of the concept.

#### Information Scent
- When clicking into a tracker or collection, there is a back button, which indicates that the user can go back to the main page of collections and trackers.
- The back button should more clearly indicate which page it would redirect the user to, to distinguish between this kind of button and a regular "go back to the previous page" button.
- Adding text to distinguish back buttons (e.g., "Back to Collections" vs. a generic "Back") improves clarity but adds visual clutter. There’s a tradeoff between a clean interface and providing detailed guidance for users.
- Similarly, a friend or content creator's username should be displayed when looking at their posts or anything on their profile. 
- There could also be a visual indicator on the navbar and/or navigation hamburger meny to indicate which page the user is currently on.

## ✅ Visual Design Study
TODO

The wireframes you constructed in A3 focused on identifying the user interface elements your app would use, how they would be laid out, and how users would flow between different screens of your app. In contrast, a visual design study will help you establish the “look and feel” of your app—namely, what fonts and colors will you use, and what do they communicate about your app’s purpose.

Look through a diverse range of visual media (including photographs, screenshots, magazines, newsprint, graphic novels, etc.) and assemble two slides of inspiration focusing on typography and color respectively. On each slide, collage together examples that you find particularly inspiring, and then use the margins to extract or annotate particular design choices you might be interested in exploring (e.g., specific color palettes and font families, or characteristics that you find interesting such as serifs, tall/short x-heights, etc.). We provide an example of a slide focusing on color in the advice section at the bottom of this page.