# Directus Theme Deployment Checklist

## 📋 Quick Deployment Guide

### Colors Used:
- **Primary (Coral)**: #ff2e32
- **Secondary (Navy Blue)**: #002f54

### 📁 Files Created:
- ✅ `custom-theme.css` - Complete theme CSS
- ✅ `favicon.svg` - Custom Lab logo favicon
- ✅ `custom-logo.svg` - Custom Lab logo
- ✅ `directus-theme-config.json` - Theme configuration
- ✅ `render-env-variables-with-theme.md` - Environment variables
- ✅ `theme-customization-guide.md` - Complete guide

### 🚀 For Render Deployment:

#### Step 1: Upload Files to Render
In your `directus-render-app` directory:
- ✅ `package.json` (already exists)
- ✅ `custom-theme.css` (created)
- ✅ `favicon.svg` (created)
- ✅ `custom-logo.svg` (created)

#### Step 2: Set Environment Variables in Render Dashboard

**Database (Keep existing):**
```
DB_CLIENT=pg
DB_HOST=aws-0-eu-west-2.pooler.supabase.com
DB_PORT=6543
DB_DATABASE=postgres
DB_USER=postgres.iuwpzqcacaqabbjkeltr
DB_PASSWORD=koechcreatives@2025
DB_SSL=false
```

**Directus Core (Keep existing):**
```
KEY=your-super-secret-key-here-32-characters-long
SECRET=your-super-secret-another-32-char-key
PUBLIC_URL=https://your-app-name.onrender.com
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=your-secure-password
NODE_ENV=production
HOST=0.0.0.0
PORT=10000
```

**NEW Theme Variables (Add these):**
```
THEME_LIGHT_PRIMARY=#ff2e32
THEME_LIGHT_SECONDARY=#002f54
THEME_DARK_PRIMARY=#ff2e32
THEME_DARK_SECONDARY=#002f54
PROJECT_NAME=Lab
PROJECT_LOGO=/custom-logo.svg
PROJECT_FAVICON=/favicon.svg
CUSTOM_CSS=/custom-theme.css
THEME_DEFAULT=light
```

#### Step 3: Deploy
1. Push changes to your repository
2. Render will automatically deploy
3. Your app will now have coral and navy blue branding!

### 🎨 What the Theme Includes:

**Light Mode:**
- White background with coral accents
- Navy blue sidebar and navigation
- High contrast for readability

**Dark Mode:**
- Navy blue background
- Coral accents maintained
- Optimal for low-light use

**Interactive Elements:**
- Coral buttons and links
- Navy blue focus states
- Custom scrollbars
- Smooth animations

**Branding:**
- Custom "Lab" logo in header
- Matching favicon
- Professional appearance

### 🔧 Troubleshooting:

**Theme not applying?**
1. Check CSS file is uploaded
2. Verify environment variables are set
3. Clear browser cache
4. Check browser console for errors

**Logo not showing?**
1. Ensure SVG files are uploaded
2. Check file paths in environment variables
3. Test with different browsers

### 📱 Testing Checklist:

After deployment, verify:
- [ ] Login page uses coral and navy blue colors
- [ ] Dashboard sidebar is navy blue
- [ ] Buttons and links are coral
- [ ] Logo appears in header
- [ ] Favicon shows in browser tab
- [ ] Both light and dark modes work
- [ ] Mobile responsive design works
- [ ] All interactive elements styled correctly

### 🎯 Admin Credentials:
- **Email**: admin@example.com
- **Password**: zxGGJmifLLTz

### 📞 Support:
If you encounter any issues:
1. Check the `theme-customization-guide.md` for detailed troubleshooting
2. Review browser developer tools for CSS errors
3. Verify all files are uploaded correctly
4. Test with a clean browser session

**Your Directus instance is now ready with custom coral and navy blue branding! 🎉** 