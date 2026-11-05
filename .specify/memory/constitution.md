# Vision AI — Project Constitution

## Purpose
Vision AI is an independent project intended to help users find a previously saved place or house profile from an image and retrieve its associated location information.

## Non-negotiable boundaries
1. **Keep projects separate.** Vision AI must remain independent from CHOCO. Do not read, modify, connect to, or reuse CHOCO code, databases, credentials, or production services.
2. **Protect production.** Do not change the deployed app, the `main` branch, or production data as part of planning or experiments.
3. **Use the lab branch.** Spec Kit experiments and approved documentation changes belong on `spec-kit-lab` unless the user explicitly approves another target.
4. **No unapproved writes.** Do not change application code, database schema, records, storage objects, authentication settings, secrets, permissions, or deployment configuration without explicit approval for that exact change.
5. **Inspect before changing.** Read the relevant files and current state first. Never guess file paths, commit identifiers, schema, or existing behavior.
6. **Preserve recoverability.** Prefer small, reviewable changes. Explain backup and rollback steps before any potentially destructive operation.
7. **Privacy and access control.** Treat house photos, GPS coordinates, names, and phone numbers as sensitive personal information. Do not expose private records publicly. Apply least-privilege access and validate authorization on the server for any future shared-data feature.
8. **Deletion workflow.** The intended customer experience is that customers may add records but cannot directly delete them; deletion requests should go through a support ticket for an authorized staff member or administrator to review. This is a product requirement to validate before implementation.
9. **Free-first.** Prefer free or low-cost options, while clearly explaining usage limits, privacy trade-offs, and possible charges.
10. **Test before release.** Keep experiments separate from production. Verify search, OCR/phone matching, GPS/map behavior, access rules, and backup/restore before proposing release.

## Working method
- Use Spec-Driven Development: clarify the problem, write a specification, define acceptance criteria, plan, then implement only after approval.
- Keep current behavior, proposed behavior, and unverified assumptions clearly separated.
- For each change, report files affected, data impact, tests performed, remaining risks, and whether production was touched.
- Ask one focused question when a decision materially affects safety or correctness.

## Current authorization
The user has approved creation of planning and guardrail documents on `spec-kit-lab` only. This does **not** authorize application-code changes, Supabase changes, deployment, or merging into `main`.
