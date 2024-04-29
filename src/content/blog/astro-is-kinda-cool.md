---
title: 'Astro is kinda cool'
description: 'Using astro was easier than I thought.'
pubDate: 'Apr 29 2024'
---

Throughout the years I tried numerous platforms to try blogging. Starting from obvious ones like wordpress, going to [hugo](https://gohugo.io/) and [statamic](https://statamic.com/). It was always either pain to setup, maintain, or use. I've kept my eyes on astro since it was released and the idea of having static sites which still has javascript available was always appealing to me. So here I'm.

## Setup
It was surprisingly easy. `npm create astro@latest` was kinda everything that needs to be done. Then u are ready to go.

## How it works?
Actually. *Magic*.  
  
You get astro files. They always start with this kind of funky header.

```javascript
---
import BaseHead from '../../components/BaseHead.astro';
import Header from '../../components/Header.astro';
import Footer from '../../components/Footer.astro';
import { SITE_TITLE, SITE_DESCRIPTION } from '../../consts';
import { getCollection } from 'astro:content';
import FormattedDate from '../../components/FormattedDate.astro';

const posts = (await getCollection('blog')).sort(
	(a, b) => a.data.pubDate.valueOf() - b.data.pubDate.valueOf()
);
---
```	
This seperates the logic from the content. This is being calculated and pre-compiled as I said - *Magically*. Once it's done, static file is served to you. This enabled huge amount of flexibility, meaning you can write an actual logic, if you need to, whilst still keep the performance of static site. They also have AstroDB which is SQL database made specifically for astro websites. From my understanding it's just fancy wrapper around SQLite with some *magic* on top of it.

Setting up and using astro is ridiculously easy, and I would recommend this even for presentation webs. We're also using it for our community website and I wouldn't be scared to use it as product website. 

With that being said. If u are looking to experiment, I would highly advice using astro and trying it on your own. You can view [source code](https://github.com/TheMartes/blog.themartes.com) to see if you like the structure and vibe, but honestly, really good developer experience.

10/10.