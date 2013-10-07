---
layout: post
title:  "Publish a Website in a day with HTML and Ruby"
date:   2013-10-07 12:32:01
categories: html ruby
---

How to publish a website online? Here's a quick and easy tutorial. Learn the basic of HTML, CSS and Ruby
and publish as simple website. 


Before getting started there are few things you need to install on your laptop:

* **Text editor** -  [Sublime Text][sublime-text]  is a good one and it's free.

* **Ruby**, **Rails**, and other programs using the [Rails Installer][rails-installer] 

* Sign up on **Heroku** and create an account. You only need to follow the guide till 
	*Step-3* of this guide: [Heroku Quickstart][heroku-quickstart] 


#Tools of trade: Terminal and Text Editor

The **Terminal** (Linux and Mac OSX) or **Command Prompt** (on Windows) is a powerful tool and helps
us communicate with our computer. Although it might seem complex it is actually easy to use. Locate
it in your computer (using "Finder" or "Find a Program") and run it.

## Create a folder (a.k.a. directory)

Let's start by creating a folder (or directory): On Linux and Mac OSX machines you'd have to type
``mkdir demo``. If you're using Windows you'd have to type ``md demo``. Remember you also have to
hit the *Enter* key to execute the command. After that, you'd have to change the *working directory*, 
ie. the current folder where you'll be typing the commands. Just type ``cd demo`` and hit *Enter*. 

## Opening a Project

You've now create a folder called ``demo`` in your computer, and it's now time to run **Sublime Text**, 
choose *File > Open* and open the folder called ``demo`` (usually that would be in your home folder!). 
You should see something like:

<div class='center'><img src="{{ site.baseurl }}/images/sublime-text.png" /></div>

## Setting up Heroku

Heroku will take care of hosting your application or website. You'd need to create an account and setup
your computer. Inside the folder ``demo`` you'd have to type the command: ``heroku login``. 

The command ``heroku`` will then be executed. It might be possible you'd see something about generating 
public keys. If that's the case, just type ``yes`` and press *Enter*. The reason why you need to create 
a set of public/private keys it's because Heroku needs it (otherwise you won't be able to publish your
website)


#Ruby and Sinatra

**[Ruby][ruby]** is a programming language. We use Ruby to write code. **[Sinatra][sinatra]** is a 
micro framework written in Ruby and we use it to create our website.

> **Backend** is the code written to handle database connections, email confirmations, and
routing of URLs. **Frontend** refers to HTML pages, images, CSS styles and Javascript.


### **Gemfile** and **site.rb** files

Create a new file using Sublime Text. You can right right on the ``demo`` folder and click on *New File*.
Save the file with the name ``Gemfile``. **Note**: the name of the file is capitalised, it's important!

Your *Gemfile* will contain this code:

{% highlight ruby %}
source 'https://rubygems.org'
gem 'sinatra'
{% endhighlight %}

The *Gemfile* specifies how to download and install *Sinatra* on your computer.

Create another file (under the ``demo`` folder). Save the file with the name ``site.rb``. It will have to
contain the following code:

{% highlight ruby %}
require 'sinatra'
get '/' do
  "I'm alive!"
end
{% endhighlight %} 

The *site.rb* file is a working program, that display the string "I'm alive!". It's written in Ruby and
it uses Sinatra to handle the web requests.

> **Note** - Remember to save the files after you've changed their content! 


## Start the server

You still need to install **Sinatra** (and few other packages). In the Terminal (or Command Prompt) type the command 

{% highlight bash%}
bundle install
{% endhighlight %} 

You'll see a list of packages (**gems**) being installed in your computer. After the installation 
is complete, you can *start the server*. You'll do it by typing the command: 


{% highlight bash%}
ruby site.rb
{% endhighlight %} 

If everything is setup correctly you'll see something similar to the following message:

{% highlight bash %}
Sinatra/1.4.3 has taken the stage on 4567 for development with backup from Thin
Thin web server (v1.5.1 codename Straight Razor)
Maximum connections set to 1024
Listening on localhost:4567, CTRL+C to stop
{% endhighlight %}


Open up your browser, and go to ``localhost:4567``, you should see the "I'm alive!" message.
Congratulations. That's a very simple web server, running on your local machine!


# HTML and CSS

Showing a simple message can be fun for a while, but it would be better to show and actual
**HTML** page. Sinatra makes it easy, just create a ``public`` folder inside ``demo`` and 
you're ready to go. 

> Note, you can use Sublime Text and right click on the ``demo``
folder. 

Inside the *demo* folder, you need to create a filed called ``index.erb``. The content 
of the ``index.erb`` file can be something like this:

{% highlight html %}
<!doctype html>
<html>
<body>
    <h1> This is a title </h1>
    <p> 
    	This is a paragraph. And the following is a link at 
    	<a href="http://coderwave.com"> Coderwave </a>
    </p>
    <p> You can also show images, like the following one </p>
    <img src="http://placekitten.com/g/200/200" />
</body>
</html>
{% endhighlight %}

The result is the masterpiece shown in the following image: 

<div class='center'><img src="{{ site.baseurl }}/images/index-page.png" /></div>

# Deploy

If you'd like to publish your website online (in technical terms: *deploy*), you only need to run few
commands from the Termial (or Command Prompt)

* ``git init``: This will initialize an empty **git** repository
* ``heroku create``: This will create your website on Heroku

After you've created the website (another term is *application*), you should see the url in the 
Terminal. It will be something like ``http://cloudless-forms-1234.herokuapp.com``. This url 
will be automatically generated for you by Heroku. 

## Publish the changes

You now have a name of a website on Heroku, but you still need to publish your website. That's also
easy. Again in the Terminal, you need to run these commands:

* ``git add .``
* ``git commit -am "first commit"``
* ``git push heroku master``

Hopefully everything went according to the plan, and you should see a message in your Terminal 
that looks similar to this:


{% highlight html %}
-----> Compiled slug size: 12.5MB
-----> Launching... done, v90
-----> Deploy hooks scheduled, check output in your logs
       http://cloudless-forms-1234.herokuapp.com deployed to Heroku
{% endhighlight %}


# Conclusion

Point your browser to the url created for you by Heroku, and it will appear. The website is now online. 
As you've noticed, it only takes less then a hour to write some HTML and publish it online. If you'd
like to style the page with CSS you can also do it, but it will be the topic of another post!


[sublime-text]: http://www.sublimetext.com/
[rails-installer]: http://railsinstaller.org/en
[heroku-quickstart]: https://devcenter.heroku.com/articles/quickstart
[sinatra]: http://www.sinatrarb.com/
[ruby]: https://www.ruby-lang.org/en/
