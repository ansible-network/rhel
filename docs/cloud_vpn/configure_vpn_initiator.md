# Configure VPN as initiator
The `cloud_vpn/configure_vpn_initiator` function will configure IPSEC VPN as initiator
on RHEL/CentOS machines.
It is performed by calling the `cloud_vpn/configure_vpn_initiator` task from the role.
The task will process variables needed for VPN configuration and apply it to the device.

Below is an example to configure an IPSEC VPN as initiator on RHEL/CentOS machines, where
the responder is RHEL/CentOS:

```
- hosts: rhel

  tasks:
    - name: Configure IPSEC VPN as initiator
      include_role:
        name: ansible-network.rhel
        tasks_from: cloud_vpn/configure_vpn_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_psk: mypsksecret
        cloud_vpn_initiator_provider: rhel
        cloud_vpn_initiator_outside_interface: eth0
        cloud_vpn_initiator_private_ip: 10.0.0.10
        cloud_vpn_initiator_tunnel_ip: 169.254.56.25
        cloud_vpn_responder_provider: rhel
        cloud_vpn_responder_public_ip: 18.191.132.220
```

## Notes
None
