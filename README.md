# docker-build-and-push-action

## How to use

```
jobs:
  docker-build-and-push:
    needs: release
    if: github.event_name == 'push'
    runs-on: ubuntu-latest

    steps:
      - name: Check-out
        uses: actions/checkout@v3
        with:
          ref: "master"
          fetch-depth: 1

      - name: Docker build and push
        uses: autonomous-testing/docker-build-and-push-action@v1
        with:
          GH_TOKEN: ${{secrets.GITHUB_TOKEN}}
```

## Inputs

See `action.yaml` for possible inputs.