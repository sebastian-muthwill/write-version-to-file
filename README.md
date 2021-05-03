# Write Version to File

A GitHub Action that fetches the latest git tag within a repo and writes this to a file within the CI build container.
This can be than picked up by following build steps. The file is neighter commited nor pushed back to the branch.

## Fork info
This action was forked from https://github.com/brettdorrans/write-version-to-file and a change to the update logic of the file was made.

## Inputs

### `filename`

**Required** - The filename to write the version tag to. Default `VERSION`

## Example usage

```
name: Write Version to File
on:
  push:
    branches:
      - master

jobs:
  write-version:
    runs-on: ubuntu-latest
    name: Write Version to File
    steps:
    - uses: actions/checkout@master
    - name: Update version
      id: version
      uses: sebastian-muthwill/write-version-to-file@master
      with:
        filename: 'VERSION'
```
