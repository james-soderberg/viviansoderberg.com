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
4. Deploy. Then, under the project's **Custom domains** tab, add
   `viviansoderberg.com`. Since the domain's DNS is already in Cloudflare, the
   DNS record is created for you automatically.
