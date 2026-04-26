# Gearutil Website

Static website for Gearutil hosted on Firebase Hosting.

## Project Structure

```
├── firebase.json    # Firebase configuration
├── public/          # Static website files
│   ├── index.html
│   ├── 404.html
│   └── tidy-reel/   # Subdirectory pages
```

## Development

To view the website locally:

1. Open `public/index.html` in a browser, or
2. Use a local server (e.g., `npx serve public`)

## Deployment

### Prerequisites

- Node.js installed
- Firebase CLI installed (`npm install -g firebase-tools`)
- Firebase project set up

### One-Time Setup

1. **Login to Firebase:**

   ```bash
   firebase login
   ```

   This opens a browser for authentication. Follow the prompts to sign in to your Google account and authorize Firebase CLI.

2. **Initialize Firebase (if not already initialized):**

   ```bash
   firebase init
   ```

   Select "Hosting" and choose your project when prompted.

### Deploying Changes

After making changes to the project files in the `public/` directory:

```bash
firebase deploy -m "Updated website content for [brief description of changes]" --only hosting
```

Example:

```bash
firebase deploy -m "Updated homepage content for spring sale" --only hosting
```

### Deployment Options

| Command | Description |
|---------|-------------|
| `firebase deploy --only hosting` | Deploy only hosting (not functions, etc.) |
| `firebase deploy` | Deploy all configured services |
| `firebase deploy --only hosting --debug` | Deploy with debug output |

## Custom Domain (Optional)

If you've configured a custom domain:

1. Run `firebase hosting:channel:create` to create a preview channel
2. Test your changes on a preview URL
3. When ready, run `firebase deploy` to publish to production

## Troubleshooting

- **Authentication issues:** Run `firebase logout` then `firebase login` again
- **Permission errors:** Ensure you have access to the Firebase project in the Firebase Console
- **Deployment failures:** Check the Firebase Console for error details

## More Resources

- [Firebase Hosting Docs](https://firebase.google.com/docs/hosting)
- [Firebase CLI Reference](https://firebase.google.com/docs/cli)