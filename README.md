# ConnorHillen.github.io

Hey you! Looking at my Github! I like you. You know why? Because it's always
good to see somebody reading the README I put so much effort into! I'm not
sure what you expected to see on a README for a personal website, so I 
hope this will satisfy. This website is entirely front-end and hosted by
GH-Pages.

## About Me

I'm Connor. I like to teach, code, write, and cook. My website is pretty basic,
and doesn't really need a lot of explanation for most people; however, things
get interesting if I assume you *aren't* most people. Maybe you're looking to
learn something about development. Maybe you're interested in learning how
to host a Github page. Remember how I said I like to teach, code, and write?
Well I'm alllll out of curry, so let's get to those.

## Goal

I like to teach. I think everything should be a learning experience; however, I
don't think I should be the only one learning! I know a few fellow students
have taken to checking out my Github to learn some code, and I want to make 
sure the record is set straight on what I've done, *why* I've done it, and 
ensure that if I made a decision you don't just think it was right and move
on. I'm going to rant a bit about what I dislike about my personal site, and
ways it could potentially be improved. I'll also have a bit of a TODO which I 
can stare at and pretend I'll get around to sometime. 

## History of the Web, and Understanding Modern Applications

### What is Front-End Development?

If you've taken a web app development course with certain professors, you may 
have been thrown into an application with a backing server and front-end and
couldn't tell the difference between a markup language and an AJAX request. 

Fear not! I'm going to try to help you understand a little important tidbit
about web app development.

A basic web application is comprised of two main parts: A back-end, and a 
front-end. Put simply, the front-end is what the user browsing your website
sees when they load your page, and the back-end is what the user is downloading
the website from and what decides what is sent out. It's the part that Reddit
hugs to death when a link get unexpectedly popular. 

Front-end development is further broken down into smaller sections, which I'll
talk about after. First, it's important to know how the modern website evolved
into what we know it as today.

### A Brief History of WWW

