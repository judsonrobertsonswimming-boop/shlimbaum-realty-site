# Shlimbaum Realty website

Static site for GitHub Pages. No build step: the files in this folder are the site.

## Files
- `index.html`: the one-page site
- `privacy.html`: privacy policy
- `*.png`: logos and photo of Jay
- `CNAME`: the custom domain GitHub Pages serves (currently `www.shlimbaumrealty.com`; change it if the domain is different)
- `robots.txt`, `sitemap.xml`: for Google (update the domain inside them if it changes)

## Go live on GitHub Pages
1. Create a new **public** repository on GitHub (for example `shlimbaum-realty-site`).
2. Upload everything in this folder to the repository's main branch.
3. In the repository: Settings > Pages > Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`. Save.
4. In Settings > Pages > Custom domain, enter `www.shlimbaumrealty.com` and save.
5. The domain owner adds these DNS records (and changes nothing else, especially not the MX records that run email):
   - `www`  CNAME  `<your-github-username>.github.io`
   - `@`  A  `185.199.108.153`
   - `@`  A  `185.199.109.153`
   - `@`  A  `185.199.110.153`
   - `@`  A  `185.199.111.153`
   Remove any old A or CNAME records for `@` and `www` that point at the previous website.
6. Wait for DNS to update (minutes to a few hours), then tick "Enforce HTTPS" in Settings > Pages.

## Connect the form to Podio
The form posts to one web address. Open `index.html`, find `var FORM_ENDPOINT = "";` near the bottom, and paste the webhook address between the quotes.

The form sends these fields: `address`, `name`, `phone`, `email`, `timeline`, `lead_source`.
`lead_source` is "Shlimbaum Realty Website Lead". A link like `/?src=mail` (for the mailer QR code) sends "Shlimbaum Realty Website Lead (mail)".

Until the address is pasted in, the form shows "We could not send your request. Please call now" so no lead is silently lost.

## Before launch
- Confirm the phone number (954) 703-9360 is the one to publish.
- Have the privacy policy reviewed.
- Sections held back until there is real content: market stats, client review quotes, more recent sales, Jay's own words, commission FAQ.
