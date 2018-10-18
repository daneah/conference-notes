# "Evolution of API Design" by [Eric Baer, Formidable](https://www.twitter.com/ebaerbaerbaer)


### Early on

API design as we know it now was mostly theoretical in the 1960s

#### Remote procedure calls (RPCs) where a client causes a method to execute on a remote server

Pros:
- Minimal network overhead
- Request only what you need
- Continuity between local and remote

Cons:
- Tight coupling between client/server
- Proliferation of API methods
- Lack of introspection

#### Simple object access protocol (SOAP) for exchanging structured information decoupled from implementation

Pros:
* Removes coupling between frontend and backend code via declarative data
* Highly structured data
* Introspection and tooling

Cons:
* Difficult to use without tooling
* More data than you need
* Complicated


### Now-ish

#### Representational state transfer (REST) is a stateless architecture for requesting resources over HTTP using URIs

Changes thinking from modeling interactions to modeling a domain
Easily cacheable and stateless

Example:
Querying posts with authors
Takes many API calls (one for list of posts, n for n posts, m for m authors, 1 + n + m)

Weaknesses:
* Chatty (TCP isn't good with multiple requests)
* Returns too much data (complete resource instead of just what's needed)
* Lacking in introspection (hard to generate documentation without strict self-imposed conventions)

Latency: 25ms-150ms


### Soon-ish

Imagine a protocol with:
* Minimal HTTP traffic
* Minimal payloads
* Human-readable syntax
* Rich tooling
* Preserved local reasoning - cohesion, encapsulation, separation of concerns

Express data naturally, then work backward

```graphql
{
    posts {
        title
        author {
            name
        }
    }
}
```

#### DANGER
Runs the risk of creating _more_ calls by making many granular queries. Merge like queries together!
Use compiler to extract requests, merge them, cache them, etc.
Typed schema allows deep introspection and rich tooling
**Plot twist**: It's GraphQL!

#### GraphQL
It's a spec, not an implementation
Just a type system and query language, i.e. an abstraction of the data source
Has implementations in many languages, including Python
Created by Facebook and used by sites like GitHub
