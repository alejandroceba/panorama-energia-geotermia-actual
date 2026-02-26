# GitHub Pages Configuration Guide

This project is configured to deploy a Quarto reveal.js presentation to GitHub Pages.

## Setup Steps

### 1. Push your code to GitHub

Ensure you've committed and pushed your code to your GitHub repository on the `main` branch:

```bash
git add .
git commit -m "Configure GitHub Pages deployment"
git push origin main
```

### 2. Enable GitHub Pages

Go to your GitHub repository settings:

1. Navigate to **Settings** → **Pages**
2. Under "Build and deployment":
   - **Source**: Select "Deploy from a branch"
   - **Branch**: Select `main`
   - **Folder**: Select `/ (root)` 

   > Note: The workflow file deploys to the `docs/` folder, which GitHub Pages serves from the repository root when configured this way.

3. Click **Save**

### 3. Verify the deployment

1. GitHub Actions will automatically run the deployment workflow
2. Go to the **Actions** tab to monitor the build
3. Once complete, your presentation will be available at: `https://<your-username>.github.io/<repository-name>`

## Automatic Updates

Any time you push changes to the `main` branch:
- The GitHub Actions workflow (`deploy.yml`) automatically builds the presentation
- The compiled files are deployed to GitHub Pages
- Your presentation updates automatically

## Troubleshooting

If you get a 404 error:

1. **Verify GitHub Pages is enabled**: Check Settings → Pages
2. **Check the source configuration**: Should be `main` branch with `/ (root)` folder selected
3. **Wait for the workflow to complete**: Check the Actions tab for any build errors
4. **Check the workflow file**: Ensure `.github/workflows/deploy.yml` exists and is correctly formatted
5. **Clear browser cache**: Sometimes a hard refresh is needed

## Manual Build

To locally test the presentation before pushing:

```bash
quarto render
```

This generates the HTML in the `docs/` folder which you can open locally.
