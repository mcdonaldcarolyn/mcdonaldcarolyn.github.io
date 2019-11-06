---
layout: post
title:      "Put Your Back Into It: Using Rails as an API"
date:       2019-11-06 00:03:06 +0000
permalink:  put_your_back_into_it_using_rails_as_an_api
---


Rails is a flexible, strong, and fully featured framework. There are many ways to use it, but one of my personal favorites is as a back end API (application programming interface). In this blog post, I will explain how to set up a back end Rails API in just a few simple steps using the Rails CLI (command line interface).


## Step 1: Initial Saffolding

 If you already have Rails and its dependencies already on your computer you can just type the following in your console:

```
$ rails new my_api --api
$ cd my_api
$ rails g scaffold {model names here}
```

Basic APIs are typically built around database models. So, in the command above, replace `{model names here}` with the actual names of your database models. For example:

`$ rails g scaffold user product wishlist`

There are many different options for scaffolding that you can [read about here](https://guides.rubyonrails.org/v3.2/getting_started.html#getting-up-and-running-quickly-with-scaffolding).

## Step 2: JSON Serializer

Creating a rails project that will serve as a backend function and storage, means that some of the configuration will be different from a typical rails project. There is no need for views, so that section with not be generated. You will need to add the serializer for the correct API formatting. 

```
$ gem 'active_model_serializers'
$ bundle install
```

Now you have the basic elements to get your API up and running. 

## Step 3: Model Schemas

Build out your table and data using the input information being added by the user and organize in a way that will make it easy for associations to be made. 


 As you build your frontend think about the data that will be store in the back and how it connected. Is there data that relies on another input from the user, etc. It is with these thoughts that the associations are created in the backend. Utilizing the has_many or belongs_to macros can make working with the data much easier. Also using those macros and the data being added in the input params are an important part of connecting the frontend and the backend rails seamlessly. 

## Step 4: Calling Your API

Finally the connection from the frontend to the rails Api, this can be done in several ways. When I used React/Redux for my build and it is essential to use the correct connection to add to the Rails side of things. Using the router POST to create new data is example of the correct way to "talk" to rails.  

`TODO: add fetch call here to show calling out to the API`

Once you have your front end rolling, the rails backend is a seamless addition to a project. 

## Other Useful Articles and Guides

* [Using Rails for API-only Applications](https://guides.rubyonrails.org/api_app.html)
* [How to Make a Rails 5 App API-Only](https://hashrocket.com/blog/posts/how-to-make-rails-5-api-only)





