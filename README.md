# hcf-configgin-ci

The concourse build pipeline for the [hcf-configgin](https://github.com/hpcloud/hcf-configgin) repo.

Exposes the make targets:
- lint
- test
- dist

To set-pipeline, you must supply your own values for the following:
- `swift-access-key`
- `swift-secret-key`
- `swift-tenant-id`
- `git-private-key`

You can simply `cp secrets.yaml.example secrets.yaml` and fill in the blanks.

Then (assuming your instance is called "lol") do a set-pipeline like this:

```bash
fly -t lol set-pipeline -p configgin-develop -c configgin-develop.yaml -l secrets.yaml
fly -t lol set-pipeline -p configgin-master -c configgin-master.yaml -l secrets.yaml
```
