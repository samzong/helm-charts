Kubernetes Helm Charts for samzong's projects.

## Adding a Chart

1. Create `charts/<chart-name>/` using lowercase hyphenated names and copy in the Helm scaffold (`Chart.yaml`, `values.yaml`, `templates/`, `_helpers.tpl`, `README.md`).
2. Populate `Chart.yaml` with `version`, `appVersion`, and `maintainers`, then document configuration and sample overrides (store examples under `charts/<chart-name>/examples/`).
3. Validate locally: run `helm dependency update charts/<chart-name>`, `helm lint charts/<chart-name>`, and `helm template charts/<chart-name> --namespace demo` until clean.
4. Open a pull request describing the chart, attach command output, and ensure the `PR Chart Checks` workflow passes.

## CI/CD

The `PR Chart Checks` workflow automatically validates charts on pull requests:

- Runs `helm lint` on all changed charts
- Renders templates with `helm template` to catch syntax errors
- Validates Chart.yaml presence before processing
