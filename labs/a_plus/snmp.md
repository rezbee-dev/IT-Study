# SNMP

## Objective

Setup SNMP and use the protocol to change the Router name

## Packet Tracer Setup

- Connect PC to Router
  - PC: 192.168.1.2
  - Router: 192.168.1.1
- SNMP Values
  - Community String: SNMPLab
  - Permissions: read-write
  - sysName (MIB): snmpLabRouter


## Exercises

<details>
  <summary>1. Configure router with SNMP using values listed above </summary>

  - IOS command: 
  ```
  enable
  configure terminal
  snmp-server community SNMPLab rw
  ```
</details>

<details>
  <summary>2. Set MIB Configuration on PC</summary>

  - PC > Desktop > MIB Browser > Advanced
  - Fill in the fields with the following:
    - Address: 192.168.1.1
    - Port: 161
    - Read Community: SNMPLab
    - Write Community: SNMPLab
</details>

<details>
  <summary>3. Change router name via SNMP and MIB</summary>

  - PC > Desktop > MIB Browser
  - Find `.sysName` in the MIBTree
    - MIB Tree > router_std MIBs > .iso > .org > .dod > .internet > .mgmt > .mib-2 > .system > .sysName
    - Select .sysName and press GO to see value (name of router should be the default Router)
    - Change router name
      - Set Operations to "Set"
      - "SNMP Set" window should pop-up
      - Change data-type to "OctetString"
      - Set value to "snmpLabRouter"
      - Press OK
      - Press GO
    - Confirm router name change via "GET" operation
  - Confirm router name change via router CLI
</details>