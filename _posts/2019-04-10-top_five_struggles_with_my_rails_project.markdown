---
layout: post
title:      "Top Five Struggles with my Rails Project "
date:       2019-04-10 22:07:23 -0400
permalink:  top_five_struggles_with_my_rails_project
---


#### What is Ruby on Rails?

Ruby on Rails is a web framework built on top of the Ruby language. It relies heavily on convention and common patterns like MVC and REST to make web app development easier. In fact, a primary goal of Rail is to help [make the developers happier](https://rubyonrails.org/doctrine/).

Rails is made up of [several pieces](https://insights.dice.com/ruby-on-rails-fundamentals/) including:

* *Action Pack* - Routing, tempaltes and controllers (i.e. the V and C in MVC)
* *Active Model* - Models (i.e. the M in MVC)
* *Active Record* - Object relational mapping to glue your models to your database

And, of course, Rails projects can leverage the rich ecosystem of [Ruby gems](https://rubygems.org/).
	
#### My Top 5 Challenges

Here are the top five things I struggled with when building my Rails project and how I figured them out

1. *Rails Macros*- This is part of the rails magic I am still getting comfortable with. Macros are class methods that create new instance methods. Rails tried to make it easy to access the data in the database through the model and creates and methods based on the fields of the database.  has_many is an example of a macro usage. 
2. *Join tables* -  I used a join table so I could access 2 major databases both together and separately. The overall idea is crystal clear to me but saving one item through the join table was very challenging in the nitty gritty detail and I build the methods for this wrong several times. It is great to be able to create several types of routes for awesome restful convention and super easy use for the user by using nesting the routes and creating stand alone routes.  The join table allows additional information to be added to the information from the user but doesn't mess too much with the pure database info. 
3. *Using devise and Omniauth together* - I found these to be like oil and vinegar- better together but hard to mix. I had install devise in first to handle a lot of the user interface and build the omni auth last and I ran into a lot of trouble adding the user information from the 3rd party onmiauth into the devise. I also felt like there were several layers deep I could add the 3rd party info and wasn’t sure how deep to create the user info for this simple app. I ended up rewriting the 2 together and it was much easier. Devise does need to part of the installation of other omniauth gems and likes to be in on all the comings and goings in the app. 
4. *Delete routes* - I think every delete function I built took several tried to get it to work. This was another area where the join table make it a bit trickier to create the just right path to delete the item. When deleting an item from nested routes or through a join table, make sure to pass in both the parent and the child  objects. 
5. *Using scope methods with several databases* -  I wanted to create a simple scope to pull out certain items from the database that did not include items from the second table- this proved very difficult.- again those tricky join tables. 

```
def self.vegetarian
    where("id not in (select meal_id from meals_ingredients mi inner join ingredients i on mi.ingredient_id = i.id where i.name in ('chicken', 'steak', 'beef', 'ground beef'))")
end
```

phew that was a doozy.  I look forward to being able to better parse out some of the data from the user using scope methods. I forsee many ways people would want to organize their meals and scopes will be essential with this. 

#### Conclusion

I was very challenged and frustrated by this project, but am hoping as I continue to use Rails i can appreciate all that it can offer. 



