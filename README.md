# hcf-configgin-ci

The concourse build pipeline for the [hcf-configgin](https://github.com/hpcloud/hcf-configgin) repo.

Exposes the make targets:
- lint
- test
- dist

To set-pipeline, you must supply your own secrets.yaml.
You can simply `cp secrets.yaml.example secrets.yaml` and fill in the blanks.

Then (assuming your instance is called "lol") do a set-pipeline like this:

```bash
# continuous integration of the `develop` branch
fly -t lol set-pipeline -p configgin-develop -c configgin-develop.yaml -l secrets.yaml
# continuous integration of the `master` branch
fly -t lol set-pipeline -p configgin-master -c configgin-master.yaml -l secrets.yaml
# continuous integration of pull requests
fly -t lol set-pipeline -p configgin-check-c configgin-check.yaml -l secrets.yaml
```
