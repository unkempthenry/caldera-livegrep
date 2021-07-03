# Start With Docker Compose

```shell
docker-compose up -d
```

Note: this won't automatically update the index over time 
(new commits to the git repos won't be picked up).

To manually trigger the re-indexing:

```shell
docker-compose up -d livegrep-indexer
```