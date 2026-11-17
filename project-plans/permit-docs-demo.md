# PermitDocs Demo

**Status** — Planned public demonstration.

**Problem** — Repeatedly copying the same case details into documents adds manual work and can introduce inconsistencies.

## Minimum implementation

- Use Python, FastAPI, and Jinja. A simple HTML form or FastAPI's interactive API documentation is enough for the first demo.
- Accept one synthetic permit record as JSON. Example fields include `case_id`, `applicant_name`, `permit_type`, and `submitted_on`.
- Use `POST /documents/preview` to render one fictional acknowledgment letter from a fixed template. Return the preview so it can be read in a browser.
- Require the fields needed by the template. Return a readable validation error for a missing field or invalid date.
- Keep records in memory for the first version. Add a download button in a later version if it improves the demo.

## Completion criteria

- A reviewer can run the project using the README and generate a preview from a checked-in synthetic fixture.
- An automated test verifies that the preview contains the expected case number and permit type.
- A second test verifies that an incomplete request receives a validation error.
- A short recording shows the record, the generated letter, and the validation response.
- The README identifies the fictional dataset and explains how the demo relates to the [municipal case study](../case-studies/urban-licensing.md).

## Interview walkthrough

Explain where field validation happens, why the template is kept separate from the input, and how a second template could be added.
