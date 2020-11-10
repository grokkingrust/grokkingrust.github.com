---
layout: article
title: "Built in: Dependency locking"
description: "."
tags: [rust, dependencies, crate]
---

You want your builds to be reproducible.  One aspect of this is to have dependency / package management.  Rust has that with [Cargo](https://doc.rust-lang.org/cargo/).  But even with dependency management, you can still get into trouble trying to reproduce your builds, especially when you come back to things after a period working elsewhere.  You want to know for sure that your dependency versions (and the versions of their dependencies too) are locked. And when you upgrade dependency versions, you want to do so consciously, not by accident.

Rust has support for that too. 

As the [Rust book](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html) states:

> When you build a project for the first time, Cargo figures out all the versions of the dependencies that fit the criteria and then writes them to the Cargo.lock file. When you build your project in the future, Cargo will see that the Cargo.lock file exists and use the versions specified there rather than doing all the work of figuring out versions again. This lets you have a reproducible build automatically. In other words, your project will remain at 0.5.5 until you explicitly upgrade, thanks to the Cargo.lock file.

That's handy.
