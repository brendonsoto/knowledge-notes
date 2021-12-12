#how-to #graphql 

# How to Create a GraphQL Server Quickly
*Prerequisite: Node.js*

- make a directory
- `cd` into directory
- `npm init -y`
- `npm install apollo-server graphql`
- make an `index.js` file
- add the following:
  ```
  const { ApolloServer, gql } = require('apollo-server');


  const typeDefs = gql`
    type Query {
      # put your stuff here
    }
  `;

  const server = new ApolloServer({ typeDefs });

  server.listen().then(({ url }) => {
    console.log(`🚀  Server ready at ${url}`);
  });

  ```
- save
- open a new terminal
- `cd` into the same directory
- run `node index.js`
- visit the url listed in the command prompt

**NOTE:** You will have to shutdown and restart the server for changes