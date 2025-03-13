***
This is NOT an official Google product.
***

# Usecases

Isolating untrusted stuff from Google, Steam, Facebook, etc.

TCP dumping stuff on noisy desktops.

Debugging stuff that "tarbombs" your home directory on first run (e.g. bazel).

# Networking

    sudo sysctl -w net.ipv4.ip_forward=1
    sudo iptables -I FORWARD -j ACCEPT -s 100.110.0.0/16
    sudo iptables -t nat -I POSTROUTING -j MASQUERADE -s 100.110.0.0/16

# TODO

IPv6

IPv4 collision check

Configurable isolation per environment:

  - network isolation off
  - process isolation off (together with --mount-proc)
  - maybe: ipc isolation on (but that kills pulseaudio+x11 anyway)

when we are done: https://github.com/friz-zy/awesome-linux-containers

first we need a "definition of done"
