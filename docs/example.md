## Example

On every `push` to a tag matching the pattern `v*.*.*`, [create a github release](https://developer.github.com/v3/repos/releases/#create-a-release):

```yaml
# When a version tag is pushed, create a github release

name: Create Release

on:
  workflow_dispatch:

  push:
    tags:
      - "v*.*.*"

permissions: {}

jobs:
  release-tag:
    name: Create Release
    runs-on: ubuntu-latest

    permissions:
      contents: write

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Release
        id: release_tag
        uses: @epreston/release-tag@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          tag_name: ${{ github.ref }}
          release_name: ${{ github.ref_name }}
          body: |
            Please refer to the commit [history](${{ github.server_url }}/${{ github.repository }}/commits/main) for details.
```

This will create a [Release](https://help.github.com/en/articles/creating-releases), as well as a [`release` event](https://developer.github.com/v3/activity/events/types/#releaseevent), which could be handled by a third party service, or by GitHub Actions for additional uses, for example the [`@actions/upload-release-asset`](https://www.github.com/actions/upload-release-asset) GitHub Action. This uses the `GITHUB_TOKEN` provided by the [virtual environment](https://help.github.com/en/github/automating-your-workflow-with-github-actions/virtual-environments-for-github-actions#github_token-secret), so no new token is needed.
