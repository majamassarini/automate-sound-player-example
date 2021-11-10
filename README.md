Automate Home Sound Player example project
====================================

A collection of files which define automation rules for sound player **Appliance**.

Automated **Appliance**:

 - sound.player.Appliance

## Run Automate Home docker container using this project files

```shell
export AUTOMATE_HOME_CONFIGURATION=`pwd`
export NETWORK_NAME='qnet-static-eth0-a7611e'
export IP='172.31.10.247'

docker run -dit --privileged --name sound-player --network $NETWORK_NAME --ip $IP -p 81:81 -p 8181:8181 -v graphite-sound-player:/opt/graphite/storage -v redis-sound-player:/var/lib/redis -v "$AUTOMATE_HOME_CONFIGURATION:/etc/automate-home" -t automate-home/complete-node:latest

docker exec -it sound-player /bin/bash
```

## UI

[GUI example](https://majamassarini.github.io/automate-sound-player-example/pages/172.31.10.247/index.html)
