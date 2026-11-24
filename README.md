# Woldra - App Legal Docs

A multi-app static site for hosting Privacy Policies and Terms of Service across all Woldra applications, designed for GitHub Pages.

## URL Structure

```
apps.woldra.com/              -> Developer landing page
apps.woldra.com/catris/privacyPolicy
apps.woldra.com/catris/termsOfService
apps.woldra.com/stepets/privacyPolicy
apps.woldra.com/stepets/termsOfService
```

## Project Structure

```
.
├── index.html                  # Developer landing page (Woldra)
├── assets/
│   └── css/
│       └── base.css            # Shared base styles
└── apps/
    ├── catris/
    │   ├── theme.css           # Catris-specific theming
    │   ├── privacyPolicy/
    │   │   └── index.html
    │   └── termsOfService/
    │       └── index.html
    └── stepets/
        ├── theme.css           # Stepets-specific theming
        ├── privacyPolicy/
        │   └── index.html
        └── termsOfService/
            └── index.html
```

## Adding a New App

1. Create a new folder under `apps/` with the app name:
   ```
   mkdir apps/newapp
   ```

2. Copy the theme file and customize:
   ```
   cp apps/catris/theme.css apps/newapp/theme.css
   ```

3. Edit `apps/newapp/theme.css` and change the CSS variables:
   ```css
   :root {
     --accent: #ff6b6b;          /* Your brand color */
     --bg-secondary: #fff5f5;    /* Your background tint */
     --font-body: 'Your Font';   /* Your typography */
   }
   ```

4. Create the page directories and copy templates:
   ```
   mkdir -p apps/newapp/privacyPolicy
   mkdir -p apps/newapp/termsOfService
   cp apps/catris/privacyPolicy/index.html apps/newapp/privacyPolicy/
   cp apps/catris/termsOfService/index.html apps/newapp/termsOfService/
   ```

5. Update the HTML files in `apps/newapp/` to:
   - Change the page title
   - Update the document content
   - Update the nav links

6. Add the app card to `index.html` in the `apps-grid` section.

## Customizing an Existing App's Theme

Edit the `theme.css` file for any app. The CSS custom properties control everything:

| Variable | Purpose |
|----------|---------|
| `--accent` | Primary brand color |
| `--accent-hover` | Hover state color |
| `--bg-primary` | Page background |
| `--bg-secondary` | Header/footer background |
| `--text-primary` | Main text color |
| `--text-secondary` | Muted text color |
| `--font-body` | Body font family |
| `--font-heading` | Heading font family |
| `--border` | Border color |
| `--accent-gradient` | Optional gradient for decorative elements |

## GitHub Pages Setup

1. Create a new GitHub repository (e.g., `woldra/apps`)
2. Push the code:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/apps.git
   git push -u origin main
   ```
3. Go to **Settings > Pages** in your repo
4. Set **Source** to `main` branch, `/ (root)` folder
5. Add a custom domain: `apps.woldra.com`
6. Configure your DNS:
   - Add a CNAME record: `apps` → `YOUR_USERNAME.github.io`
   - Or use GitHub's recommended DNS configuration

## Notes

- Each app's `theme.css` is completely independent
- The base styles handle layout, typography, and responsiveness
- Pages are pure static HTML - no JavaScript required
- All legal content is placeholder text - update with your actual policies
- Consider consulting a legal professional for your actual Terms of Service
