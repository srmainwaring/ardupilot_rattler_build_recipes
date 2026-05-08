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
rattler-build publish --recipe ./recipe.yaml -c "https://prefix.dev/ardupilot" -c "robostack-kilted" -c "conda-forge" --build-number=+1 --to https://prefix.dev/ardupilot
```

### Workflow

```bash
# build and publish to local channel
rattler-build publish --recipe ./recipe.yaml -c "https://prefix.dev/ardupilot" -c "robostack-jazzy" -c "conda-forge" --to ~/.pixi/channels/ardupilot/

# index local channel
rattler-index fs ~/.pixi/channels/ardupilot

# publish to prefix.dev
rattler-build upload prefix --channel ardupilot ~/.pixi/channels/ardupilot/osx-arm64/ros-jazzy-*.conda
```

### Appendix A: micro-ROS-Agent dependencies

The micro-ROS-Agent dependencies are packaged separately rather than with the project as is typically the case via the use of `ExternalProject_Add` in the `SuperBuild.cmake`. These dependencies are pinned to specific commits listed below.

#### Jazzy

```yaml
name: micro-ros-agent
version: "5.0.2"
expected_commit: af007872b034d1ed31de4815377031350ab0034b

name: micro-ros-msgs
version: "5.0.2"
expected_commit: 4594d9db17db735b1e655141fb4afb4cdcfc5789

name: micro-xrce-dds-agent
version: "2.4.3"
expected_commit: 73622810d984349b80bbac0ef55fc0b694d62222

name: micro-xrce-dds-client
version: "2.4.3"
expected_commit: d44dc3fa0c488376e34d26ed92853f1c66dcb670 

name: micro-cdr
version: "2.0.1"
tag: "2.0.1"

name: fastcdr
version: "2.2.0"
tag: "2.2.x"

name: fastrtps
version: "2.14"
tag: "2.14.x"

name: foonathan_memory
tag: "0.7-3"

name: spdlog
version: "1.9.2"
tag: "1.9.2"
```

#### Kilted

```yaml
name: micro-ros-agent
version: "6.1.0"

name: micro-ros-msgs
version: "6.0.0"

name: micro-xrce-dds-agent
version: "3.0.1"
expected_commit: 155cfaaf8b7abac2e85d4a62d3649b09ace0be55

name: micro-xrce-dds-client
version: "3.0.0"
expected_commit: 9e05a62f3352ce5bf1cec0d2b518391179213ce6 

name: micro-cdr
version: "2.0.1"
tag: "2.0.1"

name: fastcdr
version: "2.2.4"
tag: "2.2.x"

name: fastdds
version: "3.1"
tag: "3.x"

name: foonathan_memory
tag: "0.7-3"

name: spdlog
version: "1.9.2"
tag: "1.9.2"
```
