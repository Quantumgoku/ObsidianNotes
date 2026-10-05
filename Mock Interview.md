---
created: 2026-09-20T23:00
updated: 2026-09-20T23:11
---
1st 58/100
Where to improve

- •Explain the impact of merging and rebasing on commit history in more detail.
- •Clarify the distinctions between PUT and PATCH requests, and provide more context on the implications of 4xx and 5xx errors.
- •Detail a process for identifying the root cause of a 'cannot read property of undefined' error, including how to pinpoint a data assumption bug and propose a solution.
- •Elaborate on the data model, short code generation, and redirect flow for a URL shortener design.
- •Provide a more precise description of the note-taking API, including data models, status codes, and specific details about user authentication.

Questions & ideal answers:
How would you describe a typical feature branch workflow, and what's the difference between merging and rebasing a branch?
Answer:
- You'd start by creating a new branch off the main/trunk branch, naming it something descriptive for your feature or fix.

- All your work for that feature would then be committed to this branch.

- Instead of directly pushing these commits to main, you'd open a pull request to propose integrating your changes back into the main branch.

- Merging a branch creates a new commit, called a merge commit, that combines the histories of the two branches. This preserves both branches' commit history as it was originally.

- Rebasing takes your branch's commits and replays them on top of the target branch (usually main). This results in a more linear history, but it also rewrites the commit hashes in your branch.

- Rebasing can be risky because it changes the history of your branch, potentially causing conflicts and confusion for others who have already pulled from it.

- Personally, I'd rebase my feature branch before opening a pull request to keep my history clean and linear. For integrating shared or public branches, merging is usually a safer choice.

Basically explain everything like explaining to a child.

Your app crashes in production with a 'cannot read property of undefined' error on the user's profile page. How do you track down what's going wrong?

Answer:
- First, I'd check our logs and error tracking system for the stack trace. That'll pinpoint the exact line of code and the specific field that's undefined.

- This type of error usually points to a data assumption bug. My code probably assumes a field always exists (like `user.address.city`), but it's missing or null for some users.

- I'd investigate what differentiates the affected users from those who aren't experiencing the crash. Are they newer accounts that haven't filled out their profiles? Did they sign up before a schema change that might have affected data formatting?

- To fix this, I'd use defensive checks and optional chaining to handle cases where the field might be undefined. For example, instead of `user.address.city`, I'd use `user.address?.city || 'Unknown'`. This provides a sensible fallback value instead of crashing.

- To ensure the fix works, I'd try to reproduce the issue with realistic data. I could pull an affected user's data (anonymized, of course) or set up a staging account with a feature flag that mimics their profile state.
I identified how to check logs and debug but the ideal answers vontained assumption like mismatch and example of it, differentiates with working users and failing users, fixes, local reproduction

How would you design a basic URL shortener, the kind that takes a long URL and gives you back a short one that redirects to it?
- We'd use a database table to store our data, with columns for:

- `short_code`: The shortened URL.

- `long_url`: The original URL.

- `created_at`: Timestamp of when the short URL was created.

- `expiry`: Optional, for setting an expiration date on the short URL.

- `owner`: Optional, to track who created the short URL.

- Short codes could be generated using a counter, incrementing with each new URL. To prevent collisions, we'd check if the counter value is already in use before saving. Alternatively, we could use a random string encoded in base62, ensuring uniqueness through hashing or other collision-handling techniques.

- When a user requests a shortened URL (e.g., `https://example.com/{code}`), our server would:

- Look up the `long_url` associated with the provided `short_code` in the database.

- If found, return an HTTP redirect (301 or 302) to the `long_url`.

- Since we expect a lot of reads (redirects) compared to writes (creating short URLs), we'd implement caching for popular short codes. This could be done using in-memory caches like Redis or Memcached to significantly reduce database load.

- We need to consider potential issues beyond the happy path:

- Duplicate submissions: Handle cases where the same long URL is submitted multiple times, ensuring we only store it once and redirect to the same short URL.

- Invalid/malicious URLs: Sanitize input `long_urls` to prevent vulnerabilities like cross-site scripting (XSS) and ensure they are valid URLs.

- Short code collisions: Even with collision-handling techniques, there's a small chance of collisions. Implement strategies like retrying with a new short code or using a different generation method.
I considered a high level working but ideal answer delve deep into algo for generation coallition handling, storage model, response status for redirection(301/302), I just said cache but explicitly tell in-memory cache example, handle issues 