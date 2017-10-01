# Docker Image Utilities

This repository contains scripts used to configure/retrieve configurations for my Docker images and is used as a submodule in them.

## Docker Images

Check out the following repositories under the `./scripts` sub-directory to understand how they are used:

- [`docker-image-alpine-node`](https://github.com/zephinzer/docker-image-alpine-node)
    - [Docker Hub Repository](https://hub.docker.com/r/zephinzer/alpine-node)
- [`docker-image-alpine-node-gitbook`](https://github.com/zephinzer/docker-image-alpine-node-gitbook)
    - [Docker Hub Repository](https://hub.docker.com/r/zephinzer/alpine-node-gitbook)

## Usage

Script filenames should correspond to the environment variable they configure. For example, a script named `base_image_tag` should be setting the environment variable `BASE_IMAGE_TAG`, and should check for the existence of a configuration file named `BASE_IMAGE_TAG` in the `../../conf.d` directory.

## Contributing

### Structure/Standard of Scripts

All scripts should be executable using bash (use the appropriate hashbang). As an example, start all scripts with:

```bash
#!/bin/bash
```

All scripts should have 4 (or 5 if arguments are present) sections:

- `template`
- `constants`
- `arguments` (*optional*)
- `processing`
- `output`

Tag them with a double hex symbol (or hashtag if you will). Example:

```bash
## template
...

## constants
...

### arguments
...

### processing
...

### output
...
```

### Types of Scripts

There are two types of scripts, one that **retrieves a setting from a URL** and the other which **retrieves a setting from a file**.

### Merge Request

Fork this repo, make your changes and make a merge request back to this repository on the `master` branch.