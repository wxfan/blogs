## Combing Data Source using Graphql

### 1. What is Graphql?
- Graphql is a query language for APIs and a runtime for fulfilling those queries with your existing data. Graphql provides a complete and understandable description of the data in your API, gives clients the power to ask for exactly what they need and nothing more, makes it easier to evolve APIs over time, and enables powerful developer tools.

### 2. transport protocal
- Graphql is transport protocal agnostic, it can be used with HTTP, Websocket, MQTT, etc.

### 3. Some of the key benefits of GraphQL over OData are:
• GraphQL does not require HTTP because it is transport-agnostic, so you could use alternative 
transport protocols like WebSockets or TCP.
• GraphQL has more client libraries for different platforms than OData has.
• GraphQL has a single endpoint, usually simply /graphql.

### 4. GraphQL query document format
```
query {
  hero {
    name
    friends {
      name
    }
  }
}
```

```
query getOrdersByDateAndCountry($country: String, $orderDate: String) {
 order(orderDate: $orderDate) {
 orderId
 orderDate
 customer(country: $country) {
 companyName
 country
 }
 }
}
```
### 5. GraphQL platform
-  Hot Chocolate enables you to create GraphQL services for .NET.

- Strawberry Shake enables you to create GraphQL clients for .NET.

- Banana Cake Pop enables you to run queries and explore a GraphQL endpoint using a Monaco-based GraphQL IDE.

- Green Donut enables better performance when loading data.
