# Website language and editing guide

The default homepage is Japanese. This is a static site: no build step, language-detection script, or redirect is required.

| File | Purpose |
| --- | --- |
| `index.html` | Default homepage at the site root; an exact copy of the selected language's homepage |
| `index-ja.html` | Canonical Japanese homepage |
| `index-en.html` | Canonical English homepage |
| `resume-ja.html` | Japanese résumé |
| `resume.html` | English résumé; preserves the existing URL |
| `style.css` | Shared styling, Japanese fonts, and language controls |

The EN / JP controls always link directly to the canonical language pages. Résumé links also return to the corresponding canonical homepage. Visitors' browser language does not override the selected default.

## Make English the default later

Copy **all contents** of `index-en.html` into `index.html`, then commit the change to the branch used by GitHub Pages. No other link changes are needed.

From a local checkout:

```sh
cp index-en.html index.html
git add index.html
git commit -m "Make English the default homepage"
git push origin main
```

Run the commands on your publishing branch (`main`). GitHub Pages will publish the commit after its deployment finishes. In GitHub's web editor, the equivalent is to open `index-en.html`, copy its complete source, replace the complete source of `index.html`, and commit to `main`.

To restore Japanese as the default, copy `index-ja.html` into `index.html` instead and commit.

## Update content

Edit the appropriate canonical page (`index-ja.html` or `index-en.html`). If that language is currently the default, copy the updated canonical page into `index.html` as well. The root copy must stay identical to the selected canonical homepage.

Edit `resume-ja.html` or `resume.html` for résumé changes. They do not need a root copy. Keep the original English paper titles; Japanese title translations are explicitly labeled as reference translations.

The static site has no in-page editing controls. The original private Sites editor is separate and is not changed by this package.
