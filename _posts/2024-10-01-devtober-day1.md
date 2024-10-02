---
layout: post
title: devtober-day-1.md
date: 2024-10-01 15:51 -0700
rich-title: Devtober Day 1 - Planning and Plotting
subtitle: "Thus begins the madness..."
categories: [devtober, devlog]
---

For the uninitiated, [Devtober](https://itch.io/jam/devtober-2024) is an annual game development challenge where you work on a project every day for a month, in a similar vein to events like Inktober. Per their itch page the "rules" are:

> - Work on a game a little every day
> - Post your progress on social media
> - On the very last day, write a post mortem

For my Devtober, I've opted to do my social media updates on [Bluesky](https://bsky.app/profile/realityshift.bsky.social), but I also wanted a place for longer form updates and for my post mortem. As a result, I'll be putting those longer form posts here at the end of each week, as well as this introductory post and the post mortem.

With introductions out of the way, time to get into the meat of things: what am I planning for Devtober.

---
<br>

**Planning**

In the lead up to Devtober, I've been learning how to work with the [Bevy Engine](https://bevyengine.org/) for Rust by making a little pong clone in it. Initially I followed a [tutorial from TaintedCoders](https://taintedcoders.com/bevy/pong-tutorial) as a jumping off point before using it to explore some more of Bevy's systems as well as 3rd party plugins for things like collision. 

<figure>
{% picture posts/2024-10-01-devtober-day1/bevy-pong.jpg --alt A grey software window with a white ball bouncing off white rectangles. A score display shows 1 point to 0 points. %}
<figcaption>Behold: Pong! — <a href="https://github.com/TheExistingOne/bevy-pong">Code on GitHub under MIT.</a></figcaption>
</figure>

For Devtober, I'm planning to build off of that experience and move into 3d with Bevy. I don't think I'll make a full game or prototype but instead I'd like to set up a template and framework for me to build off of in future projects. 

My reason for this is that Bevy is a incredibly modular, yet pretty bare-bones engine. This makes it extremely powerful but also pretty slow to get started on a new project with. It also leaves you to implement a lot of things, such as collision, yourself or through community plugins. To remedy this somewhat, I'd like to build myself what will amount to a utility library to make getting started on future projects much faster. 

I'll start off simple by making a 3d project template with libraries and build toolchains pre-configured, then expand into adding some basic helpers and ECS bundles to make routine tasks like setting up collision with Avian easier. 

I don't want to aim too high for my hard and fast goals in case I get stuck along the way, so that's my general plan for the month. However, that doesn't mean I don't have additional pipe dreams/future goals:

---
<br>

**Plotting**

While I'm starting off this framework simple, my dream is that I can progress this to a grab-and-go toolkit for my work in Bevy with pre-built functionality for common elements and game behavior. 

If I happen to get that far, my focus is to support a kind of retro/mixed-media game aesthetic along the lines of Quake and [jdh's Altered Sensorium](https://www.youtube.com/watch?v=PcMua73C_94). Given this focus, I'm tentatively calling the project Dither, although we'll see if that sticks.


That's the gist, so off to work. See you around!