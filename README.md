# GraphQL Intro with Graphpack

This repository provides a simple introduction to using **GraphQL** with **Graphpack**. It covers the key concepts and tools you need to get started with building a GraphQL API.

## What is GraphQL?

**GraphQL** is a query language for your API and a runtime for executing queries by using a type system you define for your data. It allows clients to request exactly the data they need and nothing more, making it more efficient and flexible than traditional REST APIs.

### Key Concepts in GraphQL:

#### 1. **Resolvers**
Resolvers are functions that resolve a value for a type or field in your GraphQL schema. Each field in a GraphQL query corresponds to a resolver that provides the data for that field. They are the logic behind fetching and returning the data.

```js
const resolvers = {
  Query: {
    hello: () => 'Hello, World!',
  },
};
```

#### 2. **Schema**
The **GraphQL Schema** defines the types of data that can be queried or mutated in the API. It is a contract between the client and server, describing the shape of the API.

```js
const typeDefs = `
  type Query {
    hello: String
  }
`;
```

#### 3. **Query**
A **Query** is used to fetch data from the server. It is the most common operation in GraphQL. Queries specify what fields you want to retrieve from the server.

Example query:
```graphql
query {
  hello
}
```

#### 4. **Mutations**
A **Mutation** is used to modify data on the server. Mutations are similar to queries but are used when you want to create, update, or delete data.

Example mutation:
```graphql
mutation {
  createUser(name: "Alice") {
    id
    name
  }
}
```

#### 5. **Subscribers**
A **Subscriber** allows the server to push updates to clients in real time. It is often used for implementing WebSockets to allow clients to listen to events, such as updates or changes to data.

Example subscription:
```graphql
subscription {
  messageAdded {
    content
  }
}
```

### How Everything Fits Together

In a **GraphQL API**, you define your schema, which outlines all the **queries**, **mutations**, and **subscriptions** available. **Resolvers** provide the logic to fetch or modify the data when a query, mutation, or subscription is executed.

- **Schema**: Defines types, queries, mutations, and subscriptions.
- **Resolvers**: Handle the logic for the defined schema fields.
- **Queries**: Allow clients to read data.
- **Mutations**: Allow clients to modify data.
- **Subscribers**: Enable real-time data push from server to clients.

### Getting Started with Graphpack

This example is built using **Graphpack**, which simplifies the setup and configuration of GraphQL in your project. To get started, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/Elijah57/graphql-intro.git
   cd graphql-intro
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the server:
   ```bash
   npm run start
   ```

Your GraphQL API should now be running and accessible at `http://localhost:4000`.
