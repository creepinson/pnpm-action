# GitHub Action for PNPM

This Action for [pnpm](https://pnpm.js.org) enables arbitrary actions with the `npm` command-line client, including testing packages and publishing to a registry.

## Usage

An example workflow to install the package and run the build script follows:

```yaml
# This is a basic workflow to help you get started with Actions

name: Build

# Controls when the action will run. Triggers the workflow on push or pull request
# events but only for the master branch
on:
    push:
        branches: [master]

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
    # This workflow contains a single job called "build"
    build:
        # The type of runner that the job will run on
        runs-on: ubuntu-latest

        # Steps represent a sequence of tasks that will be executed as part of the job
        steps:
            # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
            - uses: actions/checkout@v2

            # Runs pnpm install and then builds it using tsc (typescript compiler)
            - uses: creepinson/pnpm-action@master
              with:
                  arguments: '["install", "build"]'
```

## License

The Dockerfile and associated scripts and documentation in this project are released under the [MIT License](LICENSE).

Container images built with this project include third party materials. See [THIRD_PARTY_NOTICE.md](THIRD_PARTY_NOTICE.md) for details.
