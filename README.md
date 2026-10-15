# Pink Cat [PINK] clan tracker

Gems donated and XP contributed by Pink Cat clan members in Pixel Worlds: two-week periods, a custom date
slider, Clan Showdown competitions, and shareable standings images.

- `index.html` – the whole site (page, styles and code).
- `data.json` – the clan data: members, their screenshot snapshots, the deadline and the current showdown.
- `eng-traineddata.wasm` – English text-recognition data for reading screenshots on the device
  (a gzipped Tesseract `eng.traineddata`, named `.wasm` so it is served as a binary file).

## Publishing with GitHub Pages

1. Make the repository public (Settings → General → Danger zone → Change visibility).
2. Settings → Pages → Build and deployment → Source: **Deploy from a branch**, then pick the branch that holds
   `index.html` and the `/ (root)` folder. Save. After a minute the site is at
   `https://<owner>.github.io/<repo>/`.
3. The branch the site saves to is set in `index.html` (`GH.branch`). Keep it the same as the Pages branch.

## Saving from the site

Viewing needs nothing. To save changes, unlock the editor with the clan password, open **Saving to GitHub**
and paste a fine-grained personal access token:

GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.
Repository access: **Only select repositories** → this repo. Permissions → Repository permissions →
**Contents: Read and write**. Nothing else.

The token stays in that browser and is only sent to GitHub. Each save commits `data.json`, and Pages
redeploys the site within about a minute. The clan password only hides the editor; the token is what
allows saving.

## Custom domain (later)

Settings → Pages → Custom domain. Add the DNS records GitHub shows there at your domain registrar. If the
site is served from a custom domain, check that `GH.owner` / `GH.repo` in `index.html` name this repo,
since the page can no longer read them from the address.
