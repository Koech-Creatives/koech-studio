# 🚨 IMMEDIATE FIX for Render Deployment

## Add These Environment Variables to Fix Current Issues:

```
DB_SSL__CA=false
HOST=0.0.0.0
PORT=10000
```

## Your Admin Login Credentials:
- **Email:** `admin@example.com`
- **Password:** `zxGGJmifLLTz`

## Steps to Fix:
1. Go to your Render service settings
2. Add the 3 environment variables above
3. Set service port to `10000` 
4. Redeploy

## If "Tenant or user not found" persists:
Change these variables:
```
DB_PORT=5432
```
OR add:
```
DATABASE_URL=postgresql://postgres.iuwpzqcacaqabbjkeltr:koechcreatives@2025@aws-0-eu-west-2.pooler.supabase.com:6543/postgres?sslmode=require
```

The SSL certificate and port binding issues should be resolved with the first 3 variables! 