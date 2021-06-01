# Helm Push

Push a chart to a ChartMuseum compatible repository with Helm v3.

## Usage
Using Token Auth:
```yaml
steps:
  - name: Push Helm Chart to ChartMuseum
    uses: datalbry/helm-push@v3
    with:
      access-token: ${{ secrets.HELM_API_KEY }}
      repository-url: 'https://h.cfcr.io/user_or_org/reponame'
      force: true
      chart-folder: chart
```

Using Password Auth:
```yaml
steps:
  - name: Push Helm Chart to ChartMuseum
    uses: datalbry/helm-push@v3
    with:
      username: ${{ secrets.HELM_USERNAME }}
      password: ${{ secrets.HELM_PASSWORD }}
      repository-url: 'https://h.cfcr.io/user_or_org/reponame'
      force: true
      chart-folder: chart
```

### Parameters

| Key | Value | Required | Default |
| ------------- | ------------- | ------------- | ------------- |
| `access-token` | API Token with Helm read/write permissions | **Yes** (if using token auth) | "" |
| `username` | Username for repository | **Yes** (if using pw auth) | "" |
| `password` | Password for repository | **Yes** (if using pw auth) | "" |
| `repository-url` | ChartMuseum repository url | **Yes** | "" |
| `chart-folder` | Relative path to chart folder to be published| No | chart |
| `force` | Force overwrite if version already exists | No | false |

## License

This project is distributed under the [MIT license](LICENSE.md).
