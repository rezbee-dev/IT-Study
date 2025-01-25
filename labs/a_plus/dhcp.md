# DHCP

## Objective

Setup DCHP to allocate IP information to hosts

## Packet Tracer Setup

- Connect two PCs and one Server to a Switch
  - DHCP server: 192.168.1.1
- DHCP Values
  - Address start: 192.168.1.2
  - Subnet mask: 255.255.255.0
  - Pool name: DHCPLab


## Exercises

<details>
  <summary>1. Configure DHCP server with values listed above </summary>

  - Services > DHCP
  - Fill in the fields with the following:
    - Service: On
    - Pool Name: DHCPLab
    - Address start: 192.168.1.2
    - Subnet mask: 255.255.255.0
</details>

<details>
  <summary>2. Configure PC to obtain IP information via DHCP</summary>

  - Desktop > IP Configuration
  - Fill in the fields with the following:
    - IP Configuration: DHCP
</details>

<details>
  <summary>3. Confirm IP configuration has been applied via `ipconfig` command</summary>

  - Desktop > Command Prompt
  - Enter: `ipconfig`
  - Should see valid IP information
</details>