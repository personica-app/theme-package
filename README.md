# Revelica Theme Package

A common theme package that can be used by multiple apps. This serves as the source of truth for Revelica's theme and colors.

# Updating

To update the theme, edit the theme.css file and then merge to this repository.

# Installation

To install the theme package, run:

```sh
pnpm add https://github.com/personica-app/theme-package.git
```

Then, import the theme in your styles:

```css
@import "revelica-themes/theme.css";
```

# Local Development

If you're working on the theme package locally and want to test changes in another local app, follow this workflow to avoid constantly publishing and updating the package.

# Using `npm link` (Recommended for Local Development)

`npm link` allows you to create a symbolic link between your local theme package and your Next.js app, enabling real-time testing of changes.

## Steps:

### 1. Link the Theme Package

**In your theme repository:**

```sh
cd /theme-package
npm link
```

This creates a global symbolic link to your theme package.

**In your Next.js app repository:**

```sh
cd /path/to/your/nextjs-app
npm link revelica-themes
```

This links the theme package to your app’s `node_modules` folder.

### 2. Make Changes and Test

Once linked, any changes made in your local theme repository (e.g., `theme.css`) will immediately reflect in your Next.js app. If your app is running in development mode, it should automatically reload with the new styles.

### 3. Unlink When Done

When you're finished testing and want to revert to the installed version of the theme package:

**In your Next.js app repository:**

```sh
npm unlink your-theme-name
```

**In your theme repository:**

```sh
npm unlink
```

Then, reinstall the package normally in your Next.js app:

```sh
npm install
```

This ensures your app is using the published version of the theme package.

---

Following this workflow will allow for a seamless development experience while working on your theme package!
