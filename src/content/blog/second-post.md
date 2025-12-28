---
title: 'The ORM Illusion: Why I Chose Raw SQL for My Minimalist Stack'
description: 'My Post'
pubDate: 'Dec 1 2025'
heroImage: '../../assets/Framework.java (3).png'
---

We are often conditioned to use ORMs like Hibernate. We treat our database tables as if they are just collections of Java Objects. But this abstraction comes at a massive cost: N+1 query problems, lazy loading exceptions, and invisible joins. For my framework, I decided to break the illusion. I wanted to talk to my database in its native language: SQL."

But I realized that an ORM is essentially a translator that doesn't always understand the context. When you write a 'Repository' method, you lose sight of the execution plan.

By switching to JDBI or raw JDBC with RowMappers, I regained control over the most expensive part of my application: the I/O.

Instead of letting a framework 'guess' how to fetch a user and their posts, I write the JOIN explicitly. 

The result? 

I can see exactly how many indexes are being hit and exactly how much data is traveling over the wire. I’m no longer debugging 'Hibernate magic'; I’m optimizing relational logic.

Minimalism isn't just about fewer lines of code; it's about fewer layers of translation. By removing the ORM, I made my application transparent. In the next post, I’ll dive into the frontend: Why I’m building my UI without the overhead of heavy SPA frameworks.
