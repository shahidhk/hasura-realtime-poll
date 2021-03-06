# Important: Moved to [hasura/graphql-engine](https://github.com/hasura/graphql-engine/tree/master/community/examples/realtime-poll)

The contents of this repo have been moved to [hasura/graphql-engine](https://github.com/hasura/graphql-engine/tree/master/community/examples/realtime-poll). Please create all issues and pull requests there.

---

# hasura-realtime-poll

A demo application to showcase real-time capabilities of [Hasura GraphQL
Engine](https://github.com/hasura/graphql-engine).

The Realtime Poll application is built using React and is powered by Hasura
GraphQL Engine over Postgres. It has an interface for users to cast vote on a
poll and the results are updated in the on-screen bar chart, in real-time.

The application makes use of Hasura GraphQL Engine's real-time capabilities
using `subscription`. There is no backend code involved. The application is
hosted on GitHub pages and the Postgres+GraphQL Engine is running on Postgres.

- Checkout the [live app](https://shahidh.in/hasura-realtime-poll/).
- Explore the database using [Hasura
  Console](https://hasura-realtime-dashboard.herokuapp.com/console/data/schema/public).
  
# Running the app yourself

- Deploy Postgres and GraphQL Engine on Heroku:
  
  [![Deploy to
  heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/hasura/graphql-engine-heroku)
- Get the Heroku app URL (say `random-string-123.herokuapp.com`)
- Clone this repo:
  ```bash
  git clone https://github.com/shahidhk/hasura-realtime-poll
  cd hasura-realtime-poll
  ```
- [Install Hasura CLI](https://docs.hasura.io/1.0/graphql/manual/hasura-cli/install-hasura-cli.html)
- Goto `hasura/` and edit `config.yaml`:
  ```yaml
  endpoint: https://random-string-123.herokuapp.com
  ```
- Apply the migrations:
  ```bash
  hasura migrate apply
  ```
- Edit `HASURA_GRAPHQL_ENGINE_HOSTNAME` in `src/apollo.js` and set it to the
  Heroku app URL:
  ```js
  export const HASURA_GRAPHQL_ENGINE_HOSTNAME = 'random-string-123.herokuapp.com';
  ```
- Run the app (go the root of repo):
  ```bash
  npm start
  ```
