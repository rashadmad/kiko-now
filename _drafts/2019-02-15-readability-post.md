---
layout: post
title: "Ruby on Rails: starter project part-1"
tags: [Blog, CRUD, Ruby, Ruby-on-Rails, Tutorial]
comments: true
---

![ruby blog](https://media.giphy.com/media/Vwz4zdntMXrUY/giphy.gif)

Tutorial getting started on ruby on rails part-1

## Why Read this

* If you aren't familiar with CRUD and want to learn more about it.
* If you are new to Ruby on Rails and want a primer.
* If you want a brief intro into MVC.
* just like my blog and want to support me :).

I will be working on a project in Ruby on Rails so I am going to need to be familiar with it. In particular how CRUD works in ruby on Rails. So what I will be doing is creating a blog in ruby on rails to gain familiarity

## Possible Obstacles
getting ruby on rails up and running can be the easiest thing in world or the hardest I won't be going over all of the issues that

* Getting ruby on rails working on windows computer
  >installing ruby on rails on windows can really be a pain sometimes your better off just either installing a virtual machine with linux on it or just working on a mac

* Installing Ruby on rails on your mac
  >You will need Ruby and Rails installed before starting
  I am not going to go over setting up ruby and rails on your system here is a good resource for that
  https://guides.rubyonrails.org/v5.0/getting_started.html

* Ruby on rails is an open source project and is constantly changing
  >these changes can cause things to not get up and running

## What is CRUD

Basically crud is an programming acronym for:

* Create
* Read
* Update
* Delete

You are using crud all over the web everyday. Twitter is a great example of crud

![twitter=crud](https://media.giphy.com/media/uTjpIPVMaYlBS/giphy.gif)

In twitter you
* _Create_ (to write a tweet)
* _Read_ (You write the tweet so it can be read by others)
* _Update_ (Twitter purposely does not allow you to edit your tweets. Just think if you retweet something nice and it was edited to be something mean that would suck)
* _Delete_ (Often people want to destroy the things that they create when they are not proud of it)

![rick and morty delete gif](https://media.giphy.com/media/xULW8N9O5WD32L5052/giphy.gif)  

I wont be creating a twitter clone, instead something more inline to the other things in this blog... a blog

## what is MVC

It is another programming acronym it stands for:
* model
* view
* controller

It deals with the data that you want to manipulate through CRUD. We will touch on MVC during this blog post but keep your focus on CRUD.


## Ruby on Rails blog walkthrough

First off If you want to go through this with me I would follow along with these set of treehouse tutorials by Jay McGavren [here](https://teamtreehouse.com/library/ruby-on-rails-5-basics)

if you don't have a treehouse account I do suggest it. It is a great tool for learning a great deal about WebDevelopment sign-up [here](http://referrals.trhou.se/rashadmadison) its only like $25 bucks a month. If you don't have a treehouse account don't stress you can still get a great deal out of this.

### Once you have Ruby and rails both installed

open up a terminal that can run ruby and enter or create a directory for your project in that directory enter this to start a new project called blog

```
$ Rails new blog
```
if successful you should have created multiple files and directories that will be read off in your terminal

Congrats you have created a Ruby on Rails app

![WOW](https://media.giphy.com/media/g9582DNuQppxC/giphy.gif)

lol Im sure that was not enough you want to do some CRUD so lets go in to the directory of the project that we just created and

On mac & Linux
```
$ bin/rails server
```
On windows
```
$ ruby bin\rails server
```

Alright For me the ```bin/rails server``` did not work basically there are multiple ways of starting a server and I had to use

```
$ rails server
```

The other ways did not work for me because I have multiple versions of ruby on my system.

When you have ran rails server in your project directory rails should be up and running on your browser at the url
```
http://localhost:3000/
```

You should see this
<img src="/images/yayRails.png" alt="yah! rails screen" />

Alright so you got rails up and running now and you have proof its up and running.

## Creating a ruby resource

first you need to stop the server using
```
ctrl + c
```

Now we shale create the most important part of our blog, "blog post". We will accomplish this using a  _ruby resource_ and _scaffolding_.

```
$ bin/rails generate scaffold Post title:string
```
or if you have other versions of ruby installed on your system.
```
$ rails generate scaffold Post title:string
```
```title:string``` is the attribute that we are giving to our resource. We will add more attributes later.

* _Title_ the name of the attribute
* _String_ the kind of data that we will be using

After generating the scaffold we should get a list of newly created items in our terminal. The main object I want you to take notice of is the ```db/migrate..``` it is responsible for running the post database table which deals with all of the data through our post.

lets start up our server agin to see are changes

```
$ rails s
```

oooh by chance did you get an error page.

![rick and morty delete gif](https://media.giphy.com/media/TqiwHbFBaZ4ti/giphy.gif)

no biggie we just need to run a the migration to create the table.

```
$ rails db:migrate
```
Now things should be back working agin check by starting up the server. Also now we should have post up and running as well check this by putting in this url to your browser.

```
http://localhost:3000/posts
```
You see what we did there. we added posts to the end of our url. So if we generate another resource in this fashion we can get to it in the same fashion.

![rick and morty delete gif](https://media.giphy.com/media/l41JU9pUyosHzWyuQ/giphy.gif)

We don't have a post created yet. Lets do that by clicking the new post link.
<img src="/images/posts.png" alt="post screen" />
Name the post anything that you like.

this is an opportunity for you to to pay around with _crud_ so create a few blog post, read them change them and delete them get your crud on.

Alright so your probably feeling jazzed about the new power you have. You can....
* create a rails app.
* create a resource.
* create attributes to said resource.
* and finally make CRUD changes to that resource that our non-coding buddies can enjoy

That sums up our post. I will be doing a part two deep dive breaking down what we really did and give you a deeper understanding of what scaffolding hides.

Thanks for following along.
