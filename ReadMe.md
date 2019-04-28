# GraphQL API

## Setup

### Run the following commnads on setup
```
npm install
npm run dockerStart
npm run deploy
npm run start
npm run load
```
## Queries

### Get all products
```
query {
  products {
    id
    name
  }
}
```
### Get one product
```
query {
  products(where: {
    id: "5ca5aa16576454000c387b4e"
  }) {
	  id
    name
    price
  }
}
```
### Count all products
```
query {
  productsConnection {
    aggregate {
      count
    }
  }
}
```
## Mutations

### Create a new product
```
mutation {
  createProduct(
    data: {
      price: 50
      country: "Singapore"
      name: "Mario Bros 2"
    }
  ) {
    id
    name
    price
    country
  }
}
```
### Update a product
```
mutation {
  updateProduct(
    data: {
      price: 10
    }
    where: {
      id: "5ca5aa16576454000c387b4e"
    }
  ) {
    id
    name
    price
  }
}
```
### Delete a product
```
mutation {
  deleteProduct(where: {
    id: "5ca5aa16576454000c387b4e"
  }) {
    name
    price
    country
  }
}
```