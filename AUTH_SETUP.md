# Authentication rollout

This branch is reserved for the Supabase authentication integration. Do not merge until login, invitations, RLS, and existing browser-data preservation are tested.

The production site remains on main. Existing garden records are stored in browser localStorage under henrys-garden-v1; do not clear or overwrite this key during migration.

Supabase project: rusipqvmxqehcztaszuv.

Outstanding: verify owner invitation, grant owner admin role, implement secure sign-in, validate per-user garden isolation, and migrate local records with explicit backup and confirmation.
