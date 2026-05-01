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

Store authentication credentials

```bash
pixi auth login prefix.dev --token pfx-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Publish to private channel and bump build number

```bash
rattler-build publish recipe.yaml --to https://prefix.dev/ardupilot -c "conda-forge" -c "https://prefix.dev/ardupilot" --build-number=+1
```