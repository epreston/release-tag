# release-tag

Modernisation of the [actions/create-release](https://github.com/actions/create-release) github action.

[![CI][ci-badge]][ci-url]

## Usage

Create a workflow `.yml` file in your `.github/workflows` directory referencing this action.

- [Example](docs/example.md).
- [Inputs](docs/inputs.md).
- [Outputs](docs/outputs.md).

## Libraries

| Library         | Reference                                                    |
| --------------- | ------------------------------------------------------------ |
| @actions/core   | https://github.com/actions/toolkit/tree/main/packages/core   |
| @actions/github | https://github.com/actions/toolkit/tree/main/packages/github |

## Tools

| Tool         | Reference                 |
| ------------ | ------------------------- |
| esbuild      | https://esbuild.github.io |
| Node.js      | https://nodejs.org        |
| EditorConfig | https://editorconfig.org  |

## References

| Website               | Reference                                                                        |
| --------------------- | -------------------------------------------------------------------------------- |
| JavaScript Actions    | https://docs.github.com/en/actions/creating-actions/creating-a-javascript-action |
| Create Release        | https://github.com/actions/create-release                                        |
| yyx990803/release-tag | https://github.com/yyx990803/release-tag                                         |
| Akryum/release-tag    | https://github.com/Akryum/release-tag                                            |

## License

This project is released under the MIT [License](LICENSE).

[ci-badge]: https://github.com/epreston/release-tag/actions/workflows/ci.yml/badge.svg
[ci-url]: https://github.com/epreston/release-tag/actions
