---
layout: post
title: "Outreachy Internship Application Part-Two"
tags: [Outreachy, Frontend Webdevloper, Internship, Open Source]
comments: true
# other options
---

![out-reachy-internship](https://user-images.githubusercontent.com/5515036/67452604-5b551b00-f5e9-11e9-8c33-c230c94aff7d.png)

# My experience as an applicant to the Outreachy internship program **Part-Two**
Synopsis of my experience as a Outreachy applicant: **Beginning work on double range slider component in vue.js**

## What is a double range slider

![Click this to go to the outrechy website](https://i1.wp.com/www.cssscript.com/wp-content/uploads/2016/06/multirange.png?zoom=2&fit=474%2C351&ssl=1)

### First lets talk about a regular range slider

Depending on your experience on the web I am sure you have used a range slider. Range sliders have degrees of options. These are great for changing the volume in a music app, or choosing the price for a product and anything that requires the increase or decrease of a value. Also range sliders just feel good to use, I mean they definitely beat just putting in a number value in.

This is an example of a range slider here.

![range slider](https://forums.tumult.com/uploads/db2156/original/2X/6/612cfae4c6a0348dab0d271162bbd072bf2ade8c.png)

## How should I go about this

my goal is to create a double range slider. The big difference here is that there is no native solution for a double range slider out of the box in HTML. There are solutions in jQuery and other plugins though. I usually look to create things with HTML/CSS and vanilla JavaScript. Which means allot of hacking.

I decided to take a look at the project specifications, seeing as I was new to Vue.js
I was thinking instead of relying on JQuery or a plugin it may be better to lean on Vue. While looking through the project trying to find the best solution I found this in a readme file:

> Elements are nothing but relatively simpler Vue components and consequently live 
in eponymous folders containing `Element.vue`, `Element.md` and `Element.styl` 
files. Elements never bundle translations.
Elements may not import other elements, because that would violate the atomicity
principle.

After, reading this it sounded like going the vanilla JavaScript direction was the right way to go. So it seems that I went the right route in making my component entirely independent. The term "atomicity principle" caught me off guard, so I googled it and found this beautifully designed article by [brad frost](https://bradfrost.com/blog/post/atomic-web-design/). The gist of atomic design is that when it comes to creating design system there are five different levels: 

1. **Atoms** - *Exp: Color, text, shapes*
2. **Molecules** - *Exp: Buttons, Input fields*
3. **Organisms** - *Exp: Forms, Headers, footers*
4. **Templates** - *Exp: Wireframe, prototype*
5. **Pages** - *Exp: About page, Profile page etc..*
____
To make a long story short the idea is to create modular components "atoms"  that combine to create collections of "Molecules". Here is an example of this: 
let's say a users wants to buy a home on real estate site. That user wants to search for a home in a specific price range. They could use my double range slider to input that minimum and maximum amount they are willing to spend. Furthermore, its very unlikely that a person wants to buy a house just for its price. They may also want a input field where they can search for the location of the home they want to buy. 

>![atomicity principle](https://bradfrost.com/wp-content/uploads/2013/06/atomic-design.png)

They may also want to search by how many bedrooms there are in the home which can be completed with a few radio buttons. The input field, radio buttons and the double range sliders are all examples of **elements** or molecules. All of these in combination will form a **organism**. This organism would be called a form. I can go over the other levels of the hierarchy some other time but you should get the gist of **atomicity principle**.
____

so with that out of the way, the big take away here is that I am not just creating a component I am creating *"element"*. *elements* can consist of *atoms* so furthermore my slider can have a color or a z-index property but still making this element as Independent as possible is very important for the atomicity principles. So I should avoid Jquery plugins.

Thant means there will be allotof hacks. Furthermore I will get into how I solve the problem with code in the next chapter but here is a preview. Of what I got going in Vue.js

![range slider giff](https://user-images.githubusercontent.com/5515036/67452817-1087d300-f5ea-11e9-8bf2-534cc85c1094.gif)






