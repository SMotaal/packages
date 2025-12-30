# @smotaal/packages

Public release distribution for @smotaal packages.

## Installation

Packages are distributed as GitHub Releases. Install using the release tarball URL:

```bash
# Install a specific version
yarn add @smotaal/markdown-to-html@"https://github.com/smotaal/packages/releases/download/markdown-to-html@1.0.0/smotaal-markdown-to-html-1.0.0.tgz"

# Or using Yarn Berry's git protocol with workspace support
yarn add @smotaal/markdown-to-html@"git@github.com:smotaal/tools.git#tag=markdown-to-html@1.0.0&workspace=@smotaal/markdown-to-html"
```

## Available Packages

| Package | Description |
| ------- | ----------- |
| `@smotaal/markdown-to-html` | Convert Markdown to HTML using GitHub's rendering |
| `@smotaal/monorepo-tools` | CLI for multi-monorepo workflows |

See [Releases](https://github.com/smotaal/packages/releases) for all available versions.

## Resolution Patterns

### Pattern 1: Direct Release URL

Use for stable, version-pinned installations:

```json
{
  "dependencies": {
    "@smotaal/markdown-to-html": "https://github.com/smotaal/packages/releases/download/markdown-to-html@1.0.0/smotaal-markdown-to-html-1.0.0.tgz"
  }
}
```

### Pattern 2: Git SSH with Workspace

Use for development or when you need a specific branch/commit:

```json
{
  "dependencies": {
    "@smotaal/markdown-to-html": "git@github.com:smotaal/tools.git#head=main&workspace=@smotaal/markdown-to-html"
  }
}
```

### Pattern 3: Resolution Override

Map a different package name to a release:

```json
{
  "dependencies": {
    "@gists.smotaal.io/markdown-to-html": "latest"
  },
  "resolutions": {
    "@gists.smotaal.io/markdown-to-html": "https://github.com/smotaal/packages/releases/download/markdown-to-html@1.0.0/smotaal-markdown-to-html-1.0.0.tgz"
  }
}
```

## Publishing

Releases are created from the private [@smotaal/tools](https://github.com/smotaal/tools) repository using the `multirepo` CLI:

```bash
yarn exec multirepo publish markdown-to-html
```

This creates a GitHub Release with the packed tarball as an asset.
