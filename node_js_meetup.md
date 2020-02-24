---
theme: gaia
_class: lead
paginate: true
color: #fff
backgroundColor: #002b36
marp: true
---

<!-- Global style -->
<style>
  h1 {
    color: #fff;
  }
  li {
    font-size: 32px;
  }
</style>

![bg left:40% 80%](https://www.arangodb.com/wp-content/uploads/2016/10/ArangoDB-logo-bg.svg)

# TypeScript Powered DAL Microservcies

https://rasjonell.tech

---

# How am I

![bg left:40% 80%](https://avatars1.githubusercontent.com/u/20546214?s=460&v=4)

- Software Engineer @ [GRÜV](https://gruv.me/)
  - Graph Databases
  - Real-Time Systems
  - Recommendation/Suggestion Systems
- OSS maintainer @ [Squash](https://github.com/SquashConsulting)
- Contributing to OSS related to [ArangoDB](arangodb.com/), [Elixir](https://elixir-lang.org/), [Phoenix](https://phoenixframework.org/).

---

<style scoped>
  section {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }
</style>

# What are we going to build

Short demo time!

---

![bg left:50% 95%](./basic_arch.svg)

<style scoped>
  h1 {
    margin-top: 100px;
  }
</style>

## Bloated API Layer.

- Presentation Layer (JSON API).
- Business Logic Code.
- Database Domain Logic Code.

Problems:

- No separation of concerns.
- Unable to scale independently.

---

![bg left:50% 95%](./microservice.svg)

<style scoped>
  h1 {
    margin-top: 100px;
  }
</style>

## Microservice Architecture.

- Separation of concerns.
- Ability to scale different areas independently.

Problems:

- Duplication of data domain logic.

---

![bg left:50% 95%](./dal1.svg)

<style scoped>
  section {
    padding-top: 10px;
  }

  h2 {
    margin-top: 0;
  }
</style>

## Separate Data Access Layer.

- Clear separation of concerns.
- Ability to scale BLL/DAL independently.
- No duplication of data domain logic.

Problems:

- Performance.
- Single point of failure.

---

## The Foxx Way

<style scoped>
  section {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }
  
  p {
    width: 100%;
  }

  img {
    width: 100%;
  }
</style>

![](./foxx.svg)

---

# Me on WWW

- [Blog](https://rasjonell.tech/)
- [Twitter](https://twitter.com/iRasjonell)
- [Mastodon](https://թութ.հայ/@gurgen)
- [Dev.to](https://dev.to/rasjonell)
