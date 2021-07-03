# Deploy to Kubernetes

```shell
kubectl deploy -f .
```

Re-indexing happens on a cronjob every 10 minutes.

## Gotchas

*Github API limits:*

You can try cranking the cronjob lower than 10 minutes, but github
may start to rate limit you.

*Broken until first cron runs:*

Nothing will work until the indexing runs once (10 minute intervals every hour).
You can try to manually trigger it:

```shell
kubectl create job --from=cronjob/livegrep-indexer indexer-manual
```

REF: https://www.craftypenguins.net/how-to-trigger-a-kubernetes-cronjob-manually/

*Search doesn't work immediately after deployment:*

Sometimes it takes a couple minutes after the first successful indexing for 
the communication between the front-end and backend to start up.