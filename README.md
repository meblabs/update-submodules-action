# update-submodules-action

GitHub action for updating references to submodules in parent repo

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
        uses: meblabs/update-submodules-action@v2.0
        with:
          parent: Blackfin-Eyewear/HyperFarm
          token: ${{ secrets.MEBBOT }}
		  commit_message: "chore: Update Api [skip ci]"
```

If there are multiple parents to update you can use the matrix strategy to run multiple jobs