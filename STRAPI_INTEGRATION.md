# Strapi Local Integration (`doomsday-core-service` ↔ `home-utilities`)

This Strapi v5 service (`http://localhost:1337`) provides the backend Content-Types consumed by `D:\Kien Nguyen\The Ark\home-utilities\doomsday-api.js`.

## Scaffolded Content-Types (`src/api/`)

| Content-Type | UID | Collection | Endpoint | Schema |
| :--- | :--- | :--- | :--- | :--- |
| **Hero** | `api::hero.hero` | `heroes` | `/api/heroes` | `src/api/hero/content-types/hero/schema.json` |
| **Biobeast** | `api::biobeast.biobeast` | `biobeasts` | `/api/biobeasts` | `src/api/biobeast/content-types/biobeast/schema.json` |
| **Squad Combo** | `api::squad-combo.squad-combo` | `squad_combos` | `/api/squad-combos` | `src/api/squad-combo/content-types/squad-combo/schema.json` |
| **Troop Tier** | `api::troop-tier.troop-tier` | `troop_tiers` | `/api/troop-tiers` | `src/api/troop-tier/content-types/troop-tier/schema.json` |

## Local Setup Checklist

1. **Start Strapi** (uses SQLite at `.tmp/data.db` via `.env`, no Docker required):
   ```powershell
   npm run develop
   ```
2. **Create Admin & Publish Data:**
   Open `http://localhost:1337/admin`, create your local admin user, and publish entries under **Hero**, **Biobeast**, **Squad Combo**, and **Troop Tier**.
3. **Allow Read Access for `home-utilities`:**
   - Either enable `find` and `findOne` under **Settings → Users & Permissions plugin → Roles → Public**, or create a **Read-only API Token** under **Settings → Global Settings → API Tokens**.
4. **Start Frontend (`home-utilities`):**
   ```powershell
   powershell -ExecutionPolicy Bypass -File "D:\Kien Nguyen\The Ark\home-utilities\start-localhost.ps1"
   ```

See `D:\Kien Nguyen\The Ark\home-utilities\STRAPI_INTEGRATION.md` for full client API usage (`window.DLS_API`), query parameters, and offline fallback details.
