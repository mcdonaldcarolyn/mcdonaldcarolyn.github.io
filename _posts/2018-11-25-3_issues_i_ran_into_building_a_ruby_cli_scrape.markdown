---
layout: post
title:      "3 Issues I Ran Into Building a Ruby CLI Scrape"
date:       2018-11-25 16:48:22 -0500
permalink:  3_issues_i_ran_into_building_a_ruby_cli_scrape
---


As part of the Flatiron School,  the CLI project is the first project students work on. It creates a CLI interface that allows users to interact with content scraped from a website. I was looking forward to building something outside the cirriculum, but I ran into several major challenges. Here are 3 of the biggest roadblocks I encountered and how I overcame them.





#### 1. Ruby Directory Permissions

As soon as I started to build the project I was running into several errors when I tried to run the code. 

```
NOTE]
You may have encountered a bug in the Ruby interpreter or extension libraries.
Bug reports are welcome.
Don't forget to include the above Crash Report log file.
For details:
```

The errors were with my ruby version or ruby in general. After alot of googling and asking for help,  I realized that using a second hand computer was a big part of the issue- I did not have the correct permissions to create the gem. I solved this by removing all gems and resetting permissions on the Ruby install directories:

```
sudo gem uninstall --all
chown $(whoami) /Library/Ruby/Gems/2.3.0
```

#### 2. Mac Environment

After fixing the permissions issue, I tried to install some of the gems I needed for my project. That's when I ran into this error:

```
3:~/lunch $ bundle install
You have one or more invalid gemspecs that need to be fixed.
The gemspec at /Users/carolynwhelpley/lunch/lunch.gemspec is not valid. Please fix
this gemspec.
The validation error was '"FIXME" or "TODO" is not an author'
git:(master)
carolynwhelpley@Jeffs-MacBook-Pr
```

Ugh! I continue to google and google- there were many suggestions. The key to overcoming this issue ended up updating my Mac to the latest version (Mojave) and upgrading Xcode. 


#### 3. Understanding the DOM

I got started by using the nokogiri scraper to grab the data from the site. Here is a simplified example of the HTML document I was scraping:

```
<div class="graphics-frame>
    <h3>Fish 1</h3>
		<div>Description of Fish 1</div>
</div>
<div class="graphics-frame>
    <h3>Fish 2</h3>
				<div>Description of Fish 2</div>
</div>
<div class="graphics-frame>
    <h3>Fish 3</h3>
		<div>Description of Fish 3</div>
</div>
```


This was my initial attempt to get  the correct data:

```
html = open ('http://fishwebsite.com')
doc = Nokogiri::HTML(html)
thing = doc.css(".graphics-frame")
thing2 = doc.css("h3")
```

I mistakening was thinking about ruby reading down for working the DOM tree and kept pulling out ALL the h3s.  I spent too much time trying to reread and rework the HTML code and not looking at my CSS selectors. Now I have such better understanding of this concept. 

#### Conclusion


This project really helped cement in for me a lot of these ideas. Once the correct info was pulled from the site, it was fun to manipulate the data and interact with the user. Creating a numbered list for the user to pull from and then looping through the responses and invalid possiblity to make a usable interface. This project was challenging for me, but I loved how it 



							

