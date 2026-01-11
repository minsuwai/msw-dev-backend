# my-backend — Setup and deployment notes

This file documents how to run and deploy the Strapi backend used by the portfolio.

## Quick start

Install dependencies and run locally:

```bash
npm install
npm run develop
# or: yarn install && yarn develop
```

Build (admin) and start in a production-like mode:

```bash
npm run build
npm run start
```

## Environment variables

Do not commit your `.env` file. Keep a `.env.example` that documents required variables and add real values to `.env` locally and in your host/CI.

Common variables (check `config/*` for exact names):

- `DATABASE_URL` (or `DB_HOST`, `DB_PORT`, `DB_USER`, `DB_PASSWORD`, `DB_NAME`)
- `APP_KEYS`
- `API_TOKEN_SALT`
- `ADMIN_JWT_SECRET`
- `JWT_SECRET`
- `PORT`
- `NODE_ENV`

## Uploads

Uploaded files are stored in `public/uploads/` by default. Do not commit upload files; keep `uploads/` in `.gitignore`.

## Production recommendations

- Use a managed Postgres DB for production.
- Configure env vars in your host provider's secrets manager (Render, Railway, DigitalOcean, etc.).
- Consider object storage (S3/GCS) for persistent uploads and backups.

## If secrets were committed

If you accidentally committed `.env` or other secrets, remove them from history and rotate credentials. Recommended tools: `git-filter-repo` or BFG Repo-Cleaner.

---

If you want, I can also append these notes into `README.md` or create a `.env.example` with the required variable names — tell me which you prefer.
