# Database

Created database namespace for the following helm
couchdb for obsidian
cloudnative-pg
dragonfly is a redis database for authentik
pgadmin for management

## Couchdb
Will depend on longhorn
Build it own init db

```yaml
        initContainers:
          init-config:
            image:
              repository: public.ecr.aws/docker/library/busybox
              tag: latest
            command:
              - "sh"
              - "-c"
              - "cp /tmp/config/*.ini /opt/couchdb/etc/default.d/; ls -lrt /opt/couchdb/etc/default.d;"

```
With the following config map

```yaml
      config:
        type: configMap
        name: obsidian-couchdb-configmap
        advancedMounts:
          main:
            init-config:
              - path: /tmp/config
```

## cloudnative-pg

Need to init-db first by adding the following line in the helm

```yaml
    initdb:
      database: immich
      owner: immich
      postInitApplicationSQL:
        - CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
        - CREATE EXTENSION IF NOT EXISTS cube;
        - CREATE EXTENSION IF NOT EXISTS earthdistance;
        - CREATE EXTENSION IF NOT EXISTS vectors;
      secret:
        name: cloudnative-pg
```

Then you should able to just recover the cluster on next deployment

```yaml
  bootstrap:
    recovery:
      source: &previousCluster postgres16-immich-v2
  # Note: externalClusters is needed when recovering from an existing cnpg cluster
  externalClusters:
    - name: *previousCluster
      barmanObjectStore:
        <<: *barmanObjectStore
        serverName: *previousCluster

```
