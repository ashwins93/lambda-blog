---
title: Sprint 2 - Lambda Labs
date: "2019-03-25T16:37:06.822Z"
---

This week we completed implementing all APIs required for our app.

## Part 1 - Individual Accomplishments this Sprint

I was not able to complete as many story points as I had orginally hoped to complete this sprint. I was able to implement all CRUD methods for houses API. I did not face any technical difficulties completing any of the tasks this sprint, the challenge I faced this sprint was lack of time to spend on the project, being employed. Since we had a strong setup in the previous sprint, implementing the houses API was a breeze, thanks to `sequelize`.

### Detailed Analysis

PR: https://github.com/Lambda-School-Labs/labspt2-house-cup/pull/20

Goal: To build houses API service

Result: The API microservice to manage schools and houses is complete.

It was fun to implement the houses service as a nested route inside `schools` microservice. I followed the convention of having one file for each controller and created a `houses.js` that exported a controller that will let the users to create, read or modify any house record. I nested the houses route insde schools route as follows.

```javascript
// controllers/routes/schools.js
const houses = require("./houses")

router.use("/:id/houses", houses)
```

The houses controller has the following endpoints.

| Endpoint                           | Method     | Description                                                     |
| ---------------------------------- | ---------- | --------------------------------------------------------------- |
| `/api/schools/:id/houses`          | **GET**    | Returns a list of all houses for the school with id per the URL |
| `/api/schools/:id/houses`          | **POST**   | Creates a new house for the school specified in the URL         |
| `/api/schools/:id/houses/:houseId` | **GET**    | Returns the house with the id `:houseId` in the URL             |
| `/api/schools/:id/houses/:houseId` | **PUT**    | Update a house with id `:houseId` in the URL                    |
| `/api/schools/:id/houses/:houseId` | **DELETE** | Removes the house specified in the URL                          |

The way I had organized the controllers (nested routers), meant that the URL parameter `:id` wasn't normally available with the request object inside the houses controller callbacks. After a lot of reading I finally learned about the express `Router` constructor. The solution was to instantiate `Router` with `mergeParams` property.

```javascript
const router = express.Router({
  mergeParams: true,
})
```

Setting `mergeParams` to `true` will cause the parameters from the parent URL to be available to all the nested routes.

## Part 2 - Weekly Reflection

I wasn't of much help to my teammates this sprint. I am hoping to be make myself available more in the coming sprint. I did manage to find time to help my team fix merge conflicts. Overall, I feel like our team is progressing at a normal pace and will be able to comfortably finish the project.
