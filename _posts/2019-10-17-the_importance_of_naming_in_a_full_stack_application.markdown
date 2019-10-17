---
layout: post
title:      "The Importance of Naming in a Full Stack Application"
date:       2019-10-17 10:40:52 +0000
permalink:  the_importance_of_naming_in_a_full_stack_application
---


Full stack applications are fun and complicated to build. As I built my final project for the Flatiron school, using React/Redux and Rails,  I struggled naming files and components either because I made it too confusing or it was not appropriate. I decided to look deeper into naming convention to finally get it right.

This was my first React project and I was excited to build with it.  There is no official guide to naming with React, although there is an understood guideline for it. Building the React components is where I ran into issues. I wanted to name a series of components "list", but then it became lists of lists, etc. What I mess I started to create, so off I went to look for help.  React is built on top of Javascript and so some naming convention should follow. I found these guidelines to be helpful:
 
[JavaScript Naming Convention Dos and Dont's](https://www.freecodecamp.org/news/javascript-naming-conventions-dos-and-don-ts-99c0e2fdd78a/)

 
One of my favorite tips was, “Will my program make sense tomorrow?”- to be specific about the naming so that you and other collaborators can understand more easily the flow of the project tomorrow (i.e. self ++ 1 day). Also using this specific wording can make RESTful naming conventions more seamless. There are so many good tips in the article as well as an excellent list of other references.
 
Other helpful tips:

- Filenames should be lowercase and may include (_) and (-)
- All components should be in PascalCase
	
As I continued to build, I was being mindful of my names and added a larger global state and Redux to the project. This article was one of my favorites on Redux naming:

[Redux Best Practices](https://medium.com/@kylpo/redux-best-practices-eef55a20cc72)

I worked on utilizing these tips into my actions and reducers.

	action type NOUN_VERB = ACTIVITY_ADD
	action creator verbNoun = addActivity
	selectors getNoun or selectNoun = getActivity
	

With the frontend finished, I needed to brush up on my rails naming conventions to tie backend together. Luckily Rails has a [well documented naming conventions](https://guides.rubyonrails.org/active_record_basics.html). For example:

- Class - CamelCase
- Methods and variable - snake_case
- Database tables snake_case and plural
- Models -CamelCase and singular
	
Another major aspect of naming convention is being mindful of the names you chose, making it simple and stream line. This will keep everything lined up as you build and make it easier for collaboration. An overlooked part also is the ease with which to  spell the names and use the convention for the language for a successful application build.  Using smart naming convention  can make the code easier to read and easier for others to understand. 


Other helpful links:

- [Structuring Projects and Naming Components in React](https://hackernoon.com/structuring-projects-and-naming-components-in-react-1261b6e18d76)
- [Alex's Rails Cheat Sheet](https://gist.github.com/alexpchin/f5d2be2ef3735889d315)

	



