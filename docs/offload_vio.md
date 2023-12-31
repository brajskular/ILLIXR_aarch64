# Running ILLIXR With VIO Offloaded

In order to run the offloading plugins you need the following extra dependecies

```
sudo add-apt-repository ppa:ecal/ecal-latest
sudo apt-get update
sudo apt-get install ecal
sudo apt-get install libprotobuf-dev protobuf-compiler
```

The most simple example is running the offloaded setup on one machine with the server in one terminal
and the device running in a different terminal. **Each terminal must be running from separate ILLIXR 
repositories** (clone ILLIXR twice to different locations; running both the server and device from the same 
ILLIR repository will cause lock issues). 

Start ILLIXR using the runner with configs/offload-server.yaml
for one terminal and configs/offload-server.yaml on the other terminal. The default configuration within the
config files will run OpenVINS on the server and will feed it with the EuRoC dataset from the device.

To run more complicated experiment setups where the device and server are not on the same machine, you will need
to setup each machine to be able to send/recieve UDP multicasts, and configure your local network. A detailed 
guide on how to do this can be found [here][1]. Currently, this set of plugins only supports offloading within 
your local area network. This is due to a constraint of eCAL which doesnt support communication outside of the LAN.


[//]: # (- References -)

[1]:    https://continental.github.io/ecal/getting_started/cloud.html