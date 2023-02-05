# `bitquery`

Bitquery is a GraphQL API that provides a flexible and efficient way to access and analyze blockchain data. By using GraphQL, Bitquery enables users to query only the data they need, rather than receiving a large amount of unneeded data. This results in faster, more streamlined access to blockchain data, and improved performance overall. More information can be found in the [official documentation](https://bitquery.io/)

## Requirements

Any GraphQL client can be used to access Bitquery. Using `requests` library in Python is recommended.

### Knowledge of GraphQL

GraphQL is a query language and runtime for APIs. It was developed and open-sourced by Facebook as an alternative to REST APIs. GraphQL allows for more efficient and flexible communication between the client and server, as the client can specify exactly the data it needs, rather than the server determining what data to send. This results in less over- or under-fetching of data, and improved performance compared to REST. GraphQL is used by many companies and organizations as a modern approach to API development.

Here is a [tutorial](https://graphql.org/learn/) for GraphQL.

## Sample Data

You can find sample data in [data/sample_bitquery](../data/sample_bitquery.json). The following lists a few items of the sample data.

```json
{
  "deposits": [
    { "date": { "date": "2020-12-01" }, "count": 6451, "amount": 206401.0 },
    { "date": { "date": "2020-12-02" }, "count": 1644, "amount": 52577.0 },
    { "date": { "date": "2020-12-03" }, "count": 1557, "amount": 49824.0 }
  ]
}
```

| Field  | Description                   |
| ------ | ----------------------------- |
| date   | The date of the deposit.      |
| count  | The number of deposits.       |
| amount | The total amount of deposits. |

## Usage

Alternatively, you can use `curl` to directly query the API with your API key.

```bash
curl -X POST -H "Content-Type: application/json" -H "X-API-KEY: <your api key>" --data '{"query":"{ ethereum { transfers { date { date } count amount } } }"}' https://graphql.bitquery.io/
```

You can also find usage example and some visualization in [Example](../examples/bitquery.ipynb)
