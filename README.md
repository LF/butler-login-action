# `butler` login action

Sets the `BUTLER_API_KEY` environment variable for use by `butler`.

## Usage

```yaml
name: my-workflow

on: push

jobs:
  login:
    runs-on: ubuntu-latest
    container: lfdev/butler:latest
    steps:
      - uses: LF/butler-login-action@v1
        with:
          credentials: ${{ secrets.BUTLER_API_KEY }}
```

The image [lfdev/butler](https://hub.docker.com/r/lfdev/butler) from Docker Hub is used in this example, but this action should work in other environments where `butler` reads the credentials from `BUTLER_API_KEY`.
