# viviansoderberg.com

A temporary single-page placeholder for **viviansoderberg.com** while the full
site is rebuilt. Plain HTML + CSS, no framework, no build step. It shows a short
"getting a facelift" notice and a mailing-list signup form.

## Files

- `index.html` — the page and its form-handling JavaScript (inlined)
- `styles.css` — all styling
- `favicon.svg`

The `variations/` folder holds earlier full-site design explorations and is not
part of the placeholder.

## Setup

### 1. Get a Web3Forms access key

The form submits to [Web3Forms](https://web3forms.com), which emails you each
signup — no backend required.

1. Go to <https://web3forms.com> and enter the address where you want signups
   delivered. You'll receive an access key by email.
2. In `index.html`, find the comment marked `Web3Forms access key` and replace
   `YOUR_ACCESS_KEY_HERE` with your key:

   ```html
   <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY_HERE" />
   ```

   The key is meant to live in client-side code and is safe to commit.

### 2. Connect the repo to Cloudflare Pages

1. Push this folder to a GitHub repository.
2. In the Cloudflare dashboard: **Workers & Pages → Create → Pages → Connect to
   Git**, and select the repo.
3. Build settings — leave **Framework preset** as *None*, **Build command**
   empty, and **Build output directory** as `/`. It's static, so there's nothing
   to build.
4. Deploy. You'll get a `*.pages.dev` URL immediately.

### 3. Point the domain (DNS is at GoDaddy)

In the Pages project's **Custom domains** tab, add `viviansoderberg.com`.
Cloudflare will show a target hostname. Because DNS lives at GoDaddy (not
Cloudflare), pick one:

- **Recommended — move DNS to Cloudflare.** Add the domain in Cloudflare, then
  at GoDaddy change the nameservers to the two Cloudflare gives you. After it
  propagates, the apex + `www` custom domain works automatically with SSL.
- **Keep DNS at GoDaddy.** GoDaddy can't CNAME the apex, so at GoDaddy add a
  `CNAME` record for `www` → the `*.pages.dev` host, add `www.viviansoderberg.com`
  as the Pages custom domain, and use GoDaddy **Forwarding** to send the root
  `viviansoderberg.com` → `https://www.viviansoderberg.com`.
