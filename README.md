# network

This role configures network settings on Linux hosts. Tested on Debian stretch,
your mileage may vary on other systems.

## Configuration options

Configuration occurs via a `network` dictionary in the host variables of the
host in question. For example

    network:
      iface:
        ip: 10.0.0.5/23       # required
        gateway: 10.0.0.4     # required

        dns: 10.0.0.3         # optional
        ip6: fec0::10/64      # optional

      bridge:
        parent: eth0          # required

        ip: 10.0.0.5/23       # optional
        gateway: 10.0.0.4     # optional
        dns: 10.0.0.3         # optional
        ip6: fec0::10/64      # optional

Currently, only simple interfaces (`inet` and `inet6`) are supported.
