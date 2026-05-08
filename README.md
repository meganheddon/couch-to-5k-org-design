# Couch to 5K: Org Design

A free 30-day organization design learning program. Single HTML file, no backend, no build step.

---

## Deploying to Netlify

1. Create a new GitHub repository and push `index.html` to the root.
2. Go to [netlify.com](https://netlify.com) → **Add new site → Import an existing project**.
3. Connect your GitHub account and select the repository.
4. Set **Publish directory** to `/` (or leave blank — Netlify auto-detects it).
5. Click **Deploy site**.
6. Add your custom domain under **Domain settings** → Netlify handles SSL automatically.

No build command needed.

---

## Swapping in Beehiiv

Two embed placeholders are marked in `index.html` with `<!-- BEEHIIV HERO EMBED -->` and `<!-- BEEHIIV FOOTER EMBED -->` comments.

To replace:
1. In Beehiiv, go to **Publication Settings → Embeds**.
2. Copy the HTML embed code for your publication.
3. In `index.html`, find the comment block and replace the `<div id="hero-form-wrap">...</div>` section with your Beehiiv embed code.
4. Repeat for the footer embed.

Tag all signups from these forms with the segment `couch-to-5k-org-design` in your Beehiiv automation settings.

---

## Adding Your Links

Search `index.html` for `<!-- ADD ... URL -->` comments — there are three:

- `<!-- ADD ENHRGY URL -->` — your EnHRgy website
- `<!-- ADD NEWSLETTER URL -->` — your newsletter or Substack
- `<!-- ADD PRIVACY URL -->` — your privacy policy (generate one free at termly.io)

---

## How Progress Works

All progress is stored in the browser's `localStorage` under the key `c5k-od-progress`. No server needed. Users' progress persists across page refreshes but is specific to their browser/device.

localStorage structure:
```json
{
  "completedDays": [1, 2, 3],
  "commitmentDate": "2026-06-01",
  "commitmentVenue": "Monthly team all-hands"
}
```

---

## Separate Deliverables (Not In This File)

- **OD Canvas PDF** — design in Canva, link from the first Beehiiv automation email
- **Beehiiv 30-email automation sequence** — one email per day, same prompt + key takeaway format
- **Privacy policy page** — generate at termly.io, link from footer
