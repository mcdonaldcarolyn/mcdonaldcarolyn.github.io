---
layout: post
title:      "Routes for beginners"
date:       2019-02-04 18:14:08 +0000
permalink:  routes_for_beginners
---



		https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSNAw9UIp2myUR0hNNnrSLJr1sfaUWaIoZ8V8Nzvp2gJQIZaMis
	
	
	       	Routes and routing are the backbone structure of web applications that experienced developers easily use, but can be a trickier concept for developers just getting into creating dynamic pages. I want to break them down and explain them so even an eight year old can get an idea of how they work. 
		
	       Routes are the way a users request on a web page or application are linked to the page that matches the requested page. Using a ruby method, mapping is created to all the possible requested pages are put in the controller/router to create the system where all the pages are connected. Each user-facing web application needs a get and a post route in order to fulfill the users request. These are referred to as HTTP verbs. All HTTP verb and routes will have some code block to perform. 
				 
 get '/new page' do
  .. show something code block.
end

post '/newpage' do
  .. create something code bock..
end

patch '/newpage/id' do
  .. modify something code block.
end

delete '/newpage' do
  .. delete something ..
end

	
		    I initially had a tough time wrapping my head around what a route does and why creating apps is set up in this way. Thinking about routes as almost a mail system really helped. For example, let’s say a particular web app is a 4 condo building with a manager living in the 5th apt. People often receive and send back pieces of mail that they sent. For this example they almost always do and it is immediate. Most days the Manager(home page) greets the mail carrier(user) and is always available to assist. The mail carrier checks the mail for the address they want. As the mail person “gets” the address and goes to the apt, they then receive the “post” mail to go somewhere else. Often as this building people send their neighbors letters. So the mail person visits all the apartments and is directed by the route/address  where to go and get what else they need.  Sometimes changes/patches to the address are written by the mail carrier and the mail is sent along its way without any issues. This idea has really helped me understand the importance of all in the individual routes for each view and how they need to both interact with itself and other views.  
	
	Soon you will be old hat at routes once you get a feel for using them- “Get” to work!

![](https://www.gettyimages.com/detail/photo/male-postal-worker-looking-at-mail-royalty-free-image/81896823)

		

