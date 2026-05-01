A collection of rattler-build recipes for packages used with ArduPilot.


Build package (e.g. micro-cdr)

```bash
cd recipes/micro-cdr
rattler-build build --recipe recipe.yaml
```

Publish package to a local channel

```bash
rattler-build publish ./output/osx-arm64/micro-cdr-2.0.1-h60d57d3_0.conda --to ~/.pixi/channels/ardupilot
```

Publish package to a local channel, overwriting previous instance

```bash
rattler-build publish --force ./output/osx-arm64/micro-cdr-2.0.1-h60d57d3_0.conda --to ~/.pixi/channels/ardupilot
```

Publish package to prefix-dev

```bash
rattler-build upload prefix --channel ardupilot ./output/osx-arm64/micro-cdr-2.0.1-h60d57d3_0.conda --api-key pfx_xxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

