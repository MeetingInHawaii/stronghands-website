# StrongHands (SHND) website

Static website for StrongHands (SHND), designed for GitHub Pages at <https://stronghands.love/>.
Plain HTML, CSS and a few lines of JavaScript. No build step, no dependencies, no external fonts or trackers.

## Structure

```
index.html            single-page site (Home, About, Motto, Technology, Wallet, Explorer,
                      Exchange, Mining & Staking, Community, History)
404.html              not-found page (noindex)
css/style.css         all styles (black and yellow theme)
js/main.js            mobile menu toggle only
assets/               logo (PNG + WebP), favicons, 1200x630 share image
robots.txt            crawler rules + sitemap location
sitemap.xml           sitemap (one page)
CNAME                 custom domain for GitHub Pages (stronghands.love)
```

## Run locally

```sh
cd website
python3 -m http.server 8000
# open http://localhost:8000
```

## Publish with GitHub Pages

1. Create a GitHub repository (for example `stronghands-website`) and push the contents of this folder to the `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Custom domain: the `CNAME` file already contains `stronghands.love`. In **Settings → Pages → Custom domain** enter `stronghands.love`.
4. DNS at your registrar (Namecheap → Advanced DNS):
   - four `A` records for host `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - one `CNAME` record for host `www` pointing to `<your-github-user-or-org>.github.io.`
   - remove the old parking `A`/`CNAME` records. Keep any `MX` and `TXT` (SPF) records if you use e-mail forwarding.
5. Wait for DNS and the certificate (up to a few hours), then enable **Enforce HTTPS** in Settings → Pages.
6. Test: `https://stronghands.love/`, `https://www.stronghands.love/` (redirects to the apex), `https://stronghands.love/robots.txt`, `https://stronghands.love/sitemap.xml`.
7. Optional: add the domain to Google Search Console and submit `https://stronghands.love/sitemap.xml`.

## Content rules (keep these when editing)

- The subject is StrongHands **(SHND)** only. Do not mix it with StrongHands Masternode (SHMN) or StrongHands Finance (iSHND).
- The only exchange promoted is XT.com (`https://www.xt.com/en/trade/shnd_usdt`).
- The only social channels are Twitter/X (`https://twitter.com/SHNDcoin`) and Telegram (`https://t.me/stronghands`).
- No prices, market capitalization, supply figures, statistics or profit promises.
- Technical figures must link to the source code or the Bitcointalk thread. The Technology table points to
  commit `70741af7b6cb85afba53950e54d2004b928a733f` of
  [`stronghandsblockchain/SHND-NewSource`](https://github.com/stronghandsblockchain/SHND-NewSource) so line numbers stay valid.
  If the source changes, re-check every row and update the commit hash.
- Wallet links point to the assets of release `v07301`. When a new release is published, update the Wallet table
  (file names, sizes, dates) from <https://github.com/stronghandsblockchain/SHND-NewSource/releases>.
- All external links use `target="_blank" rel="noopener noreferrer"`. Do not add other external links without approval.

## Motto (English and Japanese)

The motto section shows the English text and a Japanese translation with the flag of Japan (inline SVG).
Have the Japanese text checked by a native speaker before relying on it.

## Sources used

- Bitcointalk community thread: <https://bitcointalk.org/index.php?topic=2709780>
- Source code and releases: <https://github.com/stronghandsblockchain/SHND-NewSource>
- Logo: the original StrongHands coin image supplied by the project owner.
