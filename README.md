# Birthday Party Game QR Code Redirects

This repository contains redirect pages for Erin's 46th Birthday Party Games QR codes.

## How It Works

Each HTML file in this repository redirects to the current game server location. This means:
- ✅ QR codes never need to change (they point to GitHub URLs)
- ✅ You can update where they redirect by editing files here
- ✅ Perfect for printed QR codes that need to work even if server changes

## Setup Instructions

1. **Create GitHub Repository**
   - Go to github.com and create a new repository
   - Name it something like `birthday-party-redirects`
   - Make it public
   - Don't initialize with README (we have these files)

2. **Upload Files**
   - Upload all `.html` files from this folder to your GitHub repository
   - Make sure `index.html` is in the root

3. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main (or master)
   - Folder: / (root)
   - Save

4. **Your URLs will be:**
   - Base: `https://YOUR-USERNAME.github.io/REPO-NAME/`
   - Mario Kart: `https://YOUR-USERNAME.github.io/REPO-NAME/mario-kart.html`
   - Trampoline: `https://YOUR-USERNAME.github.io/REPO-NAME/trampoline.html`
   - etc.

## Updating Redirects

When your game server URL changes:

1. Edit `create-redirects.js`
2. Change `CURRENT_SERVER` to your new URL
3. Run `node create-redirects.js`
4. Upload the updated HTML files to GitHub

## Game URLs

Current redirects point to: `https://birthday-party-games.loca.lt`

### Available Games:
- 🦘 Trampoline Jumping → `trampoline.html`
- 🎯 Knife Throwing → `knife-throwing.html`
- 🎱 Mini Billiards → `billiards.html`
- ⚽ Foosball → `foosball.html`
- 🟦 Tetris → `tetris.html`
- 🏎️ Mario Kart → `mario-kart.html`
- 🏀 Basketball Throwing → `basketball.html`
- ⚽ Soccer Goal Kicks → `soccer.html`
- 🎮 Ball Defender → `ball-defender.html`