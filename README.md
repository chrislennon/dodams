# pre-install
`gem install bundler`

# install dependancies
`bundle install`

# run project locally
`bundle exec jekyll serve --baseurl ''`

`baseurl` running on github pages will include the repository name i.e. `chrislennon.github.io/dodams/`


# Creating a meetup

Create a folder for the relavent month `./meetups/2018/Month`.
Create an index.html with the following parameters - see `meetups\example\index.html` for an example.

Main Variables
**parameter**|**example value**|**purpose**
:-----:|:-----:|:-----:
layout| default| defines which style of presentation to use (only supports default)
title| Schiphol| defines the name of the Meetup
image| ./dodams.png| defines the logo for the first slide - typically host logo
description| Our March Meetup| defines the purpose for the meeetup
talks| *Array of Talks*| associative array of talks - see below
promos| *Array of Promos*| associative array of promotional slides - see below

Specifiying talks - for each talk add an array element containing the following:
**parameter**|**example value**|**purpose**
:-----:|:-----:|:-----:
title| A Presentation Title| defines the name of the presentation
speaker| Presenter Name| name of the speaker
image| ./profile-pic.png| picture of the speaker

Specifiying promo slides - for each slide add an array element containing the following:
**parameter**|**example value**|**purpose**
:-----:|:-----:|:-----:
title| A Presentation Title| defines the name of the promotion
description| Get x% off of an event| message to display
image| ./event-pic.png| picture for the promotion


Brining it all together (example.html):
```
---
layout: default

title: Example devops Amsterdam meetup slides
image: ./dodams.png
description: >
                Example <a href="https://www.meetup.com/DevOpsAmsterdam/">meetup</a> presentation using 
                <a href="https://github.com/hakimel/reveal.js">reveal.js</a> with 
                <a href="https://github.com/jekyll/jekyll">Jekyll</a> on <a href="https://pages.github.com/">GitHub Pages</a>

talks:
    - title: Title of presentation 1
      speaker: Speaker Name
      image: ./profile.png

    - title: Title of presentation 2
      speaker: Speaker 2 Name
      image: ./profile.png

promos:
    - title: Example1
      description: >
                    This is an example page for showing a <span class="promo">promotional discount</span>
      image: ./promo-example.jpg
    - title: Example2
      description: >
                    This is another example page for showing a <span class="promo">promotional discount</span>
      image: ./promo-example.jpg
---

{% include meetup-default.html %}

```
