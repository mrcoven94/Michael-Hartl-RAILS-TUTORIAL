Chapter 2 - A Toy App
=========

## Overview
We’ve come now to the end of the high-level overview of a Rails application. The toy app developed in this chapter has several strengths and a host of weaknesses.

*Strengths*

High-level overview of Rails
Introduction to MVC
First taste of the REST architecture
Beginning data modeling
A live, database-backed web application in production
Weaknesses

No custom layout or styling
No static pages (such as “Home” or “About”)
No user passwords
No user images
No logging in
No security
No automatic user/micropost association
No notion of “following” or “followed”
No micropost feed
No meaningful tests
No real understanding
The rest of this tutorial is dedicated to building on the strengths and eliminating the weaknesses.

## What we learned in this chapter

Scaffolding automatically creates code to model data and interact with it through the web.
Scaffolding is good for getting started quickly but is bad for understanding.
Rails uses the Model-View-Controller (MVC) pattern for structuring web applications.
As interpreted by Rails, the REST architecture includes a standard set of URLs and controller actions for interacting with data models.

Rails supports data validations to place constraints on the values of data model attributes.
Rails comes with built-in functions for defining associations between different data models.
We can interact with Rails applications at the command line using the Rails console.

