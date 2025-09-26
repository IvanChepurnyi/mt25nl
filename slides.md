---
theme: dracula
canvasWidth: 700
layout: cover
text-align: center
title: Redis Cache is considered harmful
---

# Redis Cache is considered harmful* 

<sup>* in 99% of the cases</sup> 

---

# About me

<v-clicks>

🫶 Passionate about open source projects

🚀 Expert in optimizing web appplications

👴🏻 One of grand-parents of Magento

🧑‍🚒 Experienced in putting out fires on production systems

</v-clicks>

---
layout: fact
---

# Redis is a **Database**

---
layout: fact
---

<img src="/cache-internals.svg">

---

# Product Save

<v-clicks>

➡️ Clears cache by defined tags

🔃 Loads list of keys from cache tag entry

⛔ Deletes keys one by one

</v-clicks>

---
layout: fact
---

# Results in 1k+ Redis Ops

---
layout: fact
---

## Don't use Redis for caching products

---

# Fix these instead

<v-clicks>

🚀 N+1 queries with pre-loaders

✅ Use `used_in_product_listing` attribute

🗂️ Utilize / write indexers instead

</v-clicks>

---
layout: fact
---

<img src="/cache-types-part1.svg">

---
layout: fact
---

<img src="/cache-types-part2.svg">

---
layout: fact
---

<img src="/cache-types-part3.svg">

---
layout: fact
---

# Configuration Cache

---

# Problem: Configuration Cache

<v-clicks>

🤦🏻 700KB cache entry size on 3 store views

📁 99.9% of uncached time spend on reading xml files

</v-clicks>

---

# Time spent on DB

<v-click>

<img src="/time-spend-on-db.png" class="m-15 h-100%" />

</v-click>

---

# Better Approach

<v-clicks>

⚙️ Store each configuration scope as PHP include

📦 Loads data from DB for a scope as value override

</v-clicks>

---
layout: fact
---

# Layout Cache

---

# Problem: Layout Cache

<v-clicks>

🔑 Each unique entity has its own cache key for layout

🧩 Most of the layout is the same across the same entity type

📈 On large catalogs, cache can grow into 20Gbytes+ overtime

</v-clicks>

---

# Better Approach

<v-clicks>

⚙️ Store each merged layout handle scope as PHP include

📦 Loads data from DB for widgets

</v-clicks>

---
layout: fact
---

<img src="/cache-types-better.svg">

---
layout: fact
---

# Collection Data

---

# Example: Configurable Products

<v-clicks>

🔄 Each time you use `getUsedProducts()` data gets cached in Redis

📈 Cache size grows with your catalog

🚫 Too volatile as it gets flushed on almost every product sale

</v-clicks>

---
layout: fact
---

# Fix the N+1 problem

---
layout: fact
---

<img src="/cache-types-better-part2.svg">


---
layout: fact
---

# Block HTML Cache

---

# Example: Price Block Cache

<v-clicks>

📈 Cache size grows with your catalog

🚫 Too volatile as it gets flushed on almost every product sale

</v-clicks>

---
layout: fact
---

# Fix the N+1 problem 

---

# Example: Top Menu

<v-clicks>

⏲️ Slow generation because of an in-effective query

</v-clicks>

---

# Better Approach

<v-clicks>

⚙️ Move cache into FPC by `ttl` attribute

🚀 Optimize a query to not use `LIKE '%/2/%`

</v-clicks>

---
layout: fact
---

<img src="/cache-types-better-part3.svg">

---
layout: fact
---

# Good News 

---

# Sponsorship Program

https://github.com/sponsors/EcomDev/

Sponsors get perks:

<v-clicks>

- Early access to build optimizations
- Access to N+1 optimization packages
- Access to Adobe Commerce specific optimizations

</v-clicks>

---
layout: fact
---
# Thank You!

Access slides here:
https://ivanchepurnyi.github.io/mt25nl/
