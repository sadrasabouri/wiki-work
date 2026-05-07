# Quartz Branch Sites On GitHub Pages

This repo publishes multiple branches into one GitHub Pages site. Each configured
branch is built with Quartz and deployed under its own URL folder.

## Files

- `.github/workflows/publish-quartz-branches.yml` builds and deploys the site.
- `.github/quartz-branches.txt` lists the branches to publish.
- `.github/quartz-content-paths.txt` lists the paths copied into Quartz.
- `.github/quartz-diff-pairs.txt` lists branch pairs to publish as diff sites.

## GitHub Setup

1. Commit and push these files to GitHub.
2. Open the repository on GitHub.
3. Go to **Settings** -> **Pages**.
4. Under **Build and deployment**, set **Source** to **GitHub Actions**.
5. Run the `Publish Quartz Branch Sites` workflow from the **Actions** tab, or
   push a Markdown/config change.

For this repository, the root index will be:

```text
https://sadrasabouri.github.io/wiki-work/
```

The default configured branch URL will be:

```text
https://sadrasabouri.github.io/wiki-work/main/
```

## Publishing More Branches

Add branch names to `.github/quartz-branches.txt`, one per line:

```text
main
demo
public-sanitized
```

Then push those branches to GitHub. They will publish as:

```text
https://sadrasabouri.github.io/wiki-work/main/
https://sadrasabouri.github.io/wiki-work/demo/
https://sadrasabouri.github.io/wiki-work/public-sanitized/
```

Branch names with slashes or special characters are made URL-safe by replacing
non URL-safe characters with `-`.

## Content Safety

By default, only these paths are published:

```text
wiki
raw
.claude/commands
```

That publishes the maintained wiki, generated views, raw Markdown sources, and
Claude command Markdown. Edit `.github/quartz-content-paths.txt` only when a
path is safe to put on the public internet. The workflow publishes
`.claude/commands` rather than all of `.claude` so local settings are not copied
into the Quartz site. It also patches the cloned Quartz build to include
dot-prefixed content paths. Claude command frontmatter is converted to a fenced
YAML block in the temporary Quartz content copy so the source command files stay
unchanged. Any staged `log/` directories and `log.md` pages are removed before
Quartz renders the site.

This only controls the generated website. If the GitHub repository is public,
all tracked source files in all branches are still visible on GitHub. For a
no-pay setup with private source material, keep private material out of the
public repository entirely and publish only sanitized branches or a separate
public publishing repository.

If an older branch was created before this workflow existed, pushes to that
branch may not trigger the workflow automatically. You can either merge the
workflow files into that branch or manually run the workflow from GitHub Actions.

## Diff Sites

A diff site renders the union of two branches' configured content paths and
uses the root `index.md` as a simple file-level diff page. List branch pairs in
`.github/quartz-diff-pairs.txt`, one per line in `BASE...HEAD` form:

```text
main...v0.1
v0.1...main
```

For each listed pair the workflow publishes a site at:

```text
https://sadrasabouri.github.io/wiki-work/main...v0.1/
https://sadrasabouri.github.io/wiki-work/v0.1...main/
```

The site is a normal Quartz build (search, backlinks, navigation all work).
The diff landing page shows counts and a table of added, changed, and deleted
Markdown files, each linking to its rendered page. It also links to the GitHub
compare view for the same branch pair.

The graph view colors every Markdown node by file status:

- green  — added on `HEAD`
- orange — changed between `BASE` and `HEAD`
- red    — deleted on `HEAD` (the page is still clickable; `BASE`'s content is shown)
- gray   — unchanged

Status is decided by SHA-256 byte-level comparison of file contents. Coloring is
applied client-side from a JSON map embedded into each generated HTML page.

If either branch in a pair does not exist on origin, the workflow logs a
warning and skips that pair instead of failing.
