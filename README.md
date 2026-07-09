# Vitals

Turn your Apple Health, COROS, Fitbit, or Garmin export into a calm health dashboard — resting heart rate, VO₂ max, sleep, training, body metrics, and the correlations between them.

## Privacy

Exports are parsed **client-side in your browser**. Raw Apple Health, COROS, Fitbit, and Garmin files are never uploaded or stored.

Accounts are optional. If Supabase is configured and a user signs in with Google, Vitals stores only:

- profile height and unit preference
- manual body measurements
- derived daily health summaries

## Run locally

```bash
pnpm install
cp .env.example .env
pnpm dev
```

Supabase is optional for anonymous use. To enable Google OAuth and cloud sync, set:

```bash
VITE_SUPABASE_URL=...
VITE_SUPABASE_ANON_KEY=...
```

Apply `supabase/migrations/001_accounts_body_summaries.sql` in your Supabase project and configure Google OAuth redirect URLs for local and production domains.

## Deploy

Deploy on Vercel with the Vite preset or:

- Build command: `pnpm build`
- Output directory: `dist`
- Environment variables: `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`

## How to get your Garmin export

Sign in at garmin.com/account → **Export Your Data**. Garmin emails a download link within a few days. Upload the `.zip` as-is.

---

*Wellness insights from your own data — not medical advice.*
