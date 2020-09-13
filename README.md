<p align="center">
  <!-- <img alt="Cider logo" src="assets/go.png" height="150" /> -->
  <h3 align="center">Cider Buildkite Plugin</h3>
  <p align="center">A Buildkite Plugin for <a href="https://github.com/cidertool/cider">Cider</a>, the App Store submission tool for Apple apps</p>
</p>

---

[![Release](https://img.shields.io/github/release/cidertool/cider-buildkite-plugin.svg)](https://github.com/cidertool/cider-buildkite-plugin/releases/latest)
![test](https://github.com/cidertool/cider-buildkite-plugin/workflows/test/badge.svg)
[![Github Releases Stats of cider-buildkite-plugin](https://img.shields.io/github/downloads/cidertool/cider-buildkite-plugin/total.svg?logo=github)](https://somsubhra.com/github-release-stats/?username=cidertool&repository=cider-buildkite-plugin)

This plugin makes it easy to use [Cider](https://cidertool.github.io/cider) in your Buildkite pipelines.

## Usage

```yaml
steps:
  - label: ':apple: Release with Cider'
    plugins:
      - cidertool/cider#v0.1.0:
          args: release --mode appstore
    env:
      ASC_KEY_ID: '...'
      ASC_ISSUER_ID: '...'
      ASC_PRIVATE_KEY: '...'
```

## Configuration

### Required

### `args` (string or array of strings)

The subcommand and arguments to pass to Cider. See the [Command Reference](https://cidertool.github.io/cider/commands/) for guidance on what's supported. This field is required because otherwise Cider won't do anything of consequence.

### Optional

### `version` (string)

Version of Cider to use, based on the tags [available in Docker Hub](https://hub.docker.com/repository/docker/cidertool/cider). 

Default: `latest`

### `workdir` (string)

Directory to run Cider in, relative to the checkout root.

Default: `"."`

## Contributing

Contributions are always welcome. If you want to get involved or you just want to offer feedback, please see [`CONTRIBUTING.md`](./.github/CONTRIBUTING.md) for details.

## License

This library is licensed under the [MIT License](./LICENSE)
