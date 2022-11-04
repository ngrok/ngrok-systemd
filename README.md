## SystemD Units

These systemd units are for use with the ngrok agent. There are two, one for running all tunnels in a configuration file and a second for running specific tunnels within a configuration file.

The ngrok agent ships with a basic systemd unit that is likely to work on a wide variety of systems and configurations. These units use additional configuration options for a higher level of security. __Caveat__: a future version of the ngrok agent may use syscalls or other system APIs blocked by these units and they will need to be updated accordingly.

### Installation

#### All tunnels unit
```
sudo cp <path>/ngrok.service /etc/systemd/system/ngrok.service
sudo systemctl daemon-reload
sudo systemctl enable ngrok
sudo systemctl start ngrok
```

#### Per-tunnel unit
```
sudo cp <path>/ngrok@.service /etc/systemd/system/ngrok@<tunnelname>.service
sudo systemctl daemon-reload
sudo systemctl enable ngrok@<tunnelname>
sudo systemctl start ngrok@<tunnelname>
# repeat for each tunnel you want to run
```
