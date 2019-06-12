---
layout: post
title:      "Connecting the Dots"
date:       2019-06-12 14:29:09 +0000
permalink:  connecting_the_dots
---


#### Understanding the connections between your JS and Rails in the JS/Rails project. 
-----------------------


As a Flatiron student, I was looking forward to the Rails/JS project to continue to work on my Rails app while building with my new javascript skills. As I went through the requirements and started to plan- I realized I needed to step back and really think about the bridge from "javascriptland" to "rubyville". 

I always like to start with the flow of the app to get a deeper understanding. Here is an example of a flow that includes Ruby and JavaScript:

1. A browser makes a request for a particular URL
2. As the app loads it first hits the environment routes
3. The routes send it to the controller
4. The controller loads the corresponding view or the JSON that is to be displayed. Within the controller the respond_to indicates what to render. 
5. In the views, the HTML and Javascript work within the DOM to utilize javascript's strengths with non page refresh drop downs and forms. 

It allows for very rich interactive page for the user. Within these steps there are a few key concepts that are worth diving into further.

### Respond_to 

This is a very important rails method. It allows Rails to determine the desired response format from the HTTP Accept header submitted by the client. If the client asks for html, it displays html, allowing you to send multiple formats to one view. Within the responds_to block you can render the specific view from the specific language or format. This addition to your controller is essential is any Rails/JS project. 

```
respond_to do |format|
	format.html {render :show}    
    format.json {render json: @variable}
end
	
```

### jQuery Selectors

The DOM is an object oriented representation of a visual webpage, which can be manipulated by Javascript. Javascript can interact with the DOM and Rails can generate the HTML, which in part creates the DOM. JQuery is a library that makes it easier to interact with the DOM. Using Jquery selectors, JS can specifically work with one or more element. After an element(s) has been selected it them can be manipulated through javascript functions. This is key to magic that is a rails/js application. 

=================

Selectors | Code | Captures
----------|------|----------
   *	           |$("*") |all elements
#id           | $("#")| all elements within an id
.class      |$(".")   | all elements with a class
element |$("p") | all `<p>` elements
                 |$("h1, p.bar, span")| all `<h1>` but just the `<p>` elements that are in  `class="bar"`

### Asset Pipeline/Application.js
Rails uses the application.js file to organize and manage all the JS, CSS, or HTML files. This streamlining of the these files allows Rails to easily access all files it needs. The order in which these are leaded is *important*. The require_tree . will include all .js files included in that folder.
```
//= require rails-ujs
//= require jquery3
//= require activestorage
//= require turbolinks
//= require_tree .

```
### Remote:true
I did not use this in my application, but it did come up a lot in my googling throughout this process. This a built in Rails helper that stops the default actions and instead runs the Javascript code. This does require the addition of a js.erb file and added code to assure the code comes back in correct form. This is an alternative to using the asset pipeline and loading everything in to the application.js file and that must be disable in order for this to work. 
```
<%= form_tag({:controller => 'my', :action => 'my_data'},:id => 'filter_form', :remote => true) do %>
```

### Conclusion

There are many other helpers, methods, and files that allow all the power of the JS/Rails app to work so well. Using Rails and Javascript together can give a programmer lots of options and flexibility for building dynamic web apps.  It can reduce the size of the request response cycle to make larger web apps run more efficiently. I am looking forward to building some awesome stuff with it. 


