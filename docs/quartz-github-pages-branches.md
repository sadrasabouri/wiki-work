# Quartz Branch Sites On GitHub Pages

This repo publishes multiple branches into one GitHub Pages site. Each configured
branch is built with Quartz and deployed under its own URL folder.

## Files

- `.github/workflows/publish-quartz-branches.yml` builds and deploys the site.
- `.github/quartz-branches.txt` lists the branches to publish.
- `.github/quartz-content-paths.txt` lists the paths copied into Quartz.

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
views
```

That intentionally leaves `raw/` unpublished. Edit
`.github/quartz-content-paths.txt` only when a path is safe to put on the public
internet.

This only controls the generated website. If the GitHub repository is public,
all tracked source files in all branches are still visible on GitHub. For a
no-pay setup with private source material, keep private material out of the
public repository entirely and publish only sanitized branches or a separate
public publishing repository.

If an older branch was created before this workflow existed, pushes to that
branch may not trigger the workflow automatically. You can either merge the
workflow files into that branch or manually run the workflow from GitHub Actions.
