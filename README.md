# Charts

A repository to hold all helm charts I have developed.
The helm repo is added using

```
helm repo add pymichaelb https://pymichaelb.github.io/charts/
```

and is served from the `pages` branch of this repository.

## Releasing new charts
1) Make all changes and merge into the `master` branch
2) Tag the head commit for the changes with format << CHARTNAME >>-<< VERSION>> e.g. rabbitmq-queue-management-0.1.0
3) Package the chart from chart directory (`helm dependency update && helm package .`)
4) Switch to `pages` branch and move package (.tgz) into root directory
5) Re-index using `helm repo index . --url https://pymichaelb.github.io/charts/`
6) Commit the new `index.yaml` file and the `.tgz` package
