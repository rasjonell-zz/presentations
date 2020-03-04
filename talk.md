<style>
  section {
    font-size: 24px;
  }
</style>

# Monolith design:

One of the most common architectural patterns is the monolith design.

In this scenario we have a front-end client (web or mobile) talking to the back end composed of the API and a database.

The API layer apart from serving endpoints also holds all the code from both Business Logic and Data Access layers.

This, for relatively big projects, results in a huge codebase that is not easy to manage. For our demo project this means that the API layer will have all the functionality for authentication, sessions and users management, all the logic related to creating posts and comments, and recommendations/suggestions.

This means that your teams cannot scale their product areas independently and after some time very few people or even no one in the company will be able to comprehend the entirety of the application. Consequently onboarding new engineers on this sort of codebase becomes unnecessarily painfully.

---

# Microservice design:

The microservice architectural pattern mostly solves these problems.

You can see in the diagram here that we modified our API layer to only serve as an endpoint which itself talks to various services, each responsible for its own area of concern.

Separating concerns in this way creates a sea of opportunities. One benefit of this pattern is that each service is encouraged to be small in size. This enables different teams in your company to scale these services independently.

If you expose your microservice interface with a standard protocol such as a REST-ful API, you will be able to use them outside of your application. For example we can turn the recommendations/personalized suggestions area of the application into its own microservice and let the community use it to build bots and services.

But of course this isn't _the_ perfect model. One major problem is that your data domain code is coupled with the Business Logic Layer. In the example here all the microservices talk to the same database, but even if you introduce stricter separation and have a different database for each service, your services will still hold all the code for talking to these databases.

---

# Separate Data Access Layer

To solve this problem, we can introduce a new layer of separation. In the diagram here you can see that in order to reach the database, our microservices go through a Data Access Layer.

Adding this layer results in de-duplication of data domain logic previously spread across different microservices. Now we have a clear separation between our Presentational Layer, Business Logic, and Data Access Layers.

The problems caused by this model are probable performance issues and network overhead. In order for a request to be completed it needs to go through the API then to one of the microservices which themselves will make a request to the Data Access Layer which will then go and finally talk to the database and get back to you with a response.

---

# The Foxx Way.

We can solve these problems by choosing Foxx microservices as our Data Access Layer.

In the graph here you can see that the microservices that represent the Business Logic Layer directly talk to the database. However one major difference here is that now we have extended our database API.

Essentially ArangoDB provides HTTP endpoints for all kinds of operations. So what DB drivers do is just expose an interface that you can use to talk to the database. With Foxx microservices you can extend that API meaning you can write domain specific logic inside your database and expose them trusted clients.

A major benefit is performance. Foxx Services have **native** access to in-memory data thus they can directly access and modify it without additional network calls.

Another opportunity this provides is that you can make your DAL services as small as possible for extra modularity and stricter separation of concerns.

Coupled with our TypeScript powered template we would have modular, performant, and type-safe microservices.
