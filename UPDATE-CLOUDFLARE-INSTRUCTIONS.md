# How to Update Cloudflare Tunnel Address for Permanent QR Codes

## Quick Steps (for Claude or anyone updating)

### 1. Start a New Cloudflare Tunnel
```bash
# From the main Birthday Game Leaderboard directory:
./cloudflared-linux-amd64 tunnel --url http://localhost:3000
```
Wait for the output to show the new URL like: `https://rapidly-familiar-korea-whenever.trycloudflare.com`

### 2. Update ALL Redirect Files
The redirect files are in `/mnt/c/Users/erin/Birthday Game Leaderboard/github-redirects/`

Run this command to update all redirect files at once:
```bash
cd "/mnt/c/Users/erin/Birthday Game Leaderboard/github-redirects"
OLD_URL="https://wrestling-buttons-tax-scores.trycloudflare.com"  # Replace with current expired URL
NEW_URL="https://rapidly-familiar-korea-whenever.trycloudflare.com"  # Replace with new Cloudflare URL

for file in *.html; do
    if [ "$file" != "index.html" ]; then
        sed -i "s|$OLD_URL|$NEW_URL|g" "$file"
    fi
done
```

### 3. Verify the Updates
Check that all files were updated:
```bash
for file in *.html; do
    if [ "$file" != "index.html" ]; then
        echo "$file: $(grep -c "$NEW_URL" "$file")"
    fi
done
```
Each file should show "3" (three occurrences of the new URL)

## Files That Need Updating
These HTML files in `github-redirects/` folder need updating:
- admin.html
- ball-defender.html
- basketball.html
- billiards.html
- foosball.html
- knife-throwing.html
- leaderboard.html
- mario-kart.html
- soccer.html
- tetris.html
- trampoline.html

**DO NOT UPDATE:** index.html (this is just the landing page)

## What Gets Updated in Each File
Each redirect file has 3 places where the Cloudflare URL appears:
1. The meta refresh tag: `<meta http-equiv="refresh" content="0; url=...">`
2. The JavaScript redirect: `window.location.href = '...'`
3. The fallback link: `<a href="...">Click here to continue...</a>`

## Why This Works
- The permanent QR codes point to GitHub Pages URLs (e.g., `https://erinb-maker-radio.github.io/birthday-party-redirects/trampoline.html`)
- These GitHub Pages files redirect to your Cloudflare tunnel
- When the Cloudflare URL expires, you only need to update these redirect files
- The QR codes themselves never need to change!

## Current Cloudflare URL
**Last Updated:** September 27, 2025
**Current URL:** https://rapidly-familiar-korea-whenever.trycloudflare.com

## Troubleshooting
- If sed command doesn't work, make sure to escape special characters in the URLs
- Always exclude index.html from updates (it's not a redirect file)
- Each redirect file should have exactly 3 occurrences of the Cloudflare URL
- The Cloudflare tunnel must be running for the redirects to work