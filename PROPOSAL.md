# What is RESTful Hooks black magic we talk about?

REST Hooks is a collection of patterns to implement Web Hooks as subscriptions. These subscriptions are manipulated via a REST 
API just like you would for any resource.

See [here](http://resthooks.org/) for more. The kind folks from [Zapier](https://zapier.com/) put it together and shared 
it with the world. We will attempt to do the same.

## Why are you trying to do this?

Web Hooks are a powerful async pattern for (near) real time service communication (RPC). Is specially helpful for event-driven, reactive architechtures. We believe that we can leverage this pattern in some of the projects we are delivering.

It will help us compose web services to offer simple solutions to complex scenarios.

## PHP

This project aims to be a PHP implementation of the pattern. There are already implementations in other languages/web frameworks like Python/Django, RoR, or Sails in Node.

## Minimum Implementation
According to the documentation, this is the minimum viable implementation:

- A Mechanism to manage subscriptions.
- A List of events.
- A Mechanism to send hooks.

# Example Use Cases for this implementation

## RESTful Webhooks + Wordpress

We use Wordpress as a "Headless CMS" where Articles (Posts) are created. Whenever there's a new post, we propagate that event to our REST Hooks service. 

That in turn will trigger **Web hooks** to our Article Enrichment Service, Article Auto-Tagging Service and will also persist the Article  in our JSON Data Store so it's available thru a JSON:API RESTfull API.

<img src="https://cloud.githubusercontent.com/assets/219427/24521072/03cfedf8-1548-11e7-9c99-6f827b1e04eb.png" width="100%" />
