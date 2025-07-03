# Render Environment Variables - Complete Setup with Custom Theme

## Required Environment Variables

### Database Configuration
```
DB_CLIENT=pg
DB_HOST=aws-0-eu-west-2.pooler.supabase.com
DB_PORT=6543
DB_DATABASE=postgres
DB_USER=postgres.iuwpzqcacaqabbjkeltr
DB_PASSWORD=koechcreatives@2025
DB_SSL=false
```

### Directus Core Configuration
```
KEY=your-super-secret-key-here-32-characters-long
SECRET=your-super-secret-another-32-char-key
PUBLIC_URL=https://your-app-name.onrender.com
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=your-secure-password
NODE_ENV=production
```

### Server Configuration
```
HOST=0.0.0.0
PORT=10000
```

### CORS Configuration
```
CORS_ENABLED=true
CORS_ORIGIN=true
CORS_METHODS=GET,POST,PATCH,DELETE,PUT
CORS_ALLOWED_HEADERS=Content-Type,Authorization
```

### Custom Theme Configuration
```
THEME_LIGHT_PRIMARY=#ff2e32
THEME_LIGHT_SECONDARY=#002f54
THEME_DARK_PRIMARY=#ff2e32
THEME_DARK_SECONDARY=#002f54
THEME_LIGHT_BACKGROUND=#ffffff
THEME_DARK_BACKGROUND=#002f54
```

### Logo and Branding
```
PROJECT_NAME=Lab
PROJECT_LOGO=/custom-logo.svg
PROJECT_FAVICON=/favicon.svg
```

### Additional Customization
```
CUSTOM_CSS=/custom-theme.css
THEME_DEFAULT=light
THEME_LIGHT_FOREGROUND=#002f54
THEME_LIGHT_FOREGROUND_ACCENT=#ff2e32
THEME_DARK_FOREGROUND=#ffffff
THEME_DARK_FOREGROUND_ACCENT=#ff2e32
```

## File Structure for Deployment

Your `directus-render-app` directory should contain:

1. `package.json` (already created)
2. `custom-theme.css` (created above)
3. `favicon.svg` (created above)
4. `custom-logo.svg` (same as favicon.svg)

## Deployment Steps

1. **Upload Files to Render**:
   - Upload the `custom-theme.css` file to your Render app
   - Upload the `favicon.svg` file to your Render app
   - Make sure these files are in the root directory of your deployment

2. **Set Environment Variables**:
   - Copy all the environment variables above
   - Set them in your Render dashboard under "Environment"

3. **Deploy**:
   - Deploy your app with the new configuration
   - The custom theme will be applied automatically

## Color Scheme

- **Primary (Coral)**: #ff2e32
- **Secondary (Navy Blue)**: #002f54
- **Background Light**: #ffffff
- **Background Dark**: #002f54
- **Accent Colors**: Various shades of coral and navy blue

## Notes

- The custom CSS file overrides Directus default theme
- Both light and dark mode are supported
- The logo will be displayed in the navigation
- All primary buttons and accents use the coral color
- Sidebar and navigation use the navy blue color 