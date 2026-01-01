---
date: '2025-12-31T07:40:00-05:00'
draft: false
title: 'Better Late Than Never: My First Open Source Contribution'
tags:
  - technical
  - open-source
  - claude-code
---

I recently made my first open-source contribution by fixing a bug in the OONI Backend project. What started as browsing "good first issue" labels turned into an exciting journey through internet censorship detection, load balancing algorithms, and Docker debugging. With Claude Code as my pair programming partner, I navigated unfamiliar code and successfully submitted [PR #1048](https://github.com/ooni/backend/pull/1048). Here's how it went.

## Why I Finally Decided to Contribute

Here's my honest truth: I've been a software engineer for 5+ years, using countless open-source tools daily, and I'd never contributed back. Not once. I felt guilty about it, especially when I saw projects like ingress-nginx struggle to find maintainers and eventually get deprecated. I used that tool constantly, knew how valuable it was to the Kubernetes community, and yet I never helped.

I kept putting it off. Too intimidating. Too busy. Too many excuses.

But recently, I decided to finally do something about it. Turns out, there are lots of ways to contribute - starring projects ⭐️, sponsoring maintainers 🪙, or tackling a "good first issue" 🛠️. It doesn't even have to be code - documentation improvements count too. I chose to dive into an actual issue, and honestly, it wasn't as scary as I'd built it up to be in my head.

If you're interested in contributing, [this guide](https://opensource.guide/how-to-contribute/) is a great starting point. 

## Finding the Right Project

I started by looking for projects I actually cared about - privacy, security, tools that help with censorship and protect journalists from digital threats. That led me to organizations like EFF (Electronic Frontier Foundation), Citizen Lab, and OONI.

OONI caught my attention because it's written in Python, which is my forte. The project detects internet censorship worldwide - pretty cool stuff that actually matters. But when I opened the repository, I was immediately overwhelmed. The codebase felt massive, and I honestly thought about giving up more than a few times.

This is where Claude Code became invaluable. Instead of trying to understand every single line of code (which was paralyzing), I asked it to give me a structured plan. It helped me focus on just the parts I needed to understand for this specific issue - a high-level overview, not a deep dive into the entire codebase. That systematic approach made the intimidation manageable.

## The Journey

I found [Issue #973](https://github.com/ooni/backend/issues/973) - a failing test that seemed manageable. The test expected 4 test helper servers but the function was returning 5. Simple enough, right?

Not quite. The codebase was unfamiliar, and the function involved load balancing logic I didn't immediately understand. This is where Claude Code became invaluable as a learning partner.

### Learning Through Questions

Instead of diving into random files or trying to understand the entire codebase, I used Claude Code to guide my exploration through strategic questions:

- "Why is the IP address converted to a number?" - Turns out it's for deterministic distribution, so the same IP always gets the same helper server.
- "Why modulo 100?" - For clean percentage-based traffic distribution.
- "Why the shift calculation?" - For load balancing across servers.

Each answer built my mental model piece by piece. I wasn't just fixing a bug blindly - I was understanding *why* the code worked the way it did.

Of course, the journey wasn't without hiccups. When I tried to test locally, Docker builds failed due to a deprecated Debian repository. With Claude Code's help debugging the issue, I found and fixed the problem in the build script. Then I could finally run the tests and verify my fix worked. That moment when the tests passed? Pure satisfaction.

### The Submission

After ensuring all tests passed, I created a detailed commit message explaining not just *what* changed but *why* it changed. Then I submitted [PR #1048](https://github.com/ooni/backend/pull/1048) using the GitHub CLI.

The entire process - from finding the issue to submitting the PR - took one focused session. The fix itself? Just a few lines of code. But the learning journey made it worthwhile.

## Key Takeaways

**You don't need to know everything to contribute.** I'd never seen the OONI codebase before, but by asking the right questions and following the code, I understood enough to fix the bug. That's the beauty of "good first issues" - they're truly beginner-friendly by design.

**Testing locally builds confidence.** Debugging the Docker build issue and verifying my fix worked gave me the confidence to submit. That "I want to be 100% sure this works" mindset paid off - no surprises for the maintainers.

**Strategic learning beats comprehensive learning.** I didn't need to understand the entire codebase. With Claude Code's help, I focused on just the parts relevant to my issue - load balancing logic, deterministic distribution, and how the test helpers worked. That targeted approach made the overwhelming feel manageable.

## What's Next?

The PR got merged, and honestly, that felt great. Not just because my code is now part of OONI, but because I finally did the thing I'd been putting off for 5 years.

Now I'm looking for the next issue to tackle. The first contribution was the hardest - breaking through that initial intimidation barrier. Now that I know the process, I'm actually excited to do it again.

If you've been putting off your first contribution like I did, I'd say go for it. Find a project you care about, look for a "good first issue," and just start. You might surprise yourself with what you can figure out.

---

**Resources:**
- Issue: https://github.com/ooni/backend/issues/973
- PR: https://github.com/ooni/backend/pull/1048
- OONI Project: https://ooni.org
- My Fork: https://github.com/RajsimmanRavi/ooni-backend
