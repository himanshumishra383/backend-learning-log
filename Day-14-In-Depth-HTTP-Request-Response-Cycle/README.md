# Day 14 – In-Depth HTTP Request–Response Cycle

## Why this topic?
Every web action (page load, API call, login, click) runs on the HTTP request–response cycle.
Understanding this removes confusion around APIs, statelessness, retries, and failures.

## Core idea
Client asks → Server responds → Connection ends (logically).

HTTP is not magic. It is disciplined message passing.

## What you’ll learn
- How a request starts
- Where DNS fits
- How connections are built
- How requests & responses are structured
- Why HTTP is stateless
- Why most production bugs happen here

Refer to `NOTES.md` for the full breakdown.