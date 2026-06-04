# update-submodules-action

[![zizmor](https://github.com/meblabs/update-submodules-action/actions/workflows/zizmor.yml/badge.svg)](https://github.com/meblabs/update-submodules-action/actions/workflows/zizmor.yml)

GitHub action for updating references to submodules in parent repo

> [!IMPORTANT]
> This action relies on `actions/checkout@v6`, which runs on the Node 24 runtime.
> Use it on `ubuntu-latest` or a self-hosted runner with agent `>= v2.327.1`.

## How to use

Workflow
```yml
on:
  push:
    branches:    
      - dev
      - staging
      - release

jobs:
  update-parent:
    runs-on: ubuntu-latest
    steps:
      - name: Update parent
        uses: meblabs/update-submodules-action@v3
        with:
          parent: Blackfin-Eyewear/HyperFarm
          token: ${{ secrets.MEBBOT }}
          commit_message: "chore: Update Api [skip ci]"
```

If there are multiple parents to update you can use the matrix strategy to run multiple jobs