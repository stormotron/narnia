Narnia Tunnel version 0.0.1
============================
Copyright (c) Netstorm, 2025

> So, do you want an encrypted Ethernet tunnel over ICMP without fragmentation? It's FREE!

Narnia program (Freeware) creates an encrypted tunnel (ChaCha20) via ICMP (ping) without fragmentation. That is, the TAP interface created by the tunnel will support any MTU - 1500 and even 9000 regardless of the transport layer, the packets are assembled by the tunnel itself.

| Parameter | Binary | Docker env | Mandatory | Default value |
| :-------- | :----- | :--------- | :-------- | :------------ |
| TAP interface name | -i  | INTERFACE | Yes | none |
| Remote IP address | -r  | REMOTE_IP | Yes | none |
| Secret password | -s | PASSWORD | Yes | none |
| MAC address for TAP | -m | MAC | No | random unicast |
| Keepalive, seconds | -k | KEEPALIVE | No | 5 |

Basic example:

```
# docker run --cap-add=NET_ADMIN --device /dev/net/tun:/dev/net/tun --net=host -e INTERFACE=nvpn -e REMOTE_IP=8.8.8.8 -e PASSWORD=MyKey --name narnia -d stormotron/narnia:latest
```

**Licensing**

The program is absolutely free and does not require any registration. The program is distributed only as binary files.

**Contacts**

Telegram: el_stormi