Web application development has evolved tons over the last two decades. 
A quick look at 
[the first website](http://info.cern.ch/hypertext/WWW/TheProject.html) shows
what websites were intended to be. Simple documents served to the user with
links to other documents. It's basically just a fancy PDF! Well, these simple
documents evolved into 
[very sophisticated works](http://www.oocities.org/area51/1075/) upon releasing
publically. Still, these were just links, images (which are just links which
get rendered differently from normal links) and styling (which, you guessed it,
are linked in). [Modern web applications](http://reddit.musicplayer.io/) can do
so much more. The field has changed. 

It's important to know how those older, document style websites were actually
operated, developed, and maintained. This lays the foundation for modern 
applications. 

An older website's directory might be extremely simple. For example:

```
./index.html
./about.html
./contact.html
./style/style.css
./images/logo.jpg
./images/banner.jpg
./sounds/annoyingSong.midi
```

In this, we are given three **pages**: index, about, and contact; all of which
are written in Hypertext Markup Language, **HTML**. To style the pages, they
would be given a Cascading Style Sheet file, **CSS**, which would replace the
default style a browser renders certain elements and replace it with something
a bit more personal. For example, if you want to be super cool and make every
header on your page a wicked awesome, super big, neon green, comic-sans, blink
title -- you can!

You see, everything in HTML is wrapped in *tags*. These tags tell the browser
what it should render the inner text as. For example, if you see:

```
<h1>My Fancy Recipes</h1>
<p>I have lots of fancy recipes because I'm fancy. <emph>Really</emph> fancy.
</p>
<p>Didn't you see my neon green blink tags?</p>
```

This means that `My Fancy Recipes` is a *top-level header*, **h1**. As you may
have guessed, a secondary header is **h2** and a third... Well. It goes on.
It means the other text is **paragraph** text; specifically, that there are
two paragraphs separate from one another. Now let's fancy it up with some CSS.

```
h1 {
    color: #0F0;
    text-decoration: blink;
    font-size: 9000;
    font-family: 'Comic sans MS';
}
``` 

Now that's a disgusting header. I feel like I'm back in '99. Lastly, we've got
some picture and music assets in the folder. Another type of file is 
JavaScript. JS has revolutionized the web. It lets the user do fancy things. 
When they press a button, it can call a function. When they hover over an 
image, a JS function can change the style. It's kind of a big deal.

To run this website from your own computer, you can just double click an HTML
file and run it. Remember, you have all of the files on your computer! All they
are doing is linking to one another and the web browser handles how it looks.
This is why some things don't work in some browsers -- the browser developer
hasn't programmed a way to read it yet!

So it's all fine that YOU get to just double click it, but how does somebody 
else see it? Well, you could put it into a zip file, email everybody a copy
of your website with the subject line "I MADE DIS" and hope you never have
to change it again. Or, you can set up an **HTTP** server. 

### Server-Side

#### Simple HTTP Server

The most basic web server is a simple HTTP server. In fact, in Python, there
is a module you can use called SimpleHTTPServer which just sends the directory
of files to anyone who visits your IP address and handles things known as HTTP
**Requests**. I won't go super in depth with these, but think of it as ways to
accept input from a user. If I click a link, I send a **GET** request from the 
browser, asking to *get* a web page. I then expect a web page back and the 
browser knows to get ready to load a new web page. If I send a **POST**, I'm 
*posting* informating to the server and may, or may not, receive a response. 

It's a bit more complicated than that, but at its core it's just a translator,
sending and receiving messages and files. You don't see HTML or CSS on the 
server. You don't render any of that! It will be on the system, but only so 
that it can send it out to the user who needs it. It doesn't load it. 

#### Bigger and Better Things

As time went on, more and more servers and server languages popped up. People
wanted more complicated things on the server and with good reason. When these
websites were starting up, you couldn't expect the user to have an amazing
computer. It makes sense that you would want to perform some *task* on the
server, so their computer didn't have to. On top of this, you want users to
*log in* or *send messages* to each other. Well you can do that with some
paragraphs and headers! 

Servers are programs, or multiple programs, which handle requests by sending
and receiving data. Aside from a simple HTTP server, it's possible to
write a server which is capable of receiving data and sending it back after
performing some function or algorithm upon it. We could have a database of
usernames and passwords, and the user types their text into a browser and
posts it over to our server, where we check if it lines up and we send them
a page if-and-only-if they passed our check. Otherwise, we'll send them a 
different page telling them they are dumb. Now, we have *conditional* 
websites. Interactive websites which can interact with other users and
with the server. The browser and the server can have a *conversation*.
Before, the conversation was very one-sided; the browser yells for 
resources and the server complies. Now when the browser yells for 
resources, the server can decide whether or not it wants to based on some
criteria. 

## Moving on To Today

Nowadays, web applications aren't so simple. We have preprocessors; things 
which take code you've written, modify it, and *then* let the server have it
to send it out. This lets us do things like complain about JavaScript and CSS,
saying we could do it better, and making a new language which gets turned into
JS/CSS before the server gets it. That way the browser knows what we're talking
about. While it's commonly used for translating, it can also be used to make
the files being sent smaller. It can send a zip file instead of all of the big
website files. It can compress images and remove useless letters in code.

On top of this, we have task-runners. These things let us run programs, or 
*tasks* which can do all sorts of fancy things whenever we run our app. This 
does fun things, like preventing our server from turning on if it things we're 
bad programmers, or reloading the server when we make changes to the code. 

We've also got templates. These are HTML files with pieces missing which get
filled in by the server before sending the page out. 

Modern web application development has taken a very **full-stack** approach to
development. This means that a developer tends to work with every piece of the 
software solution stack which runs the website. They will work a bit on the 
server, a little on the front-end, and anything in between. This is great, but
it makes modern applications a bit of a tough starting point as the lines 
between front-end and back-end blur a bit. 

### Understanding Modern App Structure

Something that might shock you after reading this is that this website and many
others are actually entirely front-end. Yes, this is being run by a simple HTTP
server (one hosted by Github). Modern JavaScript is so developed that there are
extremely powerful libraries and frameworks available. Here, I'm using 
[Angular.js](https://angularjs.org/). It lets us feel like we're serving lots
of pages, but instead they're all downloaded at once or only when needed. 
It makes it easier to perform algorithms and fancy functions without needing
to talk to the server, because honestly modern computers are pretty cool and
can deal with that. It also does lots of other things, like make HTML a bit
more powerful for things we do a lot of on modern websites like conditionally
hiding elements. 

So yes, this is a static, front-end only website. That means there is no 
Apache, Node.js, Flask, Django, or Ruby at work. It's just sending you pages
which happen to have some pretty powerful and clever JavaScript functions in 
it.

## Building a free GitHub Pages Website

Building a GH Pages website for free is really easy and a great learning
experience to introduce you to website development. 
GitHub provides a [great tutorial](https://pages.github.com/) on getting
things set up. What you'll need to do is get a website which you can run by
double clicking - a purely front-end website - and toss that into your
repo. 

This is a great time to try out frameworks and learn something about
front-end development. Make a bunch of front-end only apps, and then maybe look
into something like [Node.js](https://nodejs.org/en/) and hosting on something
like [Heroku](https://www.heroku.com/) once you can easily distinguish 
front-end from back-end. Hell, make a front-end only app hosted on GitHub which
communicates with a Heroku app without serving from it. It's pretty clearly
separated when they're two completely different services!

## Rants About my Site

Personally, I'm not sure how I feel about the design. I might adjust it with
time. I also want to keep things fairly basic, but I also want it to be a bit
of a tech demo. I'm not sure how to find that balance. I've always been a bit
of a minimalist. I'm also trying to avoid using a ton of pre-processors or
libraries. It can get a bit tedious, to be honest, especially on something as
basic as a personal site. Oh well. I'm sure fun things will come up.

Happy coding!