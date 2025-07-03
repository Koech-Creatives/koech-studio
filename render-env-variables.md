# Environment Variables for Render Deployment

## Required Database Configuration
```
DB_CLIENT=pg
DB_HOST=aws-0-eu-west-2.pooler.supabase.com
DB_PORT=6543
DB_DATABASE=postgres
DB_USER=postgres.iuwpzqcacaqabbjkeltr
DB_PASSWORD=koechcreatives@2025
DB_SSL=true
DB_SSL__REJECT_UNAUTHORIZED=false
DB_SSL__CA=false
```

## Required Directus Configuration
```
KEY=0f4dc28a64c96aa15a9841e04ddfaabdc7e9e8c09418edec304a5ebd7363a2f3
SECRET=7fac701445281233f14dc4ac9c7051306422d7dce7da4de23c973a260ca206f5
PUBLIC_URL=https://your-app-name.onrender.com
HOST=0.0.0.0
PORT=10000
```

## Admin User Setup
```
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=DirectusAdmin123!
```

## Optional Production Settings
```
NODE_ENV=production
PORT=8055
CORS_ENABLED=true
CORS_ORIGIN=true
CACHE_ENABLED=true
CACHE_TTL=10m
RATE_LIMITER_ENABLED=true
```

## Security Headers (Recommended)
```
CONTENT_SECURITY_POLICY_DIRECTIVES__SCRIPT_SRC=array:'self','unsafe-eval'
CONTENT_SECURITY_POLICY_DIRECTIVES__OBJECT_SRC=array:'none'
CONTENT_SECURITY_POLICY_DIRECTIVES__FRAME_ANCESTORS=array:'self'
```

---

## For Render Web Service Configuration:

### Key-Value Format (copy these into Render's environment variables):

**Database:**
- `DB_CLIENT` = `pg`
- `DB_HOST` = `aws-0-eu-west-2.pooler.supabase.com`
- `DB_PORT` = `6543`
- `DB_DATABASE` = `postgres`
- `DB_USER` = `postgres.iuwpzqcacaqabbjkeltr`
- `DB_PASSWORD` = `koechcreatives@2025`
- `DB_SSL` = `true`
- `DB_SSL__REJECT_UNAUTHORIZED` = `false`
- `DB_SSL__CA` = `false`

**Directus Core:**
- `KEY` = `0f4dc28a64c96aa15a9841e04ddfaabdc7e9e8c09418edec304a5ebd7363a2f3`
- `SECRET` = `7fac701445281233f14dc4ac9c7051306422d7dce7da4de23c973a260ca206f5`
- `PUBLIC_URL` = `https://your-app-name.onrender.com` (replace with your actual Render URL)
- `HOST` = `0.0.0.0`
- `PORT` = `10000`

**Admin Setup:**
- `ADMIN_EMAIL` = `admin@example.com`
- `ADMIN_PASSWORD` = `DirectusAdmin123!`

**Production Settings:**
- `NODE_ENV` = `production`
- `CORS_ENABLED` = `true`
- `CORS_ORIGIN` = `true`

---

## Render Deployment Steps:

1. **Create Web Service** in Render
2. **Connect your repository** (or use the directus-app directory)
3. **Set Build Command:** `npm install && npm install directus`
4. **Set Start Command:** `npx directus start`
5. **Set Port:** `10000` (in Render's service settings)
6. **Add all environment variables** from above
7. **Deploy**

## Important Notes:

- **Replace `your-app-name`** in `PUBLIC_URL` with your actual Render service name
- **Keep the same KEY and SECRET** values for data consistency
- **Never commit these values** to your repository
- **Use Render's environment variable interface** to set these securely

## Alternative: If you prefer a package.json approach:

Create a `package.json` in your deployment directory:
```json
{
  "name": "directus-render-app",
  "version": "1.0.0",
  "dependencies": {
    "directus": "^27.0.2"
  },
  "scripts": {
    "start": "directus start",
    "build": "directus bootstrap"
  }
}
```

Then use:
- **Build Command:** `npm install`
- **Start Command:** `npm start`

---

## 🚨 **Troubleshooting Your Current Issues:**

Based on your Render logs, here are the fixes:

### 1. **SSL Certificate Issues**
Added these new environment variables:
- `DB_SSL__CA=false` - Disables CA certificate validation
- `HOST=0.0.0.0` - Binds to all interfaces for Render
- `PORT=10000` - Uses Render's expected port

### 2. **Admin Credentials from Bootstrap**
Your bootstrap created an admin user with:
- **Email:** `admin@example.com`
- **Password:** `zxGGJmifLLTz` (from your logs)

### 3. **"Tenant or user not found" Error**
This might be due to:
- Connection pooling issues - Try the direct connection (port 5432) instead
- User permissions in Supabase

### 4. **Alternative Database Settings (if issues persist):**
If you continue having connection issues, try these alternative settings:

```
DB_HOST=aws-0-eu-west-2.pooler.supabase.com
DB_PORT=5432
```

Or use the direct connection string format:
```
DATABASE_URL=postgresql://postgres.iuwpzqcacaqabbjkeltr:koechcreatives@2025@aws-0-eu-west-2.pooler.supabase.com:6543/postgres?sslmode=require
```

### 5. **Important Steps:**
1. **Update all environment variables** in Render with the new values above
2. **Redeploy** the service
3. **Monitor logs** for any remaining connection issues
4. **Access your app** at the Render URL once deployed successfully 