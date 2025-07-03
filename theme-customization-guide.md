# Directus Theme Customization Guide

## Overview

This guide explains how to customize your Directus instance with:
- **Primary Color**: Coral (#ff2e32)
- **Secondary Color**: Navy Blue (#002f54)  
- **Custom Logo**: Lab logo with coral and navy blue branding
- **Custom Favicon**: Matching brand favicon

## Files Created

### 1. Theme Files
- `custom-theme.css` - Complete CSS overrides for Directus theme
- `directus-theme-config.json` - Theme configuration file
- `favicon.svg` - Custom favicon with Lab logo
- `custom-logo.svg` - Custom logo for app header

### 2. Documentation Files
- `render-env-variables-with-theme.md` - Complete environment variables
- `theme-customization-guide.md` - This guide

## Color Scheme

### Primary Colors
- **Coral**: #ff2e32 (buttons, links, accents)
- **Navy Blue**: #002f54 (sidebar, navigation, backgrounds)

### Supporting Colors
- **Light Background**: #ffffff
- **Dark Background**: #002f54
- **Light Accents**: #f8f9fa
- **Dark Accents**: #003366

## Implementation Options

### Option 1: Environment Variables (Recommended)
Add these to your Render environment variables:

```bash
# Theme Colors
THEME_LIGHT_PRIMARY=#ff2e32
THEME_LIGHT_SECONDARY=#002f54
THEME_DARK_PRIMARY=#ff2e32
THEME_DARK_SECONDARY=#002f54

# Logo and Branding
PROJECT_NAME=Lab
PROJECT_LOGO=/custom-logo.svg
PROJECT_FAVICON=/favicon.svg

# Custom CSS
CUSTOM_CSS=/custom-theme.css
```

### Option 2: Custom CSS Injection
The `custom-theme.css` file contains comprehensive CSS overrides that will:
- Change primary colors to coral
- Change secondary colors to navy blue
- Style sidebar and navigation
- Customize buttons and form elements
- Apply theme to both light and dark modes

### Option 3: Directus Extensions
For advanced customization, you can create a Directus extension that loads the theme.

## Deployment Steps

### For Render Deployment:

1. **Upload Files**:
   - Copy `custom-theme.css` to your app root
   - Copy `favicon.svg` to your app root
   - Copy `custom-logo.svg` to your app root

2. **Set Environment Variables**:
   ```bash
   # Database (existing)
   DB_CLIENT=pg
   DB_HOST=aws-0-eu-west-2.pooler.supabase.com
   DB_PORT=6543
   DB_DATABASE=postgres
   DB_USER=postgres.iuwpzqcacaqabbjkeltr
   DB_PASSWORD=koechcreatives@2025
   DB_SSL=false
   
   # Directus Core (existing)
   KEY=your-super-secret-key-here-32-characters-long
   SECRET=your-super-secret-another-32-char-key
   PUBLIC_URL=https://your-app-name.onrender.com
   ADMIN_EMAIL=admin@example.com
   ADMIN_PASSWORD=your-secure-password
   NODE_ENV=production
   HOST=0.0.0.0
   PORT=10000
   
   # New Theme Variables
   THEME_LIGHT_PRIMARY=#ff2e32
   THEME_LIGHT_SECONDARY=#002f54
   THEME_DARK_PRIMARY=#ff2e32
   THEME_DARK_SECONDARY=#002f54
   PROJECT_NAME=Lab
   PROJECT_LOGO=/custom-logo.svg
   PROJECT_FAVICON=/favicon.svg
   CUSTOM_CSS=/custom-theme.css
   ```

3. **Deploy**: 
   - Push changes to your repository
   - Render will automatically deploy with the new theme

### For Local Development:

1. **Copy Files**: Copy all theme files to your local Directus installation
2. **Add to .env**: Add the theme environment variables to your `.env` file
3. **Restart Server**: Restart your Directus server to apply changes

## Theme Features

### Light Mode
- Clean white background
- Coral accents and buttons
- Navy blue sidebar and navigation
- High contrast for readability

### Dark Mode
- Navy blue background
- Coral accents maintained
- Darker navy variations for depth
- Optimized for low-light environments

### Interactive Elements
- Coral hover states for buttons
- Navy blue focus states
- Custom scrollbars with coral thumb
- Animated loading indicators

### Branding
- Custom "Lab" logo in header
- Coral and navy blue favicon
- Consistent color scheme throughout
- Professional business appearance

## Troubleshooting

### Theme Not Applying
1. Check that CSS file is being served correctly
2. Verify environment variables are set
3. Clear browser cache
4. Check browser developer tools for CSS errors

### Logo Not Showing
1. Ensure SVG files are uploaded correctly
2. Check file paths in environment variables
3. Verify SVG syntax is valid
4. Test with different file formats if needed

### Colors Not Matching
1. Verify hex color codes are correct
2. Check CSS specificity (use !important if needed)
3. Test in different browsers
4. Validate CSS syntax

## Advanced Customization

### Adding More Colors
Edit `custom-theme.css` to add additional color variations:

```css
:root {
  --theme--tertiary: #your-color-here !important;
  --theme--quaternary: #your-color-here !important;
}
```

### Custom Animations
Add CSS animations for enhanced user experience:

```css
.v-button {
  transition: all 0.3s ease !important;
}

.v-button:hover {
  transform: translateY(-2px) !important;
}
```

### Responsive Design
Ensure theme works on mobile devices:

```css
@media (max-width: 768px) {
  .theme--sidebar--background {
    /* Mobile-specific styles */
  }
}
```

## Support

If you encounter issues:
1. Check the browser console for errors
2. Verify all files are uploaded correctly
3. Test with a clean browser session
4. Review Directus documentation for theme customization

## Next Steps

After applying the theme:
1. Test both light and dark modes
2. Verify logo appears correctly
3. Check all interactive elements
4. Test on different devices/browsers
5. Consider additional branding elements

The theme is now ready for production use with your coral and navy blue branding! 