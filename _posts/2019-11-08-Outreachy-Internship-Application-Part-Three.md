---
layout: post
title: "Outreachy Internship Application Part-Three"
tags: [Outreachy, Frontend Webdevloper, Internship, Open Source,Z-index,design systems, Vue.js]
comments: true
# other options
---

![out-reachy-internship](/images/creativeCommons.png)

# My experience as an applicant to the Outreachy internship program **Part-Three**
Synopsis of my experience as a Outreachy applicant: **Developing a double range slider with out plugins and How important Z-index is for a design system**

## Starting work on the double range slider

![out-reachy-internship](https://user-images.githubusercontent.com/5515036/67452604-5b551b00-f5e9-11e9-8c33-c230c94aff7d.png)


Designing a double range slider is quite challenging. I can see why so many depend on things like jQuery and other libraries as tools to complete the task. My plan was to create one with just HTML, CSS and Vue.js. 

>p.s. I plan to create a tutorial with this at some point but this blog post will just go over the over all experience that I have had developing a double range slider. Mistakes made, things learned and my thought process. 

Here is a list of the problems I needed to solve to get my double range slider working. 

1. create custom styleing for the slider making sure it fits the astetic of the vocabulary design system (use the variables that are already supplied in the design system)

2. Have to turn a single range slider into a double

3. Have to create an effect that differentiates the min & max slider (basically create an effect between the slider knobs)  

4. Have to guarantee that what ever I do works on all popular browsers

5. Have to create a demo of said slider to be included inside of the Vocabulary design system

simple enough right... 

> One of the first lessons I learned from working on this project is to really read the documentation of a project. Often documentation on some open source projects can really 'well...suck' But that was not the case with vocabulary. The documentation is quite through actually. I would of had a much easier time with it if I studied the documentation more thoroughly when I started.

*First* - I needed
 to make the range slider fit the Vocabulary design system's slider here:
 
  ![slider-image](/images/sliderimage.png)

  so that means some custom styling. Vocabulary uses the *Stylus* CSS preprocessor which I didn't have experience in.
  
  ![stylus logo](https://upload.wikimedia.org/wikipedia/commons/d/d8/Stylus-logo.svg)
  
  >I have prior experience with SASS which is quite similar. It took me a while to adjust to the way stylus abstracts css. and also utilize the varibles that the project already has set up. Its funny how making something simpler can make it more confuseing. 

that was allot to take on all-at-once so I developed the slider in its own independent project here I created a single knob slider with Vanilla JavaScript with styling akin to the vocabulary style system slider that was already inplemented:
[link to repo](https://github.com/rashadmad/Vuejs-slider)


*Second* - I had to do a little hacking for this solution. I planned to create two range sliders combine them. To create this illusion I had to utilize on Z-index. 

here is the trick:
* you have two single range sliders placed next to each other in the html
* next I postioned them on top of each other
* so now I have four elements in my slider, two bars and two knobs, I have too use z-index to make sure both knobs reach above both of theses bars so they can be used.

*Third* - This part was optional but I still found it quite important. I wanted to create some sort of way of
making the slider bar darker in-between the two knobs. Doing this was actually quite difficult, But I am extremely proud of my solution:

> I came up with creating two bars animated with CSS that would change in size with the movement of the knobs. Ironically these bars needed to appear slender. So this is where z-index stacking comes in. These new bars that I create would need a background with a interchangeable color to make sure it goes with the background.

![range slider giff](https://user-images.githubusercontent.com/5515036/67452817-1087d300-f5ea-11e9-8bf2-534cc85c1094.gif)

The one caveat with this solution is that it depends on multiple z-index levels to function. When it comes to Z-index and design systems it makes very little since to to give one element multilpe levels of with z-index with out applying it to other parts of the system. I felt that I could not move foward on the double range slider without implementing some sort of Z-index system. So I stopped work on the double range slider and moved on to creating a z-index system to go along with the double range slider I created.

While developing this double range slider I learned a great deal about how vue.js handles functions and styling. Being the first real frontend frame work that I have really dug in to. I really appreciate how convenient it makes doing things that would of been a huge pain in vanilla JavaScript. I have completed my doulbe range slider and am know moving foward to implementing it into the Vocabulary design system.








