# qgis3-ci-copr

Build QGIS 3 nightly/weekly

## Infrastructure
```
buildbot
        \
         DockerLatent[1] + cap-add=SYS_ADMIN[2]
         \
          mock - copr-cli
          \
           COPR
```

[1] http://docs.buildbot.net/latest/manual/cfg-workers-docker.html <br>
[2] https://docker-py.readthedocs.io/en/1.10.4/hostconfig/