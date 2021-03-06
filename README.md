# Split Path – JavaScript action

Takes a path and splits it at the last slash character, if any.

## Inputs

### `path`

**Required** The path to split.

## Outputs

### `dirname`

If there are any slashes in `path`, everything before the last slash; otherwise, the string `'.'`.

### `basename`

If there are any slashes in `path`, everything after the last slash; otherwise, all of `path`.

## Example usage

In this example we split the value of a variable provided by GitHub actions to obtain the plain name of the repo and the name of its owner (user or organization):

```yaml
  - id: split-repo
    uses: action-util/split-path@v1
    with:
      path: ${{ github.repository }}
```

Now `${{ steps.split-repo.outputs.basename }}` is the name of the repository, and `${{ steps.split-repo.outputs.dirname }}` is the name of its owner.
