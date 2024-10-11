---
title: UI Interaction Design
layout: doc
---

# Evaluating Discord's UI

In this blog, I'll apply some of the criteria we covered in lecture for evaluating user interfaces to Discord:
![](/cheatsheet.png){:width='600'}

## Pleasantness
An example of pleasantness that Discord provides is the ability to collapse the channels in a category for a less cluttered interface. It's also easy to use: it's an error-tolerant feature since it can be toggled, and is easily discoverable since there is a symbol indicating the collapsed status that becomes bold when hovering over the title of the category. 
![](/collapsedcategory.png){:width='400'}

## Error tolerance
Discord allows users to delete and edit messages, and even unmark them as read if a user accidentally scrolled over the messages, which marks them as read. Message ids can also be copied (to be reported), which also contributes to safety. 
![](/errortolerance.png){:width='400'}

## Accessibility
Discord does a good job particularly of avoiding having color be the only indicator, accomodating for people with various types of colorblindness. In all instances I could find, whenever a color indicated some sort of setting/status, there would always be accompanying text. This is an example of one of them.
![](/discord-status.png){:width='600'}
The different online status are not only shown through color, but also have a short title and a description of the side effects of picking a certain status. The ability to turn off notifications, effectively putting you in a focus mode, also contributes to the pleasantness of the app.

## Typography
Discord provides a lot of accessibility settings, and the option to customize typography is one of them. Users can choose a font scaling, zoom level, and spacing. Text color also switches with light mode and dark mode so contrast is maintained.
![](/appearance.png){:width='600'}
You can view how the settings look in the same tab. This is how it looks for the "cozy" preset mode that Discord provides:
![](/cozy.png){:width='600'}
And this is how it looks for "compact" mode:
![](/compact.png){:width='600'}
This is one of the things that I think Discord does really well-- I've never seen another app with as many customizable accessibility features, especially with so many options for typography.

## Speak user's language
This is another category that I think Discord does really well in. There are better examples, but I picked an example in Discord's privacy and safety options, where it is particularly important for users to be able to understand each option without being an expert. Here, encryption is explained in a way that allows users to understand the general idea through clearly explained effects on their experience in the app.
![](/userlang.png){:width='600'}

## Consistency
My example of Discord's visual consistency is with buttons, which I discovered while reading [documentation](https://discordjs.guide/message-components/buttons.html#sending-buttons) for creating a Discord bot.
![](/consistency.png){:width='600'}
Forcing all developers to conform to a standard for button colors and icons allows consistency across all of the extensions that they create for Discord. This allows users to easily get used to the button colors and their associated meanings, and infer the effects for better safety/security. For example, users will learn that red buttons imply a destructive action, and will be more cautious when presented with a red button.

## Information scent 
Discord provides visual hints for navigation by highlighting the currently selected channel, and providing an indicator for the server that you are currently viewing.
![](/navigation.png){:width='400'}