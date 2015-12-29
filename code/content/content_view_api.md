Content API
========

Content API uses to sync up data providers (Github, bitbacket etc) on the left side with right side content tabs views. So, it is API to request content from Github and show it in the corresponding view.

Each content provider could have it's own UI elements and behaviour. For example: Github has commit API and cache of the loaded data while localhost API always save data directly.
It means that content API should know nothing about internal features of the data provider.

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/content_with_provider_classes.umlsync "")


Load content sequence
==========

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/content_load_sequence.umlsync "")