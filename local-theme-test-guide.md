# Local Theme Testing Guide

## 🎯 Quick Start

Your local Directus installation is now ready to test the custom coral and navy blue theme!

### 📁 Files Added to `directus-app/`:
- ✅ `env-local` - Environment variables with theme configuration
- ✅ `custom-theme.css` - Complete theme CSS
- ✅ `favicon.svg` - Custom Lab logo favicon
- ✅ `custom-logo.svg` - Custom Lab logo

## 🚀 Testing Steps

### Step 1: Set Up Environment Variables
```bash
cd directus-app
cp env-local .env
```

### Step 2: Start the Local Server
```bash
# Make sure you're in the directus-app directory
cd directus-app

# Start Directus
npx directus start
```

### Step 3: Access Your Themed Directus
Open your browser and go to: `http://localhost:8055`

**Login Credentials:**
- **Email**: admin@example.com
- **Password**: zxGGJmifLLTz

## 🎨 What to Test

### Visual Elements to Check:
1. **Login Page**:
   - [ ] Background should be white
   - [ ] Login button should be coral (#ff2e32)
   - [ ] Form elements should have coral focus states

2. **Dashboard**:
   - [ ] Sidebar should be navy blue (#002f54)
   - [ ] Navigation text should be white
   - [ ] Active navigation items should be coral
   - [ ] Main content area should be white

3. **Buttons**:
   - [ ] Primary buttons should be coral
   - [ ] Secondary buttons should be navy blue
   - [ ] Hover effects should work properly

4. **Logo & Branding**:
   - [ ] Custom "Lab" logo should appear in header
   - [ ] Favicon should show Lab logo in browser tab
   - [ ] Project name should be "Lab"

5. **Dark Mode** (toggle in user menu):
   - [ ] Background should be navy blue
   - [ ] Sidebar should be darker navy
   - [ ] Coral accents should remain
   - [ ] Text should be white/readable

## 🔧 Troubleshooting

### Theme Not Applying?
1. **Check CSS File**: Ensure `custom-theme.css` is in the root directory
2. **Verify Environment Variables**: Check that theme variables are set in `.env`
3. **Restart Server**: Stop and restart `npx directus start`
4. **Clear Browser Cache**: Hard refresh (Cmd+Shift+R or Ctrl+Shift+R)

### Logo Not Showing?
1. **Check SVG Files**: Ensure `favicon.svg` and `custom-logo.svg` are present
2. **Verify Paths**: Check that logo paths in `.env` are correct
3. **Test SVG**: Open SVG files directly in browser to verify they work

### Colors Not Right?
1. **Check CSS**: Open browser dev tools and verify CSS variables are loaded
2. **Verify Hex Codes**: Ensure colors are #ff2e32 (coral) and #002f54 (navy)
3. **Test Specificity**: CSS uses `!important` to override defaults

## 📱 Testing Checklist

### Desktop Testing:
- [ ] Chrome/Safari/Firefox compatibility
- [ ] Light mode functionality
- [ ] Dark mode functionality
- [ ] Responsive design on different screen sizes
- [ ] All interactive elements work
- [ ] Logo and favicon display correctly

### Mobile Testing:
- [ ] Open `http://localhost:8055` on mobile browser
- [ ] Check sidebar navigation
- [ ] Verify touch interactions
- [ ] Test form inputs and buttons

## 🎯 Expected Results

### Light Mode:
- **Background**: Clean white (#ffffff)
- **Sidebar**: Navy blue (#002f54) with white text
- **Buttons**: Coral (#ff2e32) primary, navy blue secondary
- **Logo**: "Lab" logo in header with coral and navy colors
- **Accents**: Coral for focus states, links, and active elements

### Dark Mode:
- **Background**: Navy blue (#002f54)
- **Sidebar**: Darker navy (#001a33)
- **Buttons**: Same coral and navy scheme
- **Text**: White for readability
- **Accents**: Coral maintained for consistency

## 🔄 Making Changes

### To Modify Colors:
1. Edit `custom-theme.css`
2. Change the hex color values
3. Save and refresh browser

### To Change Logo:
1. Replace `favicon.svg` and `custom-logo.svg`
2. Keep the same file names
3. Restart server and refresh browser

### To Adjust Theme:
1. Edit environment variables in `.env`
2. Restart Directus server
3. Test changes in browser

## 📊 Performance Check

### Loading Speed:
- [ ] Initial page load under 3 seconds
- [ ] CSS applies immediately
- [ ] No flash of unstyled content
- [ ] Smooth transitions and animations

### Browser Console:
- [ ] No CSS errors
- [ ] No missing file errors
- [ ] Theme variables loaded correctly

## 🎉 Success Criteria

Your local theme test is successful if:
1. ✅ Login page uses coral and navy blue colors
2. ✅ Dashboard sidebar is navy blue with white text
3. ✅ All buttons use coral/navy color scheme
4. ✅ Custom "Lab" logo appears in header
5. ✅ Favicon shows Lab logo in browser tab
6. ✅ Both light and dark modes work properly
7. ✅ All interactive elements are properly styled
8. ✅ No console errors related to theme

## 🚀 Next Steps

After successful local testing:
1. **Deploy to Render**: Use the same files for production deployment
2. **Fine-tune**: Make any necessary adjustments to colors or layout
3. **Document**: Note any customizations for future reference
4. **Backup**: Save your theme files for future use

Your custom coral and navy blue theme is now ready for local testing! 🎨 