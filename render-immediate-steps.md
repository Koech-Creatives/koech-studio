# 🚨 DO THIS NOW IN YOUR RENDER DASHBOARD

## Step-by-Step Fix for SSL Certificate Errors:

### 1. Go to Your Render Service
- Log into Render.com
- Click on your Directus service

### 2. Delete ALL Current Database Variables
Go to **Environment** tab and delete these if they exist:
- `DB_HOST`
- `DB_PORT` 
- `DB_DATABASE`
- `DB_USER`
- `DB_PASSWORD`
- `DB_SSL`
- `DB_SSL__REJECT_UNAUTHORIZED`
- `DB_SSL__CA`
- `DATABASE_URL`

### 3. Add These EXACT Variables:
```
DB_CLIENT=pg
DB_HOST=aws-0-eu-west-2.pooler.supabase.com
DB_PORT=6543
DB_DATABASE=postgres
DB_USER=postgres.iuwpzqcacaqabbjkeltr
DB_PASSWORD=koechcreatives@2025
DB_SSL=false
HOST=0.0.0.0
PORT=10000
KEY=0f4dc28a64c96aa15a9841e04ddfaabdc7e9e8c09418edec304a5ebd7363a2f3
SECRET=7fac701445281233f14dc4ac9c7051306422d7dce7da4de23c973a260ca206f5
PUBLIC_URL=https://your-app-name.onrender.com
NODE_ENV=production
```

### 4. Set Service Port
- In **Settings** tab
- Set **Port** to: `10000`

### 5. Deploy
Click **Manual Deploy** → **Deploy Latest Commit**

## If STILL Getting SSL Errors:

### Try Connection String Instead:
1. **Delete ALL the DB_* variables** (keep everything else)
2. **Add this single variable:**
```
DATABASE_URL=postgres://postgres.iuwpzqcacaqabbjkeltr:koechcreatives@2025@aws-0-eu-west-2.pooler.supabase.com:6543/postgres?sslmode=disable
```
3. **Redeploy**

## Expected Result:
- No more SSL certificate errors
- Directus should start and bind to port 10000
- Service should become accessible at your Render URL

## Login After Success:
- **URL:** `https://your-app-name.onrender.com`
- **Email:** `admin@example.com`
- **Password:** `zxGGJmifLLTz` 