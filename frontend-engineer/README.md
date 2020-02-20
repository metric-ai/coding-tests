# Front-end Engineer coding test

There are many expense tracking apps out there. Being extremely powerful at
breaking down expenses by categories and reporting, they usually don’t provide
an answer to one simple yet important question: “How the total balance has been
changing over time”. The answer to this question, given in a visual form, can be
used see a big picture at a glance, reveal some tendencies, project them into
the future, set realistic financial goals and even motivate to reconsider
spending habits.

The task is to build a web app which displays balance over time chart from a
series of financial transactions. There is a
[GraphQL API](https://cash.sergees.com) which provides such transactions since a
given date. Here is an example of its’ output fragment:

```json
{
  "id": "45",
  "date": "2019-01-14",
  "type": "EXPENSE",
  "account": "Bank of Hawaii",
  "amount": -103.25,
  "destinationAccount": null,
  "destinationAmount": null
},
{
  "id": "46",
  "date": "2019-01-14",
  "type": "TRANSFER",
  "account": "Business",
  "amount": 1205.8,
  "destinationAccount": "Cash",
  "destinationAmount": 1205.8
},
{
  "id": "47",
  "date": "2019-01-14",
  "type": "BALANCE_ADJUSTMENT",
  "account": "Cash",
  "amount": 2121.04,
  "destinationAccount": null,
  "destinationAmount": null
},
...
```

Each transaction is an action over one or two accounts. There are four possible
types of transactions:

- Income. Adds a positive amount to an account.
- Expense. Adds a negative amount to an account.
- Transfer. Moves funds between two accounts.
- Balance Adjustment. Directly overrides the balance of an account.

This information is enough to calculate the **total balance** across all the
accounts for any given date in the series of transactions. The series of such
total balances is **balance over time**. The goal of the app to visualize it as
a chart.

## Web app requirements

- The app uses React and a charting library.
- The app displays the chart at the center of the web page.
- The horizontal axis of the chart represents dates.
- The vertical axis of the chart represents balances.
- The app allows to pick a start date.
- The app displays a loading indicator while the data is being loaded from the
  API and processed on the frontend side.
- The source code is available for review in github.
- There is a README file with brief steps describing how to get it up and
  running for testing purposes.

## Additional requirements

These requirements are not necessary to accomplish the task but any of them will
be a plus:

- The app is available as a live demo.
- The app allows displaying balance over time per weeks (there is a picker with
  “By days” and “By weeks” options).
- The app allows displaying balance over time for individual accounts (there is
  a picker with account options and the “Total” option selected by default).
- The app allows reloading the data from the API by clicking a “Refresh” button.
- The source code is formatted using [prettier](https://prettier.io/).
- The app has a few unit tests (at least testing the code which transforms the
  data).

## Some useful links

Mere recommendations:

- Full featured charting library for React: http://recharts.org/
- Financial charting library by TradingView:
  https://www.tradingview.com/lightweight-charts/
- GraphQL client for React:
  https://www.apollographql.com/docs/react/api/react-apollo/
- GraphQL browser and introspection tools:
  - https://github.com/graphql/graphiql
  - https://insomnia.rest/graphql/
- Free static web site deployment:
  - https://www.netlify.com/
  - https://zeit.co/
