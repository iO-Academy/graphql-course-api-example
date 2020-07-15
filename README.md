# An example GraphQL API
Built with Node.JS, Express and the express-graphql package.
## Install steps
1) Firstly clone this repo locally
2) Run `npm install` to install the project dependencies
3) Run `node index.js` or `nodemon index.js` to start the application

You should then be able to access the GraphiQL UI by visting [http://localhost:4000/graphql](http://localhost:4000/graphql)

## Example Usage

### Fetch a single course by ID
#### Query
```
query {
  course(id: 1) {
    title
    trainer
    url
  }
}
```

#### Response
```
{
  "data": {
    "course": {
      "title": "Full Stack Track",
      "trainer": "Ashley Coles, Mike Oram",
      "url": "https://mayden.academy/full-stack-track/"
    }
  }
}
```

### Fetch all courses
#### Query
```
query {
  courses {
    title
    trainer
    url
  }
}
```

#### Response
```
{
  "data": {
    "courses": [
      {
        "title": "Full Stack Track",
        "trainer": "Ashley Coles, Mike Oram",
        "url": "https://mayden.academy/full-stack-track/"
      },
      {
        "title": "Working with Developers Workshop",
        "trainer": "Mike Oram",
        "url": "https://mayden.academy/working-with-developers-workshop/"
      },
      {
        "title": "Introduction to WordPress for Developers",
        "trainer": "Ashley Coles",
        "url": "https://mayden.academy/introduction-to-wordpress-for-developers/"
      }
    ]
  }
}
```

### Fetch a list of courses by topic
#### Query
```
query {
  courses(topic: "Full Stack") {
    title
    trainer
    url
  }
}
```

#### Response
```
{
  "data": {
    "courses": [
      {
        "title": "Full Stack Track",
        "trainer": "Ashley Coles, Mike Oram",
        "url": "https://mayden.academy/full-stack-track/"
      }
    ]
  }
}
```

### Update course topic by ID
#### Query
```
mutation {
  updateCourseTopic(id: 1, topic: "cheese!") {
    title
    trainer
    topic
    url
  }
}
```

#### Response
```
{
  "data": {
    "updateCourseTopic": {
      "title": "Full Stack Track",
      "trainer": "Ashley Coles, Mike Oram",
      "topic": "cheese!",
      "url": "https://mayden.academy/full-stack-track/"
    }
  }
}
```