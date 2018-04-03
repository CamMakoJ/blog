+++
title = "ACIMS App"
description = "An introduction to the app that I developed for the plant species of Alberta"
date = 2018-04-03T07:07:37-06:00
weight = 20
draft = false
bref = "This was a fun and rewarding learning experience"
toc = true
tags = ["App development", "Alberta Plant Species", "ACIMS"]
+++

### About the app
The ACIMS app was developed after experiencing the frustration of forgetting the
ACIMS list at home and trying to download the spreadsheet onto my phone.
Spreadsheets in general aren't awesome experiences on mobile and can be quite
cumbersome. This was definitely the case with the massive ACIMS list and so I wanted
to make it better. I also have always been interested in learning to code for a long time
but hadn't had the motivation to seriously learn. With a project in mind I started to
look into what I actually needed to learn to get there.

### Free Code Camp
After deciding that my best course of action was to learn JavaScript as a language
(more on this later) I signed up with a website called [FreeCodeCamp](https://www.freecodecamp.org/).
They offer an excellent free resource that can help you kickstart learning to code for
basic web development.

### JavaScript
I chose to learn JavaScript as it seemed to me that was one of the broadest languages in
terms of applicability. It is what makes up majority of the front end of the web as well
as having a ton of great online learning resources. Given that I never took anything like
this in school, it seemed best to start with what seemed biggest and go from there. As
well the nice part of JavaScript is every browser is your interpreter which made it
seem much less daunting to 'check as I went' and see how changing components of the code
altered the outputs in the browser. I fell in love with this! I have always enjoyed
trying to work through things in a logical manner and was always attracted to computers in
this way, however I have never been strong with grammar... and well coding has a ton of
grammar, or 'syntax' rules. Any previous attempts to learn always ended up with me
being frustrated by getting bogged down in syntax issues. However with JavaScript and
being more comfortable with watching my codes impact 'live' I eventually got comfortable
enough with the syntax that I could forget about it and enjoy the writing.

### Ionic Framework
Since JavaScript is in general a web language, why did I learn it if I intended on
developing an app? Since both iOS and Android apps typically run on different languages (swift and java)
and given I was new, I wanted to be able to code in one language (easier to learn)
and yet develop for both. This was made possible with the [Ionic Framework](https://ionicframework.com/).
It essentially wraps around the 'web-app' that I wrote and allows me to build out both
the Android and iOS apps from the same codebase. This was a massive help as it reduces the
maintenance required (1 codebase vs 2) as well as helps ensure that both apps look the
same.

### Development
In developing the app I generally used what is called [AngularJS](https://angularjs.org/) as
a JavaScript framework. One thing I found while learning was that there are so many excellent
tools available, however it can be extremely daunting to choose what to use. I chatted with some friends
who are skilled programming as well as created a lot of very small mini projects. Trying
out little features on their own before attempting to combine things together. Eventually
I started to put together the app working out the kinks as I went and iteratively adding
features.

I had outlined prior to starting the general features I wanted to be involved in the app.
the ability to query the entire ACIMS list by common or scientific name and to see
the current ACIMS rank. As well I thought it would be handy if some synonyms could be
queried as well, as that tends to be handy. Once I knew the features I drew out on paper
the various 'pages' of the app and how I wanted them to look. These were very basic views
but I found them help me focus on what I was doing and gave me a better mental map of the
final product.

As I was developing the apps 'pages' I started to work on the logic component of the app.
This essentially was to take a users input in the search and return the species that
related to it. To do this efficiently and make sure later updates to the ACIMS list could be
incorporated simply (ie. not recreating individual species pages) I wanted to use an object to hold
the ACIMS data (I used a JSON) and then created a service within the app that would access it. In this way,
updating the ACIMS app means I just need to update that JSON file and the rest of the app
will update with it. Once this was done I then needed to focus on how to display that data.
Initially this was simple, display the entire list and just filter it as a user provided input.
This worked great on my computer, however as soon as I tested it on a phone it was clearly
not a very efficient way to do this. What I needed to do was reduce the number of species cards the
phone had to render at one time. Which eventually I figured out, though it took me a few
tries and I released the app originally with the main page just limited to 25 results. This
worked if you knew that's what it was doing, but was very confusing to users that didn't.

If you want to see what all of this looks like you can see the full codebase on
[github](https://github.com/CamMakoJ/acimsApp).

### App Links
+ [Google Play Store - ACIMS App](https://play.google.com/store/apps/details?id=com.ionicframework.acimsapp774258&hl=en)
+ [Apple iOS App Store - ACIMS App](https://itunes.apple.com/ca/app/acims-search-app-alberta-plant-species-list/id1198423156?mt=8)
