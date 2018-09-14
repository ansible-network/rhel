# Configure VPN routing as responder
The `cloud_vpn/configure_routing_responder` function will configure the routing where
a VPN as responder has been configured previously on RHEL/CentOS machines.
It is performed by calling the `cloud_vpn/configure_routing_responder` task from the role.
The task will process variables needed for routing configuration and apply it to the device.

Below is an example to configure routing on a RHEL/CentOS machine configured as responder,
where the responder is RHEL/CentOS.

```
- hosts: rhel

  tasks:
    - name: Configure responder routing
      include_role:
        name: ansible-network.rhel
        tasks_from: cloud_vpn/configure_routing_responder
      vars:
        cloud_vpn_responder_provider: rhel
        cloud_vpn_responder_cidr: 192.168.0.0/24
```

## Notes
None
