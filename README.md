# Metalsmith Resume

Listen, writing resumes sucks. Microsoft Word and Adobe InDesign were not meant to be layout or content editing tools, respectively, and neither excel at managing information. I wanted to change that for myself, so I made [my resume](http://resume.lowmess.com) as a [Metalsmith](http://metalsmith.io) minisite. Then I made a better one to give away to everyone else. The math is simple: `markdown + YAML + git > those other things I just mentioned`.

Get started:

## Editing

1. Fork this repo
2. Open the project on [Prose](http://prose.io)
3. Edit and add files
4. ???
5. Profit (hopefully literally)

OK fine here's more.

### Adding Experiences

The most important part of any resume is, of course, showing off your bad self. The whole point of this project is to make that easier. So anyways, jobs live in the [`/experience`](/source/experience) subdirectory and schools in the [`/education`](/source/education) one. Each is it's own `.md` file with YAML metadata.

#### Metadata

As mentioned above, the easiest way to edit your resume is with [Prose](http://prose.io). Each job/school is expecting a few metadata fields, and Prose shows all those fields to you. I'm not gonna list them all out here for you, so the second easiest way is to just look at [an](/source/experience/zion.md) [existing](/source/experience/nebuchadnezzar.md) [experience](/source/education/owen-patterson.md) and copy that.

### Personal Information

The [`person.yaml`](/source/person.yaml) file is your key to making this resume your own. That's it for this section. ¯\\\_(ツ)\_/¯

### Site Settings

You can adjust display and styling settings in the [`site.yaml`](/source/site.yaml) file.

#### Set Number of Items to Show

The `jobs` and `schools` variables let you adjust the number of jobs & schools that are shown on the resume. I'll let the surprise settle in. Setting a variable to zero will hide the section completely. Full job & school histories are available at `/experience` & `/education`, respectively, regardless of these settings.

#### Theme Color

You can set your theme with the `theme` variable. I'll one again wait to let the shock wash over you. It will automagically™ check if your theme color has a high enough contrast ratio against white and adjust the styles accordingly. For best results, choose a color that has a color contrast ratio of at least 3.5 with white. [Hey look, a calculator](http://leaverou.github.io/contrast-ratio/)!

#### Print Styles

There is a setting called `printstyles`. This is probably a bad name. 🤔 I should update this name. Anyways, what it does is it makes everything black and white when you try and print the resume.

## Development

### Installation

Lads, it's `npm i`. (just make sure you're in the root directory of the project first)

### Local Server

[Browsersync](https://www.browsersync.io/) & [nodemon](http://nodemon.io/) is a match made in heaven. Luckily for you, it's already all set up! Just run `npm start` from the root directory of your repo and begin hacking away.

### Building

`npm run build` will build the resume site for you into the `_build` directory. Pretty straightforward.

### Styling

This project uses [Tachyons](http://tachyons.io) to style everything (with a few custom classes added in for good measure). All modules are included in the build, which is then run through a few performance-enhancing PostCSS plugins (PEPP'rd) like [UnCSS](https://github.com/giakki/uncss) & [cssnano](http://cssnano.co/). As of right now, all the loaded CSS is [~3kb](http://cssstats.com/stats?url=http%3A%2F%2Fmetalsmith-resume.lowmess.com&ua=Browser%20Default), and that's pretty damn cool. 🤓

## Contributing

Contributions are welcome, as anything that makes my job easier is.

1. Fork the project
2. Make your changes
3. Open a PR that has a descriptive name (or a robust description)
4. Feel good about yourself 🎉

## Hosting

As the whole resume site is a collection of static files, it can be hosted on just about any server. I do have a few preferences though. [1]

### Netlify

[Netlify](https://netlify.com) is my number one for a few reasons, number one being it's set-it-and-forget it nature. Just hook it up to your repo and it'll build every time you push to master (or every time you edit a file with Prose). It even comes with free SSL support through Let's Encrypt. Only downside is you have to pay to have a custom domain.

### Surge

[Surge](http://surge.sh) is a cheaper option if you can live without SSL (they offer SSL, you just have to pay more for it and it isn't as easy as Netlify). It does require you to build & deploy from the command line every time you make an update, but there's a helper `deploy` script in the [`package.json`](package.json) (it's like 30 characters long honestly).

### Github Pages

Until Github opens up its [Pages](https://pages.github.com/) feature to build tools other than Jekyll (you know, like those [*other*](https://pages.gitlab.io/) guys), it's less than ideal for our purposes. That said, [it can definitely be done](https://help.github.com/articles/creating-project-pages-manually/).

### Others

There are plenty of other options that I have no experience with, like [Amazon S3](https://aws.amazon.com/s3/) and [Firebase](https://www.firebase.com/docs/hosting/).

***

[1] I'm not a paid shill, promise. I just like these services. That being said, I certainly wouldn't turn down some free swag/service... 😏
