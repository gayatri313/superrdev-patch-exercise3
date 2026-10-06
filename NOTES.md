# Patch Exercise Notes

## Summary of changes

- Fixed task search filtering by grouping the title/description OR conditions before applying the status filter.
- Removed an artificial Thread.sleep delay from TaskController that unnecessarily slowed API requests.
- Fixed the frontend loading state so it stops when a task request fails.
- Added validation for page and pageSize so invalid values return a clear 400 Bad Request instead of causing a server error.

## What I chose not to change

I did not modify the Oracle PL/SQL reference artifact because it does not run locally and the exercise asked for a focused patch. I also did not make broader refactoring or validation changes that were outside the main issues I fixed.

## Biggest remaining risk

The controller loads all matching tasks into memory and then performs pagination using a sublist. This could become a performance and memory problem with a much larger dataset.

## Tools / AI used

I used VS Code, GitHub Desktop, browser/API testing, and ChatGPT to help inspect the code, reason about the bugs, and understand possible fixes. I manually tested the API and frontend behavior after making the changes.