---
title: 'When I Created Something Unique'
description: 'Lorem ipsum dolor sit amet'
pubDate: 'Dec 20 2025'
heroImage: '../../assets/Framework.java.png'
---

The Black Box Problem: Why Did I Build a Web Framework From the Socket Up?
Modern software development is built on layers of abstraction. We use frameworks that handle everything from dependency injection to request routing with a single @Annotation. It’s efficient, but it’s also dangerous. We’ve become "Library Glue Developers"—experts at connecting black boxes without actually knowing what’s happening inside them.

I reached a point where "it just works" wasn't a good enough answer for me. I wanted to see the grain of the wood.

I didn't build a Java framework to compete with Spring Boot; I built it to audit my own understanding of the HTTP protocol. By stripping away the bloat of traditional enterprise frameworks—specifically the heavy, opinionated nature of tools like Angular on the frontend—I forced myself back to the primitives.

What I realized is that 90% of what we call "magic" in development is just well-hidden complexity. When you write your own routing engine using Regex, or handle a raw HttpExchange context, you stop seeing "features" and start seeing "flow." You realize that a framework is just a set of opinions on how data should move through a socket.

Therefoe, Building from scratch taught me three things that using a framework never could:

Performance is Transparency: You can’t optimize what you can't see. When you own the code, "memory leaks" aren't mysteries; they are visible mistakes in your own logic.

The Power of Minimalism: Most projects don't need a 50MB runtime to serve a JSON object. We've traded simplicity for the "safety" of heavy abstractions, often at the cost of speed and cold-start times.

Control over "Magic": I now view frameworks as a choice, not a necessity. I can use them more effectively because I know exactly which "black box" they are replacing.

My Blog isn't for tutorials or "How-To" guides. It’s a log of my own technical synthesis—pulling apart the systems we take for granted to see how they tick. 

I’m Akshith, and I’m interested in the code that exists before the framework starts.