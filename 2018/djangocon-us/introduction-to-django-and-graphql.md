# "Django and GraphQL" by Patrick Arminio


## GraphQL

* Takes a POST request whose body describes the shape of the data to return in the response
* Each field in the response is typed
* The schema can be introspected, which enables things like IDE autocompletion while building a request
* Supports query, mutation, and subscription actions


## GraphQL in Django

The `graphene-django` app adds url patterns and a way to use classes to create GraphQL APIs.
Authentication could be managed with Django sessions, HTTP headers, or tokens in query parameters.
