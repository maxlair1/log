---
layout: post
title: Life Update: Coffee, Homelab, and Novice Penmanship
description: Week-start update about life and things.
summary: Talk about rewriting wife's website, homelabs with Minecraft server, new house, and writing ability.
comments: true
tags: [life]
---

Happy Monday!

I wanted to publish a quick week-start update, and some other projects I am currently working on.

It has been a whirlwind these last few weeks. We have been jumping from life stage to life stage just a little too fast for comfort. From moving to our forever home (hopefully), to listening to the heartbeat of our soon-to-come baby #2, there is so much to do, and so little time. However, my relentless brain wont stop picking up new interests.

### Rewriting the infamous coffee shop list

This week I have been working on revamping [trails.coffee](https://trails.coffee), my Wife's gargantuan list of cafes. And yes, she did insist that they are ranked in chronological order. With more than two hundred entries. I'm a good husband, so I take on the tough design challenge that is a platform responsive, infinite list, that can be reordered and edited. Each cafe has a lot of content you can include. I even built a slot for photos, so she can upload some visuals from our visits! Below is an example of the cafe type if you're interested.

```typescript
// each Cafe entry at trails.coffee :)
export type Cafe = {
id: number;
created_at: string;
name: string;
images: string[] | null;
body: string | null;
date_visited: string | null;
city: string | null;
state: string | null;
address: string | null;
tags: number[] | null;
rank: number;
archived: boolean;
map_hidden?: boolean | null;
map_query?: string | null;
};
```

For the rewrite I am (like always) using React, but trying out [Bun](https://bun.com/) JavaScript runtime this time around. Additionally, structuring the UI with [Radix](https://www.radix-ui.com/) primitives. I'm new-ish to the world of server-side architecture, but thus far my golden goose has been [Supabase](https://supabase.com). It has a lot of tools, tutorials, and relevant packages to keep the layman (like me) on track. 

The challenges thus far have mostly been with touch, as she really wants an "app-like" feel to the site. Being able to add detailed entries on the fly is important to her. It's understandably essential to be able to jot down thoughts as they come. I've been tackling this by using some tried-and-true components like Emil Kowal's [Vaul](https://vaul.emilkowal.ski/) drawer. However, drag and drop is my next huge hurdle. 

I believe that I've overcomplicated the listing, by forcing table functionality. In reality, tables are not the best way to display horizontal, multi-axis data on mobile devices. Coincidentally, while working in Design Systems at Rey Rey, I am working on revamping the tables and DataGrids, meaning I now consider myself an expert (for this week). Cards using primary, secondary and tertiary column identifiers seem to win big when it comes to mobile display.

I'm excited to keep writing it, and if you want to check out the source for the original, please feel free to check out [my Github](https://github.com/maxlair1/coffee-trail)!
### Homelab and server-ing

I put up a Minecraft server. Again.

It's better though, I promise. People are really hooked this time. But I have arrived at a larger issue. I've created a fancy Docker stack, clean Glance homepage, but this optimization has consequences. I can't just type directly into the console like I am familiar with for docker-compose applications. To remedy this, I need a webGUI I can access outside of my local network. Apparently, I have been living under a rock because today I discovered [Flask](https://flask.palletsprojects.com/en/stable/). Flask is a WGSI framework for python, and it works exceptionally well for this use case. I strapped up a ultra-simple TUI-like interface to just view and interact with the Minecraft Server. It's working well... I plan to improve it as I go!

My future goal is to hook up some additional devices, then playing around with Docker swarm to improve the [dedotated wam](https://www.youtube.com/watch?v=wsO-Td0hqXo).

As far as my local server goes, one of the perks of moving means that I get a new server room. Glorious 9' by 9' of pure nerd playground. Soon I will explore building a custom server rack using angle iron and 3D-printed mounting brackets. Hopefully, It will be a dramatic improvement from the previous attempt.

### Writing, long-term goals, and farewell

The reason I am here, most likely writing for no one but myself, is to document, improve my writing skills, and carve out my little corner of the internet. I'll try to give frequent life-updates, and try to grow a greater appreciation of writing. It's another art form really.

Until next time internet!

*Max*

---
> "A mind is a terrible thing to waste. If you understand things about the world, you can change it." - Casey Simpson
