# configgin-ci

The concourse build pipeline for the [configgin](https://github.com/SUSE/configgin) repo.

Exposes the make targets:
- lint
- test
- dist

To deploy the pipeline, run the `deploy` script.

For example, to deploy to the concourse target named "lol", run:

```bash
./deploy -t lol master
```
