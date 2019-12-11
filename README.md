# tci-docker-cleanup

## About

A docker that runs a script, which acticates the following commands:

Clean exited processes:
```docker rm $(docker ps -q -f status=exited)```

Clean dangling volumes:
```docker volume rm $(docker volume ls -qf dangling=true)```

Clean dangling images:
```docker rmi $(docker images --filter "dangling=true" -q --no-trunc)```

System prune:
```docker system prune -a -f --volumes```

## How to use

All you need to do it run:
```docker run tikalci/tci-docker-cleanup```
