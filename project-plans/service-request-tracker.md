# Service Request Tracker

**Status** — Planned software project.

**Problem** — A small operations team needs to see which requests are open, how many are in each status, and how long completed requests took.

## Minimum implementation

- Use Python, FastAPI, and SQLite. Add a simple HTML and JavaScript page once the API works.
- Model requests with an ID, title, priority, status, creation timestamp, and optional resolution timestamp.
- Implement `POST /requests`, `GET /requests?status=open`, and `PATCH /requests/{id}`.
- Support a clear status flow: open, in progress, and resolved. Set the resolution timestamp when a request is closed.
- Use SQL to report counts by status and average resolution time for completed requests. Provide a command or fixture that preloads a small synthetic dataset.

## Completion criteria

- A reviewer can create one request, filter the open queue, resolve it, and see the change in the reported counts.
- Tests cover create, filter, resolve, and invalid status. One test checks the SQL report against fixtures with known totals.
- GitHub Actions runs tests on pushes and pull requests.
- The README shows a sample API request, the table schema, local setup commands, and a screenshot of the queue.

## Interview walkthrough

Explain why the resolution timestamp belongs in the data model, how the SQL excludes open requests from the average, and what would change if multiple teams needed separate queues.
