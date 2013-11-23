
The way to add an embedded content into markdown
========
This document describes the way to insert UmlSync's diagrams into markdown documentation.
And provide and idea of the possible alternatives to generate an embedded content for markdown.

The UmlSync tool support the several ways to insert diagram into markdown for any repository on GitHub:

1. Absolute path (including: user, repo, branch and path)

2. Relative path (relative path to the opened document)

3. Fixed version (by sha)

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

For example:
![Diagram: ] (http://umlsync.org/github/umlsynco/diagrams/master/diagrams/ElementInitialization.umlsync "")

The relative path:
--------

The major idea is to use relative path like this inside repository:

_!\[Diagram: \] (http://umlsync.org/github?path=./ElementInitialization.umlsync "")_

There are several benefits of such approach:

1. Offline clone of repository; You could load to plug-in only part of repository;

2. Something more...

![Diagram: ] (http://umlsync.org/github?path=./ElementInitialization.umlsync "")


Fixed version (SHA):
--------

Similar to an absolute path idea. Uses to share with colleagues a fixed version of the diagram, insert from external repository an old diagram, 

![Diagram: ] (http://umlsync.org/github/repos/umlsynco/diagrams/git/blobs/9974fbe3ef6690d32064f753d962d661b1fc7384?1385219431501 "")


GIST:
--------


The common way to add an embedded content into markdown
========

1. Identify mime type for the content
2. Relative or absolute path for the content on GitHub

\[mime:application/vnd.xmi+xml\](http://umlsync.org/github/?path=../../relative/path/to/content/file "title")

![mime:application/vnd.umlsync+json](http://umlsync.org/github/) http://umlsync.org/github/


