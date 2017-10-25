# qgis3-ci-copr

Build QGIS 3 nightly/weekly (wip)

## Infrastructure
```flat
buildbot
        |\
        | git + bash[1]                                |
        | |                                            |
        | DockerLatent[2] + cap-add=SYS_ADMIN[3]       |
        |  \                                           | CD
        |   mock - copr-cli                            |
        |   |                                          |
        |   COPR (build)                               |
        |  
        |\                                             | 
        | DockerLatent[2]                              |
        | \                                            |
        |  COPR (enable)                               | CI
        |  |                                           |                           
        |  dnf install                                 | 
```
[1] https://github.com/qgis/QGIS/pull/5333 and https://github.com/qgis/QGIS/pull/5275 <br>
[2] http://docs.buildbot.net/latest/manual/cfg-workers-docker.html <br>
[3] https://docker-py.readthedocs.io/en/1.10.4/hostconfig/