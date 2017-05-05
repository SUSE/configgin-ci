# configgin-ci

The concourse build pipeline for the [configgin](https://github.com/hpcloud/configgin) repo.

Exposes the make targets:
- lint
- test
- dist

To set-pipeline, you must supply your own secrets.yaml.
You can simply `cp secrets.yaml.example secrets.yaml` and fill in the blanks.

Then (assuming your instance is called "lol") do a set-pipeline like this:

```bash
fly -t lol set-pipeline -p configgin-master -c configgin-master.yaml -l secrets.yaml
```
