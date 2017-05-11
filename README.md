# configgin-ci

The concourse build pipeline for the [configgin](https://github.com/SUSE/configgin) repo.

Exposes the make targets:
- lint
- test
- dist

To set-pipeline, you must supply your own secrets.yaml. For deployment to production
you can use the credentials under blackbox control in the `SUSE/cloudfoundry` repo.

Then (assuming your instance is called "lol") do a set-pipeline like this:

```bash
fly -t lol set-pipeline -p configgin-master -c configgin-master.yaml \
    -l <(gpg -d --no-tty $HOME/hpcloud/cloudfoundry/secure/concourse-secrets.yml.gpg 2> /dev/null)
```
