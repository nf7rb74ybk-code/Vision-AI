# Vision AI — Project Brief

## 1. Product direction
Vision AI is a standalone website, separate from CHOCO. Its core purpose is to help a user locate a saved house/place profile by supplying a photo and then show the matching saved image and GPS/map location.

## 2. Known project context
- GitHub repository: `nf7rb74ybk-code/Vision-AI`
- Existing app entry file: `index.html`
- Default branch: `main`
- Experimental documentation branch: `spec-kit-lab`
- A separate Supabase project named `vision-AI` has been created previously. No database or storage changes are authorized by this brief.
- Earlier manual checks were reported as passing for adding a sample house profile, saving GPS coordinates, image search, opening a map, and downloading a JSON backup.
- Earlier follow-up checks for phone-number search and OCR were also reported as passing.
- The existing app has used browser-local storage. Its current implementation and data model must be inspected before relying on assumptions about persistence or multi-user behavior.

## 3. Product capabilities and requirements to validate
### Core lookup
- Save a place/house profile with an image and its GPS coordinates.
- Search using an image selected from the iPhone photo library or another supported input.
- Show the matching saved image/profile and its GPS location, with a map link or map view.
- Support manual phone-number lookup as a fallback where that field exists.
- Where OCR is used, extract a phone number from the submitted image and use it only as a search key; show a profile only when the match is sufficiently reliable and authorized.

### Accounts and record permissions (planned)
- Support customer accounts and appropriate staff/administrator roles.
- Customers may add records but should not have direct delete permission.
- A customer who wants a record deleted submits a support ticket; an authorized staff member or administrator reviews and performs the deletion.
- Define who can view each record before implementing shared or multi-user access. A successful phone/image match must never bypass authorization.

### Data safety
- Provide a way to export and restore a backup.
- Assess private image storage, GPS privacy, retention, and account access before moving data to cloud storage.
- Do not put private photos, phone numbers, GPS coordinates, API keys, or service-role secrets in public repository files.

## 4. Non-goals for this documentation phase
- No changes to `index.html` or other application code.
- No Supabase schema, Auth, Storage, policy, or record changes.
- No deployment or change to the live website.
- No CHOCO integration or modification.
- No merge or push to `main`.

## 5. Open design questions
1. Is each saved house profile private to its creator, shared with an approved team, or visible to all authenticated users?
2. Which fields are required for a profile, and which are optional?
3. How should duplicate phone numbers or multiple possible image matches be handled?
4. What confidence threshold and confirmation step should OCR use?
5. Which staff roles can review tickets and delete records, and how should that action be audited?
6. Should GPS be shown as exact coordinates, a map pin, or a less precise location depending on the viewer's permission?

These questions must be resolved in a feature specification before implementation.

## 6. Acceptance principles
A feature is not ready merely because its screen works. Acceptance must include authorization tests, privacy checks, error handling, backup/restore considerations, and iPhone usability checks.
