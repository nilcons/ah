# Usecases

Isolating untrusted stuff from Google, Steam, Facebook, etc.

TCP dumping stuff on noisy desktops.

Debugging stuff that "tarbombs" your home directory on first run (e.g. bazel).

# Networking

    sudo iptables -I FORWARD -j ACCEPT -s 100.110.0.0/16
    sudo iptables -t nat -I POSTROUTING -j MASQUERADE -s 100.110.0.0/16

TODO: support multiple concurrent AH environments, by

  - allocating IPs in a 100.110/16 (via hashing based on the name),
  - bridging the veths together in a bridge on the host.

TODO: ipv6

# TODO

Configurable isolation per environment:

  - network isolation off
  - process isolation off (together with --mount-proc)
  - maybe: ipc isolation on (but that kills pulseaudio+x11 anyway)
