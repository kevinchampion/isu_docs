# ImageX Client Documentation

## Purpose

The purpose of this repository is to collect documentation that we create to share with clients to show them how to use their sites. By having it all in one place we can benefit from collaborating and from copying generic documentation made for other clients. This is meant to be a simple, static, approach to collecting documentation in one place. In the event that ImageX develops a more robust documentation platform, this should still be of use for populating that platform with content.

## How it works

Documentation in this repository is created using [markdown](http://daringfireball.net/projects/markdown/). The markdown can then be compiled into html for sharing with clients.

## Structure

Each distinct client should have its own directory within this repo. In the case of clients that have many large distinct projects, it may make sense to have distinct directories for each of that client's projects.

## Markdown

Markdown is a simple and expressive formatting language that makes it easy to write content and focus as much as possible on the content alone. The markdown can then be converted to html using a variety of different tools. The following are some resources:

- [Markdown syntax](http://daringfireball.net/projects/markdown/syntax)
- [Markdown live preview](http://markdownlivepreview.com/)
- [Sublime Text markdown preview plugin](https://github.com/revolunet/sublimetext-markdown-preview)

## Future

Right now this repository is just a collection point. The future path needs to implement some way of using the content in this repository to host the documentation for the client. Having all client documentation in one centralized repository complicates this because it means that using something simple to convert this into a static html site, like Github's gh-pages or by using Jekyll, will expose all documentation to the public. Instead, we'll need it to work so that access to documentation is limited to the clients viewing their own documentation and documentation is not publicly accessible unless we want it to be.

One idea is that we can figure out a way of building this documentation into the actual client sites themselves. Perhaps we could create a module that pulls only documentation for that client into their site and access controls can then be handled within Drupal.

Another idea is that we self-host this on a centralized server and control access by simple http authentication.
