# Visualizing real-time data with Angular and D3

Hello! I'm Jeremy and I'll be your guide as we walk through building out a realtime dashboard built with Angular and D3 charts.

This guide will help walk you through the steps for the workshop. It provides step by step instructions, but does not include all of the 'why', which is covered in the workshop itself.

## Expectations

This workshop expects that you have a basic understanding of the following.

* How to build web applications (not necessarily with Angular), such as how HTML/CSS/JavaScript are used to create more complex applications than just static content.
* How to work with data, such as how to use API and basic ideas of how data can be streamed.
* Single Page Applications. There is a server side element to this workshop, but the frontend application is entirely separate.

> Even if you are brand new or aren't certain about your level of experience in these areas, I suggest that you follow along and not worry too much. Many people have shared they learn a lot by simply following along even if they miss a detail here or there.

## How this guide works

On the left is the table of contents, which is broken down into separate chapters. We'll work through the content from the top to the bottom. All of the code you need to write can be found in these topics.

During the course of the workshop, I'll publish new topics as we begin a new chapter of the workshop. This allows you to work ahead within the current chapter or go back if you need.

## Getting help

If you run into trouble, I've setup a Gitter room for everyone to use to chat during the workshop. Please use this to help others if you are able.

Gitter: https://gitter.im/gnomeontherun/oscon-2017-workshop
[![Join the chat at https://gitter.im/gnomeontherun/oscon-2017-workshop](https://badges.gitter.im/gnomeontherun/oscon-2017-workshop.svg)](https://gitter.im/gnomeontherun/oscon-2017-workshop?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

If you have a specific question or comment to send me, I'll try to monitor the chat during breaks and make sure I can answer your question. Please think about the kinds of questions you ask, while there are no bad questions some might be too specific to your work or use cases and would be best for us to talk after the workshop.

## What you'll learn

In this workshop, you'll learn a lot of things about Angular, realtime data, D3, and NodeJS.

* How to consume a realtime stream from Twitter
* How to use Firebase as a realtime database
* How to create an Angular app using the CLI
* How to setup and use the Clarity UI library
* How to connect to a realtime database on Firebase
* How to display charts

## Workshop outline

The workshop has been broken into several chapters.

### Chapter 1 - Setting up the server

This chapter covers how to setup and run the server. While the specifics of this server are not going to be covered, the concepts of what it does will be discussed. By the end of this chapter, we'll have a server capable of streaming realtime data from Twitter.

### Chapter 2 - Setting up the Angular app

We'll then build the basics of our Angular app by using the Angular CLI tool to help us create the project. There are some dependencies that we need to install and setup, and then we'll have a basic Angular app showing in the browser.

### Chapter 3 - Displaying the latest tweets

Next, we'll dive in to Angular more deeply by creating a component to display the latest tweets in realtime. To do this, we'll have to load this data from Firebase, learn how to pass data around, and then display the tweets. We'll have a nice sidebar showing a timeline of most recent tweets based on a keyword.

### Chapter 4 - Displaying realtime statistics

Now that we've got the tweets showing, we want to start to display charts and stats about the Twitter stream. We'll learn how to use D3 through the NgxCharts library, and see how data aggregations gives us interesting insights.

### Chapter 5 - Changing the term with voice

The last step is to allow the UI to change the term, which we'll allow the user to type a new term or optionally speak it. This will call the server to restart the stream with the new term and the UI will reflect this new data.