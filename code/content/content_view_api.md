Content API
========

Content API uses to sync up data providers (Github, bitbacket etc) on the left side with right side content tabs views. So, it is API to request content from Github and show it in the corresponding view.

Each content provider could have it's own UI elements and behaviour. For example: Github has commit API and cache of the loaded data while localhost API always save data directly.
It means that content API should know nothing about internal features of the data provider.

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/content_with_provider_classes.umlsync "")

LoadContentController is a simple wrapper over the DataProvider API. 


Load content sequence
==========

LoadContentController doesn't have specified API with DataProvider but anyway it is expect:  

Two events: content in focus (clicked on file), content loaded (trigger content data received)

Three API: load/save/close content

Both events and API should contain enough data which could one-to-one specify content and data provider:

1. Data Provider: GitHub
2. repo: user/repo
3. branch: master
4. absolute path: /x/y/z.umlsync
5. status: "loading|loaded|new|modified|sha|error"
6. sha: optional if status == sha only
7. isEditable: true/false - indicates if it is possible to edit content (for example if user is owner of the repository)
8. content - payload if status == "loaded" and error message in case of error


ContentController - is a controller over the loaded content collection. It handles requests from the multiple data providers and
open content in the corresponding views.

There are two different use-cases for content-load:

1. Load content by focus
2. Load an embedded content or content by link

Load content by focus:
-----------
![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/content_load_sequence.umlsync "")