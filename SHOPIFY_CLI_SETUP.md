# Shopify CLI Theme Upload Guide

This guide walks you through setting up and using the Shopify CLI to upload and manage this theme store.

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- A Shopify store account

## Installation

### 1. Install Shopify CLI and Theme Tools

```bash
npm install -g @shopify/cli @shopify/theme
```

Or use the npm script:
```bash
npm run shopify:install
```

Verify installation:
```bash
shopify version
```

### 2. Authenticate with Shopify

Log in to your Shopify store:
```bash
npm run shopify:login
```

Or directly:
```bash
shopify auth login
```

This will open a browser window where you can authenticate. Select your store when prompted.

## Development Workflow

### Local Development with Live Preview

To start the local development server and sync changes in real-time:

```bash
npm run shopify:dev
```

Or with a specific store:
```bash
npm run shopify:dev -- --store your-store.myshopify.com
```

This will:
- Start a local server on `http://localhost:9292`
- Sync theme files to your development theme in Shopify
- Show live updates as you edit Liquid, CSS, and JavaScript files

### Push Theme to Store

To upload your theme to a specific theme in your store:

```bash
npm run shopify:push -- --store your-store.myshopify.com --theme "Your Theme Name"
```

### Deploy to Live (Production)

To push your theme to the live theme (be careful!):

```bash
npm run shopify:push -- --store your-store.myshopify.com --theme "Your Theme Name" --allow-live
```

## Common Commands

```bash
# List all themes in your store
npm run shopify:list -- --store your-store.myshopify.com

# Pull theme files from Shopify (download)
npm run shopify:pull -- --store your-store.myshopify.com --theme "Your Theme Name"

# Delete a theme
shopify theme delete --store your-store.myshopify.com --theme "Your Theme Name"

# Check theme configuration
shopify theme info --store your-store.myshopify.com --theme "Your Theme Name"
```

## Quick Start Checklist

1. Run `npm run shopify:login` to authenticate
2. Run `npm run shopify:dev -- --store your-store.myshopify.com` to start local development
3. Make your changes to Liquid, CSS, and JavaScript files
4. Run `npm run shopify:push -- --store your-store.myshopify.com --theme "Your Theme Name"` to upload
5. Verify changes in Shopify Admin > Online Store > Themes

## Verification Checklist

After uploading, verify your theme:

- [ ] Theme appears in Shopify Admin > Online Store > Themes
- [ ] All Liquid templates render correctly
- [ ] CSS and styling loads properly
- [ ] JavaScript functionality works as expected
- [ ] No console errors in browser dev tools
- [ ] Mobile responsive design looks good

## Troubleshooting

### Authentication Issues
If you're having trouble logging in:
```bash
shopify auth logout
npm run shopify:login
```

### Theme Won't Upload
- Ensure your Shopify store URL is correct (e.g., `mystore.myshopify.com`)
- Verify you have permissions to edit themes
- Check for syntax errors in Liquid files

### Live Preview Not Working
- Ensure you're using the correct store URL
- Clear browser cache if changes don't appear
- Restart the dev server if needed

## Additional Resources

- [Shopify CLI Documentation](https://shopify.dev/docs/themes/tools/cli)
- [Theme Development Guide](https://shopify.dev/docs/themes)
- [Liquid Reference](https://shopify.dev/api/liquid)
