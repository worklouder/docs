# Work Louder Docs

Developer documentation for Work Louder devices and the Input app, built with [Mintlify](https://mintlify.com).

## Contents

| Page                                  | Description                                                     |
| ------------------------------------- | --------------------------------------------------------------- |
| [InputKit](input-kit/user-guide.mdx)  | Control your device from your own scripts and apps over WebSocket |

## Project structure

```
docs.json                  Site configuration: name, colors, logo and navigation
input-kit/user-guide.mdx   InputKit guide (Input's WebSocket API)
logo/                      Light and dark mode logos
favicon.png                Browser tab icon
```

Pages are MDX files (Markdown with components) with a YAML header that sets the
page `title` and `description`.

## Adding a page

1. Create an `.mdx` file with a header:

    ```mdx
    ---
    title: "Page title"
    description: "One-line summary"
    ---
    ```

2. Add its path, without the extension, to `navigation` in `docs.json`. Pages that
   are not listed there do not appear in the sidebar.

See the [Mintlify components](https://mintlify.com/docs/components) for callouts,
steps, tabs, cards and more.

## Local preview

Run the following from the repository root:

```bash
npx mint dev
```

The site opens at `http://localhost:3000`.

## Checks

Run both before opening a pull request:

```bash
npx mint validate
npx mint broken-links --check-anchors
```

## Publishing

The site deploys automatically when changes are merged into `main` through the
Mintlify GitHub app. Open a pull request from a branch rather than pushing to
`main` directly.

## Troubleshooting

- If the preview does not start, run `npx mint@latest dev` to use the latest CLI.
- If a page returns 404, check that it is listed in `docs.json` and that you are
  running the command from the folder that contains `docs.json`.
