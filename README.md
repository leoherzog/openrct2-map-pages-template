# openrct2-map-pages-template

An interactive, zoomable web map of your OpenRCT2 park — automatically rendered and published to GitHub Pages.

Powered by [openrct2-map](https://github.com/leoherzog/openrct2-map).

## Setup

### 1. Create your repository

Click the green **"Use this template"** button at the top of this page, then **"Create a new repository"**. Give it a name and make sure it's set to **Public** (required for free GitHub Pages hosting) or **Private** if you pay for Github Pro.

### 2. Enable GitHub Pages

In your new repository:

1. Go to **Settings** (gear icon in the top menu bar)
2. Click **Pages** in the left sidebar
3. Under **Source**, select **GitHub Actions**
4. Click **Save**

### 3. Upload your park file

1. Open the **`park/`** folder in your repository
2. Click **Add file** → **Upload files**
3. Drag in your `.park`, `.sv6`, or `.sc6` save file
4. Click **Commit changes**

The map will start rendering automatically. You can check progress in the **Actions** tab. This takes a few minutes.

### 4. View your map

After the build finishes (green checkmark on the **Actions** tab), your map will be live at:

```
https://<your-username>.github.io/<your-repo-name>/
```

## Updating Your Map

Upload a new version of your park file the same way. Each upload creates a new snapshot in the timeline — you can step through them in the viewer.

To re-render with a custom label, go to **Actions** → **Render Park Map** → **Run workflow**, and enter a label.

## Troubleshooting

| Problem | Solution |
|---|---|
| **Build failed** | Check the **Actions** tab for error details. The most common issue is an unsupported file format. |
| **Page shows 404** | Make sure GitHub Pages is set to use **GitHub Actions** as the source (see Step 2). |
| **Map looks outdated** | The build might still be running. Check the **Actions** tab for a yellow spinner. |
| **"No park file found"** | Make sure your save file is inside the `park/` folder, not the repository root. |
