---
layout: post
title:      "Sinatra Project"
date:       2020-08-03 06:02:24 +0000
permalink:  sinatra_project
---


The model I chose to go with for this project was captains and ships. Captains have many ship and a ship belongs to a captain. There was a lot more I wanted to do with this project. I wanted to have Companies own Manifests of goods and be able to store those goods on ships in cargo slots. I wanted the cargo slots to fill up and tell the captain how many slots were occupied and I wanted the captains to be able to see the manifests on their ships without being able to modify them. I had a hard time with routs and I'm not sure I understand restful routs. But the pages do what I wrote them to do ships have full CRUD-ability while users as static once created.The Captain and Ship models both have a method called valid_params?() that runs the params keys against the db table to see if the values are good or not. There is also a redirect_in_not_signed_in method on all the controllers that checks the session[:captain_id} vs the current_captain_id. This was a cool little problem to solve and took me a while to figure out.
