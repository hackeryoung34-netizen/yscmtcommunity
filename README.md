# YSCMT Community

Migration of YSCMT Community from Hatchable to a Vercel-hosted frontend with Supabase Auth and PostgreSQL.

## Included
- Responsive community website
- Email one-time-link authentication through Supabase
- Student, teacher and mentor profiles
- Public member directory
- Authenticated community discussions
- PostgreSQL schema with row-level security policies

## Setup
1. Create a Supabase project.
2. Open the Supabase SQL Editor and run `supabase/schema.sql`.
3. Copy the Project URL and anon/public key from Supabase Project Settings → API.
4. Put those values in `config.js` as `url` and `anonKey`.
5. In Supabase Authentication → URL Configuration, set the Site URL to the production domain and add the Vercel preview and production URLs to Redirect URLs.
6. Deploy this repository to Vercel.
7. Add `community.yscmtenterprise.ng` to the Vercel project and configure its DNS record in Cloudflare when Vercel provides the target.

## Migration notes
- Never publish personal member data, passwords, API secrets or service-role keys.
- Hatchable-managed passwords and sessions cannot be copied into Supabase. Existing members will need to sign in again using email.
- Export profile and post data from Hatchable through a protected, private backup and import it only after the Supabase schema is ready.
- Keep the Hatchable project active until the new domain, authentication, data and discussions have been tested.
