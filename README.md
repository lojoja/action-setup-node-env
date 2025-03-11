# action-setup-node-env

A composite action that sets up node, pnpm, caching, and installs project dependencies.

This repository is not meant to be referenced in third-party workflows; please fork the repository if you would like to use it in your project.

```
- uses: lojoja/action-setup-node-env@main
  with:
    node-version: ""
```

See [actions/setup-node](https://github.com/actions/setup-node/blob/main/README.md) for possible `node-version` values.

## License

action-setup-node-env is released under the [MIT License](./LICENSE)
