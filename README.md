# Split-it

A funky little bill-splitter for friends — *split the bill, not the friendship*.

Add who's at the table, snap or type the receipt, tap who had what, and it works out
who owes what (service charge included). Households and couples can be grouped at the
end so each family pays one amount — no calculator required.

## Using it

1. **Who** — add everyone at the table (first names are fine).
2. **Items** — photograph/upload the receipt, or type items in by hand. Every line is editable.
3. **Split** — tap the people who shared each item. Tapping more than one splits it equally;
   anything left untagged falls into "other / shared".
4. **Total** — set the service-charge %, then read off each person's total. Use the
   **By group** toggle to combine a household into one payment line.

Themes and the house colour can be changed in the **Tweaks** panel (bottom-right).

## Receipt scanning & your API key

Scanning the receipt photo uses Claude's API, called directly from your browser. To keep this
free of any server, it uses a **bring-your-own-key** approach:

- The first time you open the app, paste your own Anthropic API key into the box on the
  **Items** step (get one at <https://console.anthropic.com/settings/keys>).
- The key is stored **only on that device** (in the browser's local storage). It is never
  shared, never sent anywhere except directly to Anthropic, and never committed to this repo.
- Friends who open the link without a key simply type items in instead — everything else
  (splitting, grouping, service charge) works with no key at all.

**Do not** hard-code a key into this file or share a device that has your key saved. Anyone
with the key could run up usage on your account. Set a low monthly spend cap on your
Anthropic account for peace of mind.

Scanning uses the inexpensive Claude Haiku model, so a receipt scan costs a fraction of a penny.

## How it's hosted

A single static `index.html` served from GitHub Pages, in this subfolder. No build step,
no backend. React and Babel load from a CDN at runtime.

## Updating

Replace `index.html` with a new version, commit, and push — GitHub Pages redeploys
automatically within a minute or two.
