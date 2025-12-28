---
title: 'Rebuilding the Web Router with Regex'
description: 'A continuation of my first post'
pubDate: 'Dec 15 2025'
heroImage: '../../assets/Framework.java (1).png'
---


In the modern Java ecosystem, we are taught that @GetMapping("/users/{id}") is the starting point of an application. We treat it as a fundamental truth. But during the development of my framework, I wanted to know the cost of that convenience. Behind that annotation lies a massive engine of Reflection and Runtime scanning. For a minimalist system, I wanted something more transparent: The Regex Router."

The Synthesis (The Logic of the Match) "I realized that at its core, web routing is just a pattern-matching problem. A URL is a string; a controller is a function. The 'magic' is simply the bridge between them.

Instead of using Reflection to scan classes, I implemented a Route object that stores a compiled java.util.regex.Pattern. When a request hits the server, we don't ask the JVM to find a method—we ask the Regex engine to find a match.

This shift changed how I handle dynamic parameters. By using Named Capturing Groups in Regex, I could extract variables like id or slug directly from the path during the matching phase. No heavy parsing, no intermediate objects—just a direct mapping from the URL string to the handler context."

The Insight (Value for the Reader) "Writing an explicit router taught me two things that a high-level framework never would:

The Cost of Abstraction: Reflection is powerful, but it's a 'runtime' cost. Compiled Regex is a 'startup' cost. For high-performance, low-latency microservices, the difference is measurable.

Predictable Debugging: When a route fails in Spring, you’re often digging through stack traces of proxy classes. When a Regex route fails, you just test the string against the pattern. It’s binary; it either matches or it doesn't.

In Conclusion, I'd like to say that "We often use heavy frameworks because we’re afraid of the 'low-level' stuff". But Regex isn't scary—it's precise. By taking control of the routing logic, I didn't just make my framework faster; I made it more predictable. In the next post, I’ll look at why I chose to handle the HttpExchange context manually instead of using a standard Wrapper.