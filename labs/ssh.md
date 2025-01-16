# SSH Exercise

## Objective
Enable SSH access to a Cisco Router

## Packet Tracer Setup
- Connect PC with router
- IP Address: 192.168.1.0/24

## Exercises

<details>
  <summary>1. Configure hostname on router to R1</summary>

  ```
  enable
  configure terminal
  hostname R1
  ```
</details>

<details>
  <summary>2. Configure IP address on Ethernet interface on router</summary>

  ```
  enable
  configure terminal
  interface gigabitethernet0/0
  ip address 192.168.1.2 255.255.255.0
  no shut
  ```
</details>

<details>
  <summary>3. Configure IP address on PC</summary>

  - Config > Interface > Ethernet
  - Enter the following:
    - IP Address: 192.168.1.1
    - Subnet Mask: 255.255.255.0
</details>

<details>
  <summary>4. Confirm network communication via ping</summary>

  ```
  # Router to PC
  ping 192.168.1.1

  # PC to router
  ping 192.168.1.2
  ```
</details>

<details>
  <summary>5. Configure router to accept incoming SSH connections. Set options for 2 password attempts and 60 second timeout</summary>

  - Note
    - Need to enable SSH on a vty lines to allow for remote SSH connection
 
  ```
  enable
  configure terminal
  ip domain-name ssh-lab
  crypto key generate rsa
  1024
  ip ssh time-out 60
  ip ssh authentication-retries 2
  line vty 0 15
  transport input ssh
  password 123
  end
  show ip ssh
  ```
</details>

<details>
  <summary>6. Connect to router from PC via SSH</summary>

  ```
  ssh -l username 192.168.1.2
  ```
</details>

<details>
  <summary>7. Attempt to connect to router from PC via telnet and confirm it is denied</summary>

  - Should say its closed upon connecting
  ```
  telnet 192.168.1.2
  ```
</details>


