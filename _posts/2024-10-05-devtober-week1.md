---
layout: post
title: devtober-week-1.md
date: 2024-10-05 19:00 -0700
rich-title: Devtober Week 1 Retrospective
subtitle: "It's time to start dogfooding"
categories: [devtober, devlog]
---

A week of Devtober has gone by already, albeit a short one. It's been a pretty busy week for me so I haven't gotten as much done as I would have liked to, but that doesn't mean I have nothing to show. Additionally, I've already learned a few things about my development approach that I'm going to be changing going into week 2.

If all of this sounds alien to you, you may want to look at my [overview post]({% post_url 2024-10-01-devtober-day1 %}), otherwise let's dive in.

--- 
<br>

**What I planned for**

The project I set for myself this year was to create a development library (which I've tentatively named Dither) for the Bevy Engine to help me make games faster in the future, rather than a game itself. That last part is the first and probably largest mistake I've made so far but we'll get to that in a bit.

To that end, I set a couple of core goals for that library:
- A template for Bevy with the core toolchains setup and working out of the box
- Some basic helper functions to assist with common tasks
- Rapid-prototyping bundles to help with basic setup and collision

---
<br>

**What I've done**

The first and biggest thing I've gotten up and running is a system for creating basic objects. With just under half the code, I can now create one of several different primitives complete with collision and physics. This kind of rapid prototyping tool was a big focus for me because Bevy's built in PbrBundle can get a little verbose and requires a fair bit of boilerplate. Of course, this system can't do arbitrary meshes but for blocking out a scene quickly, that's just fine.

<figure>
{% picture posts/2024-10-05-devtober-week1/templates.jpeg --alt A blue cube, sphere, and torus floating on a gray void next to computer code %}
<figcaption>A couple of objects created with the new system - Click to enlarge</figcaption>
</figure>

My other big accomplishment this week is getting a basic project compiling on Windows, macOS, Linux, and WASM with build instructions for each. This sounds deceptively simple but getting an actually optimized build from Bevy on all of those requires a fair bit of fiddling so having it all set up is a relief.

I was somewhat surprised to discover that the hardest build to get working was WASM, not because anything should have been especially strange but because it refused to play nice with Windows. It turns out that trunk-rs, the WASM packager I'm using, has a bug that causes the `trunk serve` command that you'd use for testing to crash unless you either create the compilation directory for it or run `trunk build` first. This only affects Windows and is very confusing, but luckily I was able to work around it by using a dummy file to commit the directory to git so that it shouldn't occur again.

Finally, while a bit of a smaller objective, I also built out some helper functions to create game windows and related components much faster which should be pretty helpful going forward.

All in all it was a pretty productive week. In fact, if you look back up at the list of goals for the month, after 5 days all of those are to some extent included in Dither. Whoops.

Now, to my credit I did include some stretch goals in my day 1 outline, but they were quite vague. This was the second big mistake I've made in the first week.

As you may suspect, this is going to require some pivoting.

---
<br>

**Lesson 1: Outlining**

As that last section suggests, one issue I encountered was under planning. In the process of trying not to bite off more than I could chew, I aimed to do too little.

I don't think aiming too low was necessarily the problem, as doing too much really can be an issue. Instead my problem was that I didn't outline the project well enough. If I had set my original goals and then outlined the project more completely, I could have reached this point and picked more tasks off my outline and continued on.

This isn't too hard to fix, in fact I sat down earlier today and actually wrote up some documentation and goals for Dither, complete with full descriptions and reasoning. That will give me a much stronger development direction, but also means I'll probably be going back and refactoring some things that I could have gotten right the first time.

In the future, I'll make sure to put more time into outlining so that I don't cause problems for myself down the road

---
<br>

**Lesson 2: Dogfooding**

I alluded it briefly in the first section, but there is a larger problem than just not outlining well enough. That was my decision to only focus on Dither, and to not make a game alongside it.

My concern was that trying to prototype a game at the same time would spread my attention too thin and make it difficult to make progress on either. Instead I hoped to get by with prototyping small systems to check features, but this hasn't been working as well as I hoped. Not using my library in a larger capacity is making it hard to see what areas need work and what features are most needed.

To address this, I'm going to adopt the classic development approach of dogfooding[^1] by doing the one thing I explicitly planned not to do this month: make a game.

As slightly insane as that sounds, I do think it's the only way I'm going to get Dither where I want it to be. The point of it was to help me make games faster and better than I can now, and using it for that purpose seems like the best way to figure out where the gaps are. Dither will still be my main focus, but I'll be working on and sharing progress on that game at the same time.

My big takeaway from this is that if I don't intend to use a tool in isolation, I probably can't develop it in isolation

---
<br>

**Lesson 3: Documenting**

The last thing I encountered this week was not a problem, but instead a strategy that I'm finding helpful going forward: writing end user documentation. Documenting your project is good, of course, but I've found it weirdly helpful to sometimes write documentation that I probably won't need. 

I found this out when I was getting builds working across platforms. As I worked out the commands for each system, I wrote up build documentation in the README like I was showing someone else how to compile my project. It's probably not something I'll go back and look at much, but by the end of it I found that I had better internalized how I had laid out my build system.

This makes some sense, as writing things out does help you remember them but it was still surprising how useful I found it. Going forward, I'll probably be writing a lot more down.

---
<br>

At the end of the first week, I'm feeling pretty confident. I've gotten a little bit done every day and while I'm making some big changes to my project, I'm glad I figured them out now instead of later.

If you're interested in keeping an eye on my in-the-moment progress, I'm posting updates as I work on [Bluesky](https://bsky.app/profile/realityshift.bsky.social), and if you're interested in Devtober check out their [Itch page](https://itch.io/jam/devtober-2024).

Now it's time to get back to work. See you around!


[^1]: Using your own tool to gain a better understanding of how it works and how best to improve it.