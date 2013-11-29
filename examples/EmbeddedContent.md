
The way to add an embedded content into markdown
========
This document describes the way to insert UmlSync's diagrams into markdown documentation.
And provide and idea of the possible alternatives to generate an embedded content for markdown.

The UmlSync tool support the several ways to insert diagram into markdown for any repository on GitHub:

1. Absolute path (including: user, repo, branch and path)

2. Relative path (relative path to the opened document)

3. Fixed version (by sha)

4. GIST-diagram

An absolute path: 
--------
An absolute path looks like this:

_!\[Diagram: \] (http://umlsync.org/github/umlsynco/diagrams/master/diagrams/ElementInitialization.umlsync "")_

You could send this path to your colleagues to open the concrete diagram.
But in case of markdown it is recommended to use an absolute path if it is necessary to insert the diagram from another GitHub repository.

There are several reason for that:

1. Unify an access to offline clone of repository:

   - There is no way to identify an absolute path for the loaded content for the local clone of repository;

   - If it will be possible to identify the resource location then it is not clear which version should be selected GitHub or local ?

2. It is easier to change an online source control system (bitbucket, github, googlecode);

3. Even if you changed the location of repository, an absolute link will be point on GitHub. So, you could insert links on GitHub from any place (even from your intranet repository);

The relative path:
--------

The major idea is to use relative path like this inside repository:

_!\[Diagram: \] (http://umlsync.org/github?path=./ElementInitialization.umlsync "")_

There are several benefits of such approach:

1. Offline clone of repository; You could load to plug-in only part of repository;

2. Something more...


Fixed version (SHA):
--------

Similar to an absolute path idea. Uses to share with colleagues a fixed version of the diagram, insert from external repository an old diagram.

And of course is is not recommended to use inside repository!

_!\[Diagram: \] (http://umlsync.org/github/repos/umlsynco/diagrams/git/blobs/9974fbe3ef6690d32064f753d962d661b1fc7384?1385219431501 "")_


GIST:
--------
_!\[Diagram:\ ] (http://umlsync.org/github-gist/userId/gistId "")_

GitHub has a 60-requests limit on a git repositories access for the not logged-in users.
But there is no such limitation on GISTs. we are working on the way to create a UML widgets for the 3pp sites.

<br><br>
---

The common way to add an embedded content into markdown

As you know it is possible to insert the references on content into gfm(github flowered markdown).

But how to insert an embedded content as reference ?

For a one hand it is good that user have to specify the full path to the umlsync.org:
1. It is clreat how to open an embedded content 
2. From the markdown point of view it is some kind of image (which is corresponding to UML diagram specific)

BUT for another hand it is necessary to implement common approach for all storage service. It should be possible to:
1. Change service provider (github, googlecode, bitbucket etc)
2. Change viewer application (UMLSync etc)
3. Identify content type and handler
4. Identify content by relative path, absolute path and SHA(fixed version) 
5. Make the reference compatible storage servie (with GitHub references for example)

###Mime type
It sounds like a good idea to replace the \[Diagram:\] prefix which on \[mime:type\] to make it possible to handle the conent via special handler.

For example:
_\[mime:application/vnd.xmi+xml\](http://umlsync.org/github/?path=../../relative/path/to/content/file "title")_

the next step is to drop the reference on the umlsync.org:
_\[mime:application/vnd.xmi+xml\](../../relative/path/to/content/file "title")_

BUT how to identify that content belong to Github ?
1.storage prefix:
_\[mime:application/vnd.xmi+xml\](github/user/repo/master/path/to/content/file "title")_
_\[mime:application/vnd.xmi+xml\](googlecode/user/repo/master/path/to/content/file "title")_

2.storage prefix:



