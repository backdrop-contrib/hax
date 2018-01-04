HAX
======================
HAX is short for Headless Authoring eXperience. The goal of HAX is to integrate with
hax-capable webcomponents which provide the entire authoring experience. This keeps the
AX disconnected from Backdrop except for handling the end point logic of where to save data.
This can be seen on [haxtheweb.org](https://haxtheweb.org/) which is a fully decoupled version
of this project which we then pull back into Backdrop.

- [Check out the DrupalCon 2017 presentation where we announced this](https://www.youtube.com/watch?v=dGi8n1LAQbg)
- [Video of me talking through this module working in Drupal 7 and 6](https://www.youtube.com/watch?v=8rOf6tb8Ls4)

Installation
------------
- Install this module using the official Backdrop CMS instructions at
  https://backdropcms.org/guide/modules

- Download and install the webcomponents module as it is a requirement of this

This is intended to be run prior to being pushed to a server via sftp or git or whatever your workflow is. If you don't currently have bower you can get it via `npm install -g bower`

## no Webcomponents installed yet
Create a directory for webcomponents to live in for the system. This is recommended as:

`mkdir -p sites/all/libraries/webcomponents/polymer`

Copy the `bower.json` included in the hax module over to this directory:

`cp sites/all/modules/hax/bower.json sites/all/libraries/webcomponents/polymer/bower.json`

Run bower install to get dependencies in place:
`cd sites/all/libraries/webcomponents/polymer`
`bower install`

Skip the next heading

## What if I already had webcomponents?
Go to polymer directory :
`cd sites/all/libraries/webcomponents/polymer`

Run the following:
`bower install --save LRNWebComponents/cms-hax`

Answer any questions bearing in mind that hax currently is written against webcomponentsjs 0.7.x and polymer 1.x.x as of this writing. You will have the dependencies needed.

## Usage
This should give you the dependencies you need to get going. Enable the module and go to the permissions page to ensure uses have the 'use hax' permission checked. Once this is checked then people will start to see a 'HAX Authoring' local menu item / tab / contextual option show up when they have access to edit a node.

Click this, and then hit the power button in the top of the UI to get started. When your done editing hit the power button again and it'll save back to the server.

## Side note on Build routines
If you are looking to use a build routine, that's great! You'll just want to make sure that you have all the elements in place needed to make HAX run. HAX paths and interface won't show up unless users have permissions so while not recommended to include HAX in your build routine, it won't hurt anything either (other then download size).

## but but but, you don't run it this way do you!?
You are correct. We have a much more advanced methodology of getting webcomponents into the right place. We're also leveraging the same bundle of components across multiple distributions of Drupal 7 + static sites + GravCMS. So while what the ELMS:LN team (who produced this) uses will look a liiiiittttle bit different if you dig into our file system, ultimately we are just tricking drupal into loading all the files the way we just described above.

Our build routine ultimately is just smashing together the top 50 or so commonly used elements in our universe and then tricking webcomponents into thinking all these elements live in the polymer.html file. By doing this we can cheat on page delivery as we can send you 1 heavily cached asset after 1st page load which actually resolves to 50+ elements. When it comes to HAX, we still keep that separate as that's only supposed to be loaded for users that actually have need of it.

Usage
-----
- Go to a node (or create one) then click the 'HAX editor' tab.
- Hit the power button in the top of the UI to get started. When your done editing hit the power button again and it'll save back to the server.

Advanced
--------
If using other webcomponents in projects it's recommended to symlink this directory back to a shared location located in sites/all/libraries/webcomponents/polymer/elements (or whereever you keep your global elements).

Issues
------

Bugs and Feature requests should be reported in the Issue Queue:
https://github.com/backdrop-contrib/hax/issues

Current Maintainers
-------------------

- Bryan Ollendyke (https://github.com/btopro/)

Credits
-------

- Ported to Backdrop CMS by btopro (https://github.com/btopro).

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.
