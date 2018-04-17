# Product Store

A NodeJs Express application that servers product store APIs for the customer, contains multiple APIs such as Product, Inventory, ProductList (Can be filtered by Product)

## Getting Started

The App is built and run as below

### Installing

To run the app just intall the required dependencies and and hit npm start i.e.

---> Go to the project directory and

```
npm install
node app.js
```

### API sources and information

The APP is to give an idea about how to generate & call GET APIs using nodejs and express. I've initially called a GET API to get the data and create three GET APIs, two reflects the same called API and other aggregated list of called API that is generated from the above two APIs. We can pass in a filter that filters the product list from the available all the list of products.
|
|\_\_ APIS : /api/products
/api/inventory
/productList
or
/productList/:productName

Data obtained for each of the APIs is as follows for example:

### /api/products:

```
[
    {
      "name": "shirt",
      "price": 15
    },
    ....
```

### /api/inventory

```
{
    "inventory": [
      {
        "name": "shirt",
        "inventory": 12
      },
    ....
```

### /productList

And repeat

```
[
    {
      "name": "shirt",
      "price": 15,
      "inventory": 12
    },
```

additional parameter can be passed into url to filter the list as:
/product/shirt i.e. /product/:productName

The application also handles the errors nicely and displays it to user as a HTML clearly and was built using pub framework

when a filter was provided and the list doesn't contain the product then a response is generated as follows:

```
## Please Verify the data entered
## {error.stack: No Data Matched with the list}
```

other errors with related to code are also thrown in the same way.

The application api call without defining the API i.e. just using a GET '/' or GET '/api/' will return a response as below

```
{
    "message": "hooray! welcome to our product api!"
}
```

## server hosting and port

The server when we run

```
node app.js
```

is hosted at, FYI we can easily change the port when we host it my changing the value of port in

```
----
   |__ app.js file
```

change the port number to the one that you wanted, I have here set the port to 8080

```
http://localhost:8080/
```

follow shown API endpoints to see the data

## Datasource folder

This is folder is just for reference if in case you want to use to get the data initially, you can replace the path in below files:

```
product.js
productList.js
inventory.js
```
