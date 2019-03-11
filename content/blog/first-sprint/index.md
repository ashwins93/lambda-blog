---
title: Sprint 1 - Lambda Labs
date: "2019-03-11T17:46:32.125Z"
---

This post is first in a series of posts describing my journey in lambda labs. A collaborative effort from a group of 5 students from Lambda School - Web PT 2 to build "House Cup", a website that lets school administrators incentivize student behavior.

## Part 1 - Individual Accomplishments

I was involved in planning the project including the preparation of TDD and division of work among my team. I chose to concentrate on the API part of the project which we decided to build using `NodeJS`, `express` and `sequelize`. We decided that we should be using `Postgres` as our database in both production and development. Consequently I proceeded to add the required dependencies and configure the application. I also helped my teammates set up their local development environment. Later I built the `schools` API service.

### Detailed Analysis

PR: https://github.com/Lambda-School-Labs/labspt2-house-cup/pull/7

Goal: To build schools API service

Result: Succeeded in building the CRUD methods to interact with the Shools DB model.

The first sprint proved to be a breeze for me particularly. I did not have to work on anything that I hadn't done already in one of the Lambda School assignments. I used `sequelize.js` ORM to make my task easier. We had not used an ORM like `sequelize` before, it was a great experience for me to learn a new library and implement it without running into too much trouble. I had to read a lot of documentation.

## Part 2 - Milestone Reflections

The goal for the first sprint was to get our `User` models ready and also to get our front-end and back-end code deployed. We were able to perform all of that comfortably. At this point in writing I have a tiny bit of work experience as a developer. My experience proved useful in accomplishing this sprint's goals, particularly the use of `sequelize.js` helped us to quickly put together the necessary API endpoints.

We were able to deploy the back-end to `heroku` with relative ease. The front-end deployment to `netlify` took a bit of work. The front-end source had 2 different lock files which caused some problems with the deployment.

I did a bit of research before we begun this project and I couldn't find any competing products that were similar to the one we are developing. I believe we can't go wrong in choosing `React` as the front-end framework as it is, at the time of this writing, one of the most popular framework with a lot of support from the community. `Postgres` was the most obvious choice for the database for similar reasons. Between `knex` and `sequelize` the choice had to be made. After a bit of research I came to realize that `sequelize` is a proper ORM that provides a friendly interface abstracting the SQL away while `knex` was simple a query-builder, however the team as a whole was comfortable using `knex` due to practice. I convinced my team to choose `sequelize` for the long term benefits an ORM would provide.
