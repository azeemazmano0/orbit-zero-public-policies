# Orbit Zero Phase C closure and deletion acceptance

**11 November 2026 | Status: pending actual verification**

This document is an internal operator checklist. It does not constitute evidence that deletion or public policy publication has occurred.

## Operating scope and protections
- Staging only: Supabase project `kdpbgnkxmqtwntapilen`.
- Production `vojynrctvkczuvmagonj` is explicitly out of scope.
- Do **not** delete established tester Accounts A, B, C or D. Account D's earlier email ownership challenge remains frozen.
- Do not publish app links, merge the public policy PR, or declare a PASS until the below evidence exists.
- Do not store plaintext access tokens, passwords, refresh tokens, arbitrary profile/email details or identity-document scans in evidence.

## Account ownership verification
1. The owner initiates a deletion request by emailing `orbitzero.askme@gmail.com` from a disposable staging user's registered email, ideally by using the website link.
2. Operator verifies that the support inbox actually received the request. A `mailto:` link is not proof of delivery.
3. Operator locates the **specific** test account by registered email via Supabase **Authentication > Users**. Record UID in a restricted test evidence store, not GitHub.
4. Use a new confirmation reply to the registered address and verify matching acknowledgement before deleting. If proof of control cannot be established, STOP.
5. Explicitly confirm the user is not A/B/C/D and is in the staging project, not production.

## Pre-deletion acceptance
1. Create a dedicated, confirmed staging account through the app's regular Auth flow.
2. Generate actual user-owned records: profile, Passport account and stamps, and if safe a staging adventure/visit. Document which records were available.
3. Confirm which storage buckets, if any, hold account-owned objects. Remove those objects using authorized Storage APIs before Auth deletion. Do not delete shared catalogue photographs.
4. Capture a short-lived existing access token only in a secure test session, never in a report; record its intended expiry.
5. Record aggregate baseline counts for user-owned records in Auth, profiles, Passport accounts/stamps, adventures, verified visits, beta participants, achievement epochs and private GPS challenges.

## Delete and verify
1. With explicit user confirmation, delete this disposable staging Auth user using the Supabase admin Auth interface, **not** raw SQL against `auth.users`.
2. Observe success/failure directly. If deletion fails due to Storage ownership or FK/trigger restrictions, STOP and document the exact failure without forcing a bypass.
3. Independently verify Auth user absent, all account-owned rows absent, any owned Storage objects absent, and other testers' counts unchanged.
4. Confirm that sign-in with the deleted account fails, refresh of its old session fails, and test at least one protected API using a previously issued unexpired access token. Record response and expiry behavior; **do not** promise all access tokens are revoked immediately.
5. Record operator actions, timestamps, whether backups/logs/support messages remain, and any cleanup exceptions. Notify the verified owner only when all required checks pass.

## Retention/disposal approval
- **Active account data:** delete following verified request via admin Auth removal and dependent cleanup.
- **Support correspondence target:** 90 days after case closure, unless exceptional documented retention is necessary. Must have an operator-owned repeatable deletion workflow.
- **Temporary recovery exports target:** 30 days from creation or sooner if no longer required. Inventory all local and cloud copies; delete or securely dispose, recording proof.
- **Provider logs/backups:** record *actual* Supabase plan and backup configuration. Do not equate dashboard log-history availability with guaranteed deletion from all provider systems.
- **Auth audit records:** inspect database logging configuration and verify treatment, rather than assuming Auth deletion cleans audit history.
- **Restoration:** record deleted UID in an access-restricted deletion register sufficient to prevent reactivation through restored snapshots; purge only after the agreed recovery window and any lawful obligations.
- **Public text:** confirm that promises mirror implemented operational measures and do not assert unsupported deletion deadlines.

## Website and in-app release acceptance
1. Review final public policy pages with legal operator name and current data practices; verify access to the deletion-request mailbox.
2. Merge reviewed GitHub PR to `main` and enable GitHub Pages with source **Deploy from a branch**, branch **main**, folder **/docs**, then force HTTPS if the UI supports the option.
3. Verify unauthenticated URLs (after Pages deployment):
   - `https://azeemazmano0.github.io/orbit-zero-public-policies/`
   - `https://azeemazmano0.github.io/orbit-zero-public-policies/delete-account/`
   - `https://azeemazmano0.github.io/orbit-zero-public-policies/support/`
4. Open all three pages on mobile, check page navigation and actual email reception; do not infer delivery from `mailto:`.
5. Update Flutter in-app privacy, support, and Delete Account links and verify using a built app on a real device.
6. Record Google Play Console policy/deletion URL settings and final release checks with evidence.

**GO decision:** only after a successful disposable-account deletion test, confirmed retention controls, live unauthenticated HTTPS pages, functional mailbox and in-app links. Do not change the original 13/20 tracker until mapping to its exact acceptance criteria is reconciled.
