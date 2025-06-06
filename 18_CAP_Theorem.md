# CAP Theorem 

CAP Theorem is like the golden rule of distributed databases. If you ever plan to design a system that runs on multiple servers (aka distributed system), you NEED to know this.

---

## What Does CAP Stand For?

It stands for **Consistency**, **Availability**, and **Partition Tolerance** — the big three pillars of distributed systems. But here's the twist — you can only pick **two out of these three** at any time. Yep, that's the CAP Catch!

---

## Let's Break Down the Trio

### 1. Consistency (C)

Imagine you're on Instagram, and you post a new pic. Consistency means that no matter which server your friend is connected to — the moment you hit post, your friend sees that pic instantly. Everyone sees the same data at the same time. No outdated stuff.

> Think of it as: "One truth for all."

### 2. Availability (A)

This means your system is *always on*. You ask it something? It replies. Even if it doesn't have the latest update, it'll still give you *some* data rather than erroring out.

> Think of it as: "I’ll always answer your call — even if I’m a little outdated."

### 3. Partition Tolerance (P)

Now imagine one of your servers is in Delhi, another in Mumbai, and the internet cable between them breaks. Partition Tolerance means: "No worries bro, the system will keep running on both sides like nothing happened."

> Think of it as: "Survive the breakup and keep moving."

---

## What Does the CAP Theorem Say?

You can only pick TWO out of these THREE. Let’s see what happens when you pick different pairs:

* **C + A (Consistency + Availability):** Great! Until your servers can’t talk to each other. You’ll have to shut things down until communication is restored.
* **C + P (Consistency + Partition Tolerance):** You’ll get the same, latest data — but the system might say "Sorry bro, I’m busy" when under network issues.
* **A + P (Availability + Partition Tolerance):** Always online and resistant to network failures — but might show different data from different servers.

---

## Where Do NoSQL Databases Fit In?

Most NoSQL databases love **Availability + Partition Tolerance (AP)**. They’re like: "Keep it fast and available, bro! If the data’s slightly behind, no big deal."

Different databases prioritize different things:

* **MongoDB:** Generally leans AP.
* **Cassandra:** Also AP.
* **HBase:** CP mostly.

So your choice depends on what you care about more — speed, consistency, or fault-tolerance.

---

## Summary Time

CAP Theorem is like choosing two out of your three favorite desserts — you can’t have all three.

* **Consistency:** Everyone sees the same latest thing.
* **Availability:** System is always there for you.
* **Partition Tolerance:** System works even if servers stop talking.

Pick wisely when designing your system. And yeah — every choice comes with a cost.

---

