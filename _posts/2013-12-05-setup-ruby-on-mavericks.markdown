---
layout: post
title:  "Setup Ruby and Bundler on OSX Mavericks"
date:   2013-12-05 13:34:05
categories: ruby
---

Here's how you install Ruby and Bundler on OSX Mavericks.

## Install the XCode command line tools

Open the Terminal (you don't find it? search for it using Spotlight!), and type the following command:

{% highlight text %}
xcode-select --install
{% endhighlight %}	

You should see a pop-up, click on **Install**. When the installation is completed, you need to 
type the following on your Terminal to install **RVM**

{% highlight text %}
\curl -sSL https://get.rvm.io | bash
{% endhighlight %}

You'll see a list of 'dots' on your screen, that's fine it means it's downloading and installing
the software.

## Are we there yet? No, we need to install Ruby

Almost, it's now time to install **Ruby**. After _RVM_ has been installed, you still need 
to use the Terminal and install Ruby on your machine. Type the command:

{% highlight text %}
rvm install 2.0.0
{% endhighlight %}

Now you should have Ruby installed. This command will
set the 2.0.0 as the default version:

{% highlight text %}
rvm use 2.0.0 --default
{% endhighlight %}

## Are we there yet? No, we need to install Bundler

Last thing to do, we need to install **Bundler**. Again, in the Terminal:

{% highlight text %}
gem install bundler
{% endhighlight %}

Now you should have Ruby and Bundler on your Mac OSX Mavericks.


## There's an error! It says XYW! 

Fear not, Google and StackOverflow are your best friends, search
for that particular error and with a bit of luck and patience, you'll find how to fix it. 
Write a comment, and we'll see how to solve it.
