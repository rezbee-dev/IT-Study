# FTP Exercise

## Objective
Save the network configurations of a Cisco router onto a server

## Packet Tracer Setup
- Connect server and router together

## Exercise
<details>
  <summary>1. Configure IP address on Ethernet interface on router</summary>

  ```
  enable
  configure terminal
  interface gigabitethernet0/0
  ip address 192.168.1.1 255.255.255.0
  no shut
  ```
</details>

<details>
  <summary>2. Save current router configurations</summary>

  - Need to save the live configurations in order to populate config file (?)
  ```
  enable
  copy run start
  ```
</details>

<details>
  <summary>3. Configure IP address on server</summary>

  - Desktop > IP Configuration
  - Fill out the following fields:
    - IPv4 Address: 192.168.1.2
    - Subnet Mask: 255.255.255.0
    - Default Gateway: 192.168.1.1
</details>

<details>
  <summary>4. Confirm server can communicate with router</summary>

  - Ping the router from the server CLI: `ping 192.168.1.1`
</details>

<details>
  <summary>5. Setup FTP credentials</summary>

  - Services > FTP
  - Set the following:
    - Service: on
    - Username: router_config
    - password: 123
    - Write permissions: checked
</details>

<details>
  <summary>6. Add FTP credentials to router</summary>

  ```
  enable
  configure terminal
  ip ftp username router_config
  ip ftp password 123
  ```
</details>

<details>
  <summary>7. Transfer router configuration file to server via FTP</summary>

  ```
  enable
  copy startup-config ftp:
  192.168.1.2
  router_config_bk
  ```
</details>

<details>
  <summary>8. Confirm file is on server</summary>

  - Services > FTP
  - Should see the file in the window below
</details>
