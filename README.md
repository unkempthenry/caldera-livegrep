# Caldera Livegrep

Deploy [livegrep](https://github.com/livegrep/livegrep) indexing for Caldera github repos.

There are a couple options: 

- see `docker-compose/` for docker
- see `kubernetes/` for K8s

## Notes

Unfortunately all the plugin repos are specified manually. E.g.

```
...
    command:
     - /livegrep/bin/livegrep-github-reindex
     - "-name=Caldera"
     # Core
     - -repo=mitre/caldera
     # Plugins
     - -repo=mitre/access
     - -repo=mitre/atomic
     - -repo=mitre/builder
     - -repo=mitre/compass
     - -repo=mitre/debrief
     - -repo=mitre/emu
     - -repo=mitre/fieldmanual
     - -repo=mitre/gameboard
     - -repo=mitre/human
     - -repo=mitre/manx
     - -repo=mitre/mock
     - -repo=mitre/response
     - -repo=mitre/sandcat
     - -repo=mitre/ssl
     - -repo=mitre/stockpile
     - -repo=mitre/training
...

```

Livegrep does [support](https://github.com/livegrep/livegrep/pull/225) indexing submodules,
though I haven't figured out how to pass the option from the 
`livegrep-github-reindex` plugin :thonking:. 