# Implementation of Atomicity and Durability in Transactions

Imagine you're running a secret vault of information, and every time you update something inside it, you want to be 100% sure that either the whole thing is updated properly or nothing changes at all. Plus, once you've locked in a change, not even a crash or power cut should undo it. That’s what **Atomicity** and **Durability** in transactions are all about.

---

## 1. Recovery Mechanism – Your Safety Net 🛡️

Bro, think of this like a safety rope while climbing a mountain. The **Recovery Mechanism** is built into every DBMS to handle accidents like system crashes. If something breaks mid-way, this mechanism pulls the database back to a safe and consistent state – like nothing bad ever happened.

---

## 2. Shadow-Copy Scheme – One Safe Copy at a Time

Let’s say you’re editing an important document. But just to be safe, you make a copy and work on that. If things go wrong, you still have your original. That’s exactly what the **Shadow-Copy Scheme** does:

* There's a disk pointer called the **db-pointer** that always points to the latest good version of the database.
* When a transaction wants to make changes, it creates a **new copy** of the entire database.
* The original becomes the **shadow copy** – untouched and safe.
* If the transaction crashes or fails, the new copy is trashed.
* If the transaction commits successfully, the db-pointer now points to the new version, and the old one is deleted.

---

## 3. How Atomicity Works in Shadow-Copy Scheme

You either do the full update or do nothing at all – no half-baked states. That’s Atomicity.

* If a crash happens before changing the db-pointer, the old shadow copy stays intact.
* If everything goes well, the pointer shifts to the new copy.

No in-between state. All or nothing.

---

## 4. How Durability is Ensured Here

You know how when you save a game, even if the console shuts down, you don’t lose progress? Same energy here:

* If a crash happens **before** the db-pointer update, we stick with the old copy.
* If it happens **after**, we go with the new one.
* The db-pointer acts like a bookmark, always pointing to the correct version.

Once you’ve committed, your changes are locked in forever. No crash can undo that.

---

## 5. Some Real Talk: Downsides of Shadow-Copy Scheme

* Copying the **entire** database for every little change? That’s a LOT of disk work – super inefficient.
* Updating the db-pointer has to be atomic too. It must succeed completely or not happen at all.
* Usually, this pointer is saved in a special disk block that supports atomic updates.

---

## 6. Log-Based Recovery – The Smarter Way Most Databases Work

Now, imagine instead of copying everything, you just keep a **diary** of all the changes. That’s what **log-based recovery** does.

* Before applying any change, we write it in a **log file**.
* This log is stored safely so it can be replayed or rolled back in case something goes wrong.

Much faster, much cooler.

---

## 7. Two Styles of Log-Based Recovery

### a) Deferred Database Modifications – "Wait Before You Write"

* We write all the changes to the log **first**.
* Only **after** the transaction commits do we apply changes to the actual database.
* If the transaction crashes before commit? Ignore the log, nothing changes.
* If it commits and then crashes? Just redo everything from the log.

### b) Immediate Database Modifications – "Change Now, Fix Later"

* Changes are applied **immediately**, even before the transaction commits.
* If the transaction fails, we use the log’s old values to **undo** changes.
* If the transaction commits, and a crash happens after, we use the new values to **redo** them.
* But logs are **always** written first, before applying anything.

---

## 8. Handling Failures Like a Pro

* If a crash happens **before** the transaction finishes, the log helps us **undo** the changes.
* If it crashes **after** a commit, the log helps us **redo** everything.

That’s how we make sure Atomicity and Durability always hold up, no matter what.

---

## Summary – Like Explaining to Your Best Friend

Bro, here’s the deal:

* Atomicity = All or nothing. No halfway.
* Durability = Once done, always done. No rollback after commit.
* **Shadow-Copy** is like making full copies and switching when done – safe but slow.
* **Logs** are like smart journals – we write down changes and use them to fix or finish the job.
* Real-world databases use logs because they’re way faster and scalable.

In short, databases take their transactions seriously – just like we take care of our secrets or important chats. Once saved, always safe. All or nothing, every single time.
