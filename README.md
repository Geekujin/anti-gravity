# Anti-Gravity

A neo-cyberpunk stylesheet, and its documentation, served at **https://style.rogues.nexus/**.

This repo is the master copy of `anti-gravity.css`. Every other copy is derived from it.

```html
<link rel="stylesheet" href="https://style.rogues.nexus/v2/anti-gravity.css">
```

## Layout

```
/
  index.html            Docs: getting started and every element, with live examples and code
  CNAME                 style.rogues.nexus
  LICENSE               MIT
  .nojekyll             Serve files as-is (no Jekyll processing)
  v2/
    anti-gravity.css    The stylesheet
    index.html          Release notes for v2: new, changed, deprecated, migration
```

## Setting up hosting (once)

1. Create a public GitHub repo named `anti-gravity` and push these files to `main`.
2. In the repo: Settings > Pages > Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Settings > Pages > Custom domain: `style.rogues.nexus` (the `CNAME` file already sets it).
4. At Porkbun, add a DNS record for `rogues.nexus`:
   - Type `CNAME`, host `style`, answer `geekujin.github.io`
5. Once the DNS check passes, tick **Enforce HTTPS**.

GitHub Pages caches files for about 10 minutes, so sites pick up a new release within that time.

## Releasing a change

**Non-breaking** (fixes, new elements, new variables, new highlights):

1. Edit `v2/anti-gravity.css` and bump the version in its header comment (`v2.3` > `v2.4`).
2. Add a section to the top of `v2/index.html` with tagged entries (New, Changed, Deprecated).
3. Update the version in the footer of both pages and in the Versions table in `index.html`.
4. If the change adds an element, add a `.spec` block for it to `index.html`. Code snippets are generated from the live example automatically.
5. Commit to a branch, open a pull request, check the result, then merge.
6. Sync the copies (see below).

**Breaking** (renamed or removed classes, changed markup, removed deprecated aliases):

1. Copy `v2/` to `v3/` and make the changes there. Leave `v2/` alone apart from critical fixes.
2. Write `v3/index.html` with the breaking changes and a migration table.
3. Point `index.html` at `v3/anti-gravity.css`, add v3 to the Versions table and mark v2 as Maintained.

## Keeping copies in sync

The CSS also lives outside this repo. Always copy **from** this repo, never into it:

1. `v2/anti-gravity.css` here is the source. Edit only this file.
2. The Anti-Gravity Design System on Claude: replace `components/bundle.css` with the new file and note the version.
3. Any project that keeps a local copy instead of linking to the hosted file: replace its copy.

If a change was made somewhere else first (for example, in the design system), bring it into this repo as a pull request, then sync outwards again.

## Protecting `main`

A push to `main` reaches every linked site within about 10 minutes, so:

- Settings > Branches > add a rule for `main`: **Require a pull request before merging**, and block force pushes.
- Optionally require signed commits. Merges made with GitHub's merge button are signed by GitHub.

## Rules for the stylesheet

- Keep the file **pure ASCII**. Write any other character as a CSS escape (`"\25B8 "`), and in HTML as an entity (`&#x25B8;`).
- The last line must stay `:root { --ag-loaded: 1; }`. Pages use it to detect a cut-off download.
- Comments describe the style as neo-cyberpunk and name no games, brands or other sites.

## AI disclosure

AI was used in creating this stylesheet. Anti-Gravity was designed and directed by a person, with an AI model (Claude, by Anthropic) helping to write the CSS, the documentation and the examples.

## Licence

MIT. See `LICENSE`.
