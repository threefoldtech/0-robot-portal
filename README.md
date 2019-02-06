# robot portal

The repo provides a tool for visualizing [0-robot](https://github.com/zero-os/0-robot/).

It allows registration of robot connections that can then be explored using the portal.

## Prerequisites

It is built on top of [portal9](https://github.com/Jumpscale/portal9/) and needs portal9 as well as [jumpscale](https://github.com/Jumpscale/core9/).

Follow the instructions [here](https://github.com/Jumpscale/bash/) to have a running installation. And the instructions here to install [0-robot](https://github.com/zero-os/0-robot/blob/master/docs/getting_started.md).

You need to setup config manager before using the robot portal. To create a config directory follow instructions [here](https://github.com/Jumpscale/core9/blob/master/docs/config/configmanager.md).

## Adding the robot portal

### Using prefab

To add the robot portal simply type this in a `js9` shell:

```python
j.tools.prefab.local.web.zrobotportal.install(branch='master')
```

### Manual installation

First clone the repo.

Check the `JumpScale9` config file location by typing `js9` and then:

```python
j.core.state.configJSPath
```

Which should return the location of the toml config file. Under the `portal` section in the config file add the full path of `apps` directory inside this repo to the `contentdirs` field, for example:

```toml
contentdirs = "{path of the repo}/apps"
```

If the portal is already running, first stop the portal:

```python
j.tools.prefab.local.web.portal.stop()
```

To start the portal:

```python
j.tools.prefab.local.web.portal.start()
```

Robot portal should be loaded now.

# Repository Owners:
* [rkhamis](https://github.com/rkhamis), telegram: @rThursday
