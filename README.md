# openrct2-map-pages-template

An interactive, zoomable web map of your OpenRCT2 park, rendered and published to GitHub Pages whenever you upload a save.

Powered by [openrct2-map](https://github.com/leoherzog/openrct2-map). Every render uses the tool's latest release.

## Setup

### 1. Create your repository

Click the green **"Use this template"** button at the top of this page, then **"Create a new repository"**. Make it **Public** for free GitHub Pages hosting. A private repository needs a paid plan such as GitHub Pro, and the published map is still publicly visible.

### 2. Enable GitHub Pages

In your new repository:

1. Go to **Settings** → **Pages**
2. Under **Build and deployment**, set **Source** to **GitHub Actions**

### 3. Upload your park file

1. Open the **`park/`** folder in your repository
2. Click **Add file** → **Upload files**
3. Drag in your `.park`, `.sv6`, `.sc6`, or `.sv4` save file
4. Click **Commit changes**

Keep only one save file in `park/`. If there are several, the workflow renders whichever it finds first.

Rendering starts automatically and takes a few minutes. Follow progress in the **Actions** tab. The first run takes longer because it downloads OpenRCT2 and the game data, which are cached for later runs.

### 4. View your map

When the run shows a green checkmark, your map is live at:

```
https://<your-username>.github.io/<your-repo-name>/
```

Shared links show a preview image on Discord, Slack, and social media.

## Updating Your Map

Upload the new save to `park/`. A file with the same name replaces the old one; otherwise delete the old file. Each render replaces the whole map, so earlier versions are not kept.

The map's title defaults to the render's date and time in UTC. To set your own, go to **Actions** → **Render Park Map** → **Run workflow** and enter a label. This re-renders the current save.

## Render Options

The map renders with a transparent background, a tidied park, and sunny weather. To change these or other settings such as zoom and rotations, add flags to the **Render map** step in `.github/workflows/render.yml`. The [openrct2-map README](https://github.com/leoherzog/openrct2-map#readme) documents the available flags.

## Troubleshooting

| Problem | Solution |
|---|---|
| **Build failed** | Open the failed run in the **Actions** tab for the error. |
| **A run failed before you uploaded a save** | Expected. The workflow ran on the repository's first commit, before there was a park to render. |
| **"No park file found"** | Put the save inside `park/`, not the repository root, with one of the extensions listed above. |
| **Wrong park rendered** | `park/` holds more than one save. Delete all but one. |
| **Page shows 404** | Set the Pages source to **GitHub Actions** (step 2) and wait for a successful run. |
| **Map looks outdated** | The run may still be going; check **Actions** for a yellow spinner. GitHub Pages also caches pages for up to 10 minutes. |
