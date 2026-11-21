# viviansoderberg.com

**Vivian's Place** — a shop and portfolio for Vivian Soderberg's paintings and
fine art prints. Plain HTML with inlined CSS and JavaScript. No framework, no
build step, no dependencies.

## Pages

| File | What it is |
|---|---|
| `index.html` | Homepage — header painting, originals, prints, about, Stay awhile |
| `inquiries.html` | Commission / purchase form |
| `the-valley-over.html`, `the-unknown.html` | The two available originals |
| `once.html`, `memories-home.html`, `somewhere-i-know.html`, `going.html`, `between-dreams.html`, `poppies-at-dusk.html`, `almost.html` | Sold originals |
| `print-lilacs.html`, `print-poppies.html`, `print-white-flowers.html` | The three prints |
| `images/` | All artwork and photography, 2000px on the long edge |
| `favicon.svg` | Tab icon |

Every page carries its own styles, so editing one never affects another. The
colour palette and type stack are defined in the `:root` block at the top of
each file.

## Editing

**Prices, titles, sizes** — the homepage grid and the listing page for a piece
each hold their own copy. Change both.

**Adding a painting** — save the photo in `images/` (lowercase, hyphenated,
2000px long edge), copy an existing `<figure class="card">` block in
`index.html`, and copy a listing page such as `almost.html` as a starting point.

**Marking something sold** — on `index.html` swap the price line to
`$000 <span class="sold">Sold</span>` and replace the "Email to purchase" link
with `<span class="soldout">Sold</span>`. On its listing page swap the buy link
for `<p class="status">Sold</p>`.

## How purchases and signups work

There is no backend and no cart.

- **Email to purchase** links go to `inquiries.html?piece=Name`. The form there
  composes an email to `viviansoderbergart@gmail.com` in the visitor's own mail
  app, pre-filled with the piece name. If no mail app opens, the confirmation
  shows the address as a fallback.
- **Stay awhile** links out to
  <https://viviansoderberg.substack.com/subscribe>.

### Switching to Square later

Create each item in Square with stock tracking set to `1` (originals are
one-of-one, so Square marks the link sold out automatically), generate a payment
link, and replace that product's `href="inquiries.html?piece=..."` with the
Square URL. Change the label from "Email to purchase" back to "Add to cart".
There is a comment above the originals grid in `index.html` describing this.

## Deploying

Cloudflare Pages builds from the repo root. Framework preset **None**, build
command **empty**, output directory **`/`** — it is static, so there is nothing
to build. Pushing to `main` deploys.

DNS is at GoDaddy. Either move the nameservers to Cloudflare so the apex and
`www` work automatically with SSL, or keep DNS at GoDaddy, add a `CNAME` for
`www` pointing at the `*.pages.dev` host, and use GoDaddy Forwarding to send the
root to `https://www.viviansoderberg.com`.

## Still to do

- **Objects** is in the menu but has no page yet — needs photos of the
  reclaimed-wood pieces.
- Eight of the ten originals have **no dimensions**, so their listing pages read
  only "Original" and their cards show no size on hover.
- `images/` holds photographs that no page currently uses, including the
  earlier unnamed shots of the same paintings. They cost nothing to a visitor,
  but can be pruned.
