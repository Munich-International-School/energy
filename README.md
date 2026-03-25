# MIS Solar Energy

Live solar energy displays for Munich International School, hosted via GitHub Pages.

## Pages

- **[signage.html](https://munich-international-school.github.io/energy/signage.html)** — Full-screen TV signage display (landscape, auto-cycling slides)
- **[widget.html](https://munich-international-school.github.io/energy/widget.html)** — Compact card widget for embedding on mis-munich.de

## Usage

### TV Signage
Open `signage.html` in a browser on any landscape TV/display. It auto-cycles through slides showing live solar production, CO₂ impact, classroom comparisons, 7-day history, energy tips, and green challenges.

### Website Widget
Embed on any page with:
```html
<iframe src="https://munich-international-school.github.io/energy/widget.html" width="380" height="220" frameborder="0" style="border-radius:16px;overflow:hidden"></iframe>
```

## Configuration
Content (tips, challenges, slide visibility) is managed from the MIS Admin panel under **Solar Digital Signage**.

## Deployment & Secrets

This site is deployed via GitHub Actions. The API key is **never stored in the repository** — it is injected at deploy time from a GitHub Secret.

### Required GitHub Secret

| Secret name | Description |
|---|---|
| `SOLAR_API_KEY` | API key for the Firebase Cloud Functions solar API |

To set or rotate the key:
1. Go to **Settings → Secrets and variables → Actions** in this repository.
2. Create or update the secret named `SOLAR_API_KEY`.
3. Push any commit to `main` (or run the workflow manually) to redeploy with the new key.

### GitHub Pages source

In **Settings → Pages**, set the **Source** to **GitHub Actions** so the deployment workflow controls which build is published.
