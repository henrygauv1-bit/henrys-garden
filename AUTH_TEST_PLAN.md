# Henry's Garden authentication acceptance tests

Status: staging only; not yet deployed or end-to-end tested.

1. Supabase Authentication > URL Configuration: Site URL must use the GitHub Pages origin/path, and redirect allow list must include `https://henrygauv1-bit.github.io/henrys-garden/auth.html`.
2. Verify invitation-only setting remains disabled for public signup. Confirm email provider settings: minimum 12 characters and complexity policy. Leaked-password checks require a paid plan and remain off.
3. Invite the existing administrator account to the activation redirect URL, if eligible; avoid duplicate accounts. If the existing account cannot be reinvited, use the provider's supported recovery/password setup path.
4. Confirm email redirects to `auth.html` rather than localhost, a valid invitation establishes a session, and password update succeeds. Confirm expired/reused tokens do not create access.
5. Sign in via `login.html`; sign out; verify an unauthenticated visitor cannot read `gardens` or `garden_entries`.
6. Create a separate test invitee account. Verify that it cannot see the admin's garden or any other owner's records, and cannot update their rows.
7. Verify the admin can read all gardens but cannot alter another user's entries unless separately authorized. Check admin status through `public.admins`.
8. Before any cloud migration, export the existing localStorage `henrys-garden-v1` backup. Upload only on explicit confirmation; never overwrite local browser records on login.
9. After tests pass, publish only authentication pages initially; preserve the live `index.html` until cloud data integration is proven.

Do not call this complete until live email, browser sign-in, and two-account row-level-security tests have passed.
