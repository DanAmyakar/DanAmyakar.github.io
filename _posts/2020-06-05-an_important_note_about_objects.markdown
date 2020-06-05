---
layout: post
title:      "An Important note about objects..."
date:       2020-06-05 16:02:33 +0000
permalink:  an_important_note_about_objects
---


While I was writing and testing my CLI project I ran into an interesting error that threw me for a loop. Luckily I am familiar with pry some what and was able to identify this mind boggler. Not happy with the solution right now but learned something about how objects stored in an array are fetched by methods and what to expect when you forget about how data is represented.

First off, I used Age of Empires 2 API for my project. I used to play that game all the time. I figured the familiarity would be a step in the right direction for the first project. There are seven, yes thats right, only (7) seven things that act as different categories of items in the whole game. Civilizations, buildings, units, technology, the age a player is in, the map its self, and the resources on the map.

The Civilizations, units, technologies, and buildings are the focus of my program. Each of the four categories (classes) stores each object in an @@all (class variable called all, data type 'array'). That last bit is important, because it determins how you need to request that object.

```
#entering something like this:
my_obj = my_class.all.select{|obj| obj.id == x}
=> [#<some_object_whose_id=x>]   which looks a lot like the object we wanted...  
```

The issue, or iss-me I guess, is that this object is still in an array. Because this object is in an array, it wont be able to call an instance method. The way I went around this issue is by having the request actually grab the object at the index of x-1.
```
my_obj = my_class.all[x - 1]
=> #<some_object_at_index_(x-1)>
```

However, I am by no means an expert and this took me a long day to figure out. I am sure there are many methods that could fix this issh.

Until next time.
