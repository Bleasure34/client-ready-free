---
name: pre-delivery-qa
description: Run a systematic pre-handoff QA sweep on a web project and produce a pass/fail checklist with fixes applied or filed. Use before every client delivery, demo, or launch.
---

# Pre-Delivery QA Sweep

The last hour before handoff finds the embarrassing bugs. You run that hour systematically.
Outcome: either everything passes, or the user gets an exact list of what fails and why.

## Process

Work through the checklist below. For each item: **verify it against the actual code/config**
(don't assume), mark `PASS` / `FAIL` / `N/A`, and for failures either fix immediately (if
under ~10 lines and unambiguous) or file it in the report with the fix described.

### 1. Placeholder & debris scan
- Grep for: `lorem ipsum`, `TODO`, `FIXME`, `XXX`, `console.log`, `print(`, `dd(`, `var_dump`,
  `debugger`, placeholder images, `example.com`, `test@`, `your-name-here`, `changeme`.
- Check visible page copy for template leftovers ("Your Company", default hero text).

### 2. Broken-state checks
- Every internal link/route resolves. Every form has a success AND failure state.
- 404 page exists and is styled. Error pages don't leak stack traces in production config.
- Empty states: what renders when there's no data yet? (New client sites always start empty.)

### 3. Configuration for production
- Debug mode off in prod config. Source maps decision is deliberate. `.env.example` matches
  every env var the code actually reads (grep for the env-access pattern of the framework).
- Analytics/tracking installed if speced. Favicon, page titles, meta descriptions set —
  no "React App" or "Document" titles.

### 4. The money paths
- Contact/checkout/signup flows traced end-to-end in code: form → handler → persistence/email.
  Confirm the email "to" address is the client's, not the developer's test address.
- Payment keys: live vs. test keys are env-switched, never hardcoded.

### 5. Cross-cutting
- Responsive: check for fixed pixel widths in layout containers, missing viewport meta.
- Accessibility minimum: images have alt attributes, form inputs have labels, color isn't the
  only state indicator, focus states not suppressed (`outline: none` without replacement).
- HTTPS assumptions: no hardcoded `http://` resource URLs (mixed content).

### 6. Run what exists
- If there's a test suite, run it. If there's a linter/build, run it. A build that fails on a
  clean checkout is an automatic handoff blocker.

## Output

`qa/QA-REPORT.md`: summary verdict (**SHIP** / **SHIP WITH NOTES** / **DO NOT SHIP**),
the full checklist with statuses, fixes applied (with file references), and remaining failures
with concrete fix descriptions and effort estimates. Print the verdict and any failures in chat.

## Rules

- Never mark PASS on inspection you didn't do. An honest N/A beats a guessed PASS.
- Fixes you apply during the sweep must be minimal and behavior-preserving — this is QA,
  not refactoring. Anything bigger gets filed, not done.
