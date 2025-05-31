# action-setup-node-env

A composite action that sets up node, pnpm, caching, and installs project dependencies.

This repository is not meant to be referenced in third-party workflows; please fork the repository if you would like to use it in your project.

## Inputs

| Name                | Description                                                                                                                                         | Default |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| cache               | Whether to cache dependencies.                                                                                                                      | "true"  |
| node_version        | The node version to use in version spec syntax.                                                                                                     | "22"    |
| global_dependencies | A space-separated list of packages to install globally. Dependencies in "package.json" files, if present, will not be installed when this is given. | ""      |
| working_directory   | The working directory for the action.                                                                                                               | "."     |

## Outputs

| Name         | Description                 |
| ------------ | --------------------------- |
| node_version | The installed node version. |

## Examples

### Global dependencies

```
jobs:
  node:
    runs-on: ubuntu-latest
    outputs:
      node_version: ${{ steps.node.outputs.node_version }}
    steps:
      - uses: lojoja/action-setup-node-env@main
        id: node
        with:
          cache: "true"
          global_dependencies: >-
            eslint@9.0.0
            globals@16.0.0
          node_version: "22"
```

### Project dependencies

```
jobs:
  node:
    runs-on: ubuntu-latest
    outputs:
      node_version: ${{ steps.node.outputs.node_version }}
    steps:
      - uses: lojoja/action-setup-node-env@main
        id: node
        with:
          cache: "true"
          node_version: "22"
```

## License

action-setup-node-env is released under the [MIT License](./LICENSE)
