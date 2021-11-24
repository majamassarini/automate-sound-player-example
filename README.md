automate-home sound player example project
==========================================

An example project for the [automate-home project](https://github.com/majamassarini/automate-home).

A collection of files which define automation rules for one single **Appliance**.

- [sound.player.Appliance](https://automate-home.readthedocs.io/en/latest/appliances.html#sound-player-appliance)

This *Appliance* automates a **Sonos** device, through a *Performer*.

To automate the sound player two sensors, other than the buttons, are used:

- [sensor.luxmeter.Appliance](https://automate-home.readthedocs.io/en/latest/appliances.html#sensor-luxmeter-appliance); data come from a **KNX** sensor.
- [sensor.alarm.Appliance](https://automate-home.readthedocs.io/en/latest/appliances.html#sensor-alarm-appliance); data come from **KNX**.

## Project notes
  1. The buttons, in this project, have not an associated Appliance model, their *KNX* messages are directly delivered to the sound player Appliance through the *Performers*.  

## Run automate-home docker container using this project files

```shell
export AUTOMATE_HOME_CONFIGURATION=`pwd`
export NETWORK_NAME='qnet-static-eth0-a7611e'
export IP='172.31.10.247'

docker run -dit --privileged --name sound-player --network $NETWORK_NAME --ip $IP -p 81:81 -p 8181:8181 -v graphite-sound-player:/opt/graphite/storage -v redis-sound-player:/var/lib/redis -v "$AUTOMATE_HOME_CONFIGURATION:/etc/automate-home" -t majamassarini/automate-home:latest

docker exec -it sound-player /bin/bash
```

## UI

[GUI example](https://majamassarini.github.io/automate-sound-player-example/pages/172.31.10.247/index.html)
