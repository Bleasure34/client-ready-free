---
name: project-intake
description: Turn a messy client brief (email thread, call notes, voice-memo transcript) into a structured project spec, scope boundary list, and effort estimate. Use at the start of every client engagement, before quoting.
---

# Project Intake

You convert unstructured client input into a spec the freelancer can quote from and the client
can sign off on. The output protects the freelancer from scope creep — that is the job.

## Input

The user will paste or point you at: emails, call notes, a transcript, an RFP, or "the client
basically wants X". If they give you a file path or directory, read it.

## Process

1. **Extract requirements.** List every concrete thing the client asked for, quoted or closely
   paraphrased. Tag each as `[explicit]` (they said it) or `[inferred]` (implied but unstated).
2. **Find the holes.** List every decision the brief does NOT answer that will block work:
   hosting, content responsibility, browser/device support, integrations, auth, who owns the
   domain, existing brand assets, launch date, budget signal. Phrase each as a question the
   freelancer can forward to the client verbatim.
3. **Draw the scope boundary.** Produce an explicit OUT-OF-SCOPE list. Infer the likely creep
   vectors for this project type (e.g., "logo design" on a website build, "content writing" on
   a CMS build, "ongoing updates" on anything) and exclude them by name unless the brief
   includes them.
4. **Estimate.** Break the work into tasks ≤1 day each. For each: estimate in hours,
   assumptions, risk level (L/M/H). Sum to a range (sum of estimates → sum × 1.5). Never give
   a single number.
5. **Flag red flags.** Vague payer, "simple" used more than twice, redesign-of-a-redesign,
   client supplies code of unknown origin, timeline shorter than the estimate range minimum.

## Output

Write `intake/SPEC.md` (create the directory if needed) with sections in this order:
**Project summary** (3 sentences max) · **Requirements** (tagged) · **Open questions for
client** (forwardable verbatim) · **In scope / Out of scope** · **Task breakdown & estimate
range** · **Risks & red flags** · **Suggested next step**.

Then print the open-questions section in the chat so the user can paste it into an email
immediately.

## Rules

- Never invent requirements the client didn't state or clearly imply; the spec gets signed.
- Estimates are for a competent solo developer using AI tooling, not a team.
- If the brief is too thin to estimate (under ~5 extractable requirements), say so and output
  only the open-questions list — a bad estimate is worse than none.
