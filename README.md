# Tapestry 5 Documentation Project

This is a project to rebuild how Tapestry 5 documentation is generated; by hosting the project on GitHub, we can make it far, far, easier for people to contribute (we can grant access to anyone with a signed Apache CLA).

Currently, we are in the process of just setting things up.

## Overview

The site is built using [Jekyll](http://http://jekyllrb.com/), a Ruby program for building static web sites.  You need to have Ruby, the Jeykll gem, and a few other things installed.
Once installed, the command `jekyll` command will build an output directory, `_site`.

More commonly, you will execute `jekyll --server --auto` and open port <http://localhost:4000/>.  You can then change any files and refresh the browser to see the result.

## Coming up

So far, a lot of work to get the /index.html page working, which is full of special cases.

Next up, writing a script to convert the Confluence XML to markdown.

Jekyll has a lot of features (plugins and etc.) that will make our documentation a lot more concise and easier to maintain.

Ultimately, there will be a Gradle script that will build the documentation _for a specific release number_, then copy the `_site` folder over to an Apache CMS SVN directory for checkin and live deployment.
That is, deploying a live web site on Apache will involved a Subversion project that contains the files to be deployed; it is then a matter of commiting the site via SVN.
The Gradle script will streamline the process of generating the site and copying the files to a specified Subversion workspace.
Possibly, the Gradle script will be able to download the verison's API documentation file and extract that to the Subversion workspace as well.

The goal is to have site generation be as turn-key as possible, even when the version number changes.
