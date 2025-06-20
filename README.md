# 100-year-stack

Inspired by [Alexander Petro’s talk](https://www.youtube.com/watch?v=lASLZ9TgXyc), this repo documents and possibly offers an implementation for a 100 year web service.

## Goals

- prevent breaking changes by choosing very few and stable dependencies
- serve a small to medium size audience
- be fast and reliable by using web standards
- make using web standards convenient without adding custom APIs

## Tech Stack

There are a lot of choices to achieve these goals. Alexander also suggests a tech stack. This is my interpretation in 2025:

- **fastify.js**<br>
  There are a lots of router libraries for the JS server ecosystem. While Alexander suggests using `express`. It has a fewer breaking changes than fastify (10 years between v4 and v5). But it’s also 4 to 5 times slower than fastify. Fastify released major versions after about 2 years, which is a good timeframe in my opinion and they have an [LTS commitment](https://fastify.dev/docs/latest/Reference/LTS/).
- **SQLite**<br>
  Probably the simplest database that is also battle-tested and has a very strong [LTS commitment](https://sqlite.org/lts.html).
- **CSS**<br>
  It might be weird to now just list a browser technology, but this is intentional. CSS has evolved and is evolving to offer everything that is needed to build robust and flexible design systems. Every layer on top of it, is an unnecessary liability.
- **HTML**<br>
  Whatever can be done with HTML, should be done with HTML. This also includes using native web components if applicable.
- **HTMX/Datastar**<br>
  If none of the technologies above suiffce, JavaScript may be used. JavaScript on the client side is a tricky subject, as there is an ocean of libraries with frequent breaking changes. [HTMX](https://htmx.org/essays/future/) and [Datastar](https://data-star.dev/essays/the_road_to_v1) are both committed to long term stability. Datastar hasn’t reached 1.0 at the time of writing, so it’s unclear yet, if it can be a proper alternative to HTMX.

## Todo

- [ ] add basic fastify server
- [ ] add SQLite database with proper pragmas
- [ ] add example routes with db connection and rendering
- [ ] add CSS structure using its capabilities like @layers, custom properties, view transitions etc
- [ ] add HTMX/Datastar
- [ ] add Dockerfile for easy setup
