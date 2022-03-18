# ![GA Logo](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Mongoose Relationship Movies 🎥

Using what you have learned about Express, Express Routing, RESTful routing, CRUD operations, and Mongoose, use the Mongoose ODM to implement full CRUD functionality on an API that has data relationships that are bouth 1:M and N:M.

How we make it work: 
- we will build an express server that makes mongoose CRUD requests to a Mongo db. 

## Overview

There will be 3 models in total: `Movies`, `Ratings` and `CastMembers`. 

1 Movie can have many Ratings (`1:M`), because you cannot review more that one film at once, and many `Movies` can may many `Castmembers` (`N:M`) because actors can appear in many film roles.

This deliverable is broken up into three parts.

* In part one, you will create an express app and the `Movie` model, with no relattions. This part will need a `movies` controller
* * In the seond part, you will create a rating `Schema` and `ratings` routes. You can accomplish this part with either mongo refs or embedded documents.
* The third part covers Many to Many, and you will create a `CastMember` schema and `castMember` controller for your express app.

## **Part 1**: 

Creating the API

1. The  model we will be using is _*movies*_, so we will be making a _*movie*_ API. 

*Movie Schema:*

| column name | type |
|:-----------:|:----:|
| title | string |
| description | string |


1. Your API should be accessible via five routes: 

*Example API Routes:*

| Method | Action | URL | Functionality |
|--------|:------:|:---:|:--------------|
| GET | index | /movie | list all movies  |
| POST | create | /movie | add a new movie |
| GET | detail/show | /movie/:id | show one movie |
| PUT / PATCH | update | /movie/:id | update one movie |
| DELETE | delete | /movie/:id | delete one movie |

-------

### **Steps to Achieve -- Part 1**

**You will need to:**
1. Fork and clone this repository!
2. Run `npm init` to start your node project. 
3. Create a `.gitignore` and add everything to ignore
4. Create your Express App
5. Add Mongoose functionality!

**Recommended Workflow:**
1. Stub out your routes. For the purposes of initial declaration, `res.send("test")` to make sure you're hitting them.
2. Link your model to your server.
3. Update your routes to "do something" and make the magic happen!

-------

## **Part 2**: 

Adding ratings to your Movie API.

**Movies have a 1:M relationship with ratings -- one Movie can have many ratings**

1. We will be creating another mongoose model for ratings, it will be an embedded in the Movie. Movie ratings can have 0 - 10 stars and a comment.

*Rating Schema:*

| column name | type |
|:-----------:|:----:|
| stars | integer |
| comment | string |

*Movie Schema:*

| column name | type |
|:-----------:|:----:|
| \_id | integer |
| title | string |
| description | string |
| ratings | [Rating] |


1. Your API needs these routes either updated or added: 

*Example API Routes:*

| Method | Action | URL | Functionality |
|--------|:------:|:---:|:--------------|
| GET | index | /movie | list all movies and incldue thier ratings |
| POST | create | /movie/:id/rating or /movie/:movieId/rating | add a new rating to a movie |
| PUT / PATCH | update | /rating/:id | update one rating |
| DELETE | delete | /rating/:id | delete one rating |

-------

### **Steps to Achieve -- Part 2**

**You will need to:**
1. Create an embedded document in the Movies model.
2. Add routes to your express app to interact with the embedded model.

**Recommended Workflow:**
1. Embed your Ratings model in your Movies model.
2. Stub out your routes. For the purposes of initial declaration, `res.send("test")` to make sure you're hitting them.
3. Update your routes to "do something" and make the magic happen!

-------


<!-- ## **Part 3** (Bonus): 

Adding CastMembers to your movie API.

**CastMembers have a M:M relationship with ratings -- one Movie can have many CastMembers and CastMembers can be in many movies**

1. The last model we will be adding to our API is castMembers. Many castmembers can be in many movies -- so we will have to use references.

*castMembers Schema:*

| column name | type |
|:-----------:|:----:|
| name | string |
| bio | string |
| filmography | reference to movies schema |

*Movie Schema:*

| column name | type |
|:-----------:|:----:|
| title | string |
| description | string |
| ratings | [Rating] |
| cast | reference to castMembers schema |


1. Your API needs these routes either updated or added: 

*Example API Routes:*

| Method | Action | URL | Functionality |
|--------|:------:|:---:|:--------------|
| GET | index | /movie | list all movies and incldue thier cast members |
| POST | create | /castMember | create a new castMember |
| PUT | update | /castMember/:id | update a castMember |
| DELETE | delete | /castMember/:id | delete one castMamber |
| PUT | update | /movie/:id/castMember | add a new cast member to a movie |
| PUT | update | /castMember/movie or /castMember/:castMemberId/movie/:movieId | add a new cast member to a movie |

-------

### **Steps to Achieve -- Part 3**

**You will need to:**
1. Create a castMembers model with a reference to the movies model
2. reference the cast members in the movie model
3. Add routes to your express app to interact with the new models

**Recommended Workflow:**
1. Embed your Ratings model in your Movies model.
2. Stub out your routes. For the purposes of initial declaration, `res.send("test")` to make sure you're hitting them.
3. Update your routes to "do something" and make the magic happen!

-------


--- -->

## Licensing
1. All content is licensed under a CC-BY-NC-SA 4.0 license.
2. All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
