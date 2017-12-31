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

- cd into the hax directory and run `bower install`

- Enable the module and go to the permissions page to ensure uses have the 'use hax' permission checked. Once this is checked then people will start to see a 'HAX Authoring' local menu item / tab / contextual option show up when they have access to edit a node.

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
