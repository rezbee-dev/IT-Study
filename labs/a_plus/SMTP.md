# SMTP

## Objective

Enable SMTP on a small network

## Packet Tracer Setup

- Connect two PCs and two Servers to a Switch
  - Client #1: 192.168.1.3
  - Client #2: 192.168.1.4
  - Mail server: 192.168.1.2
  - DNS server: 192.168.1.5
- Setting values
  - name: pcX
  - email: pcX@smtplab.net
  - username: pcX
  - password: 123
  - mail server: smtplab.net


## Exercises

<details>
  <summary>1. Configure email client settings on both clients. </summary>

  - Desktop > Email
  - Fill in the fields with the following (PC1):
    - Your Name: pc1
    - email: pc1@smtplab.net
    - incoming mail server: pc1@smtplab.net
    - outgoing mail server: pc1@smtplab.net
    - username: pc1
    - password: 123
  - Do the same for PC2, except use "PC2"
</details>

<details>
  <summary>2. Setup SMTP server</summary>

  - Turn SMTP on, add domain name "smtplab.net", and add the 2 pcs
  - Services > Email
  - Fill in the fields with the following:
    - SMTP Service: On
    - POP3 Service: On
    - Domain Name: smtplab.net
    - User setup:
      - user: pc1, password: 123
      - user: pc2, password: 123
</details>

<details>
  <summary>3. Setup DNS server</summary>

  - Setup DNS server and add the "smtplab.net" domain name using A record
  - Services > DNS
  - Fill in the fields with the following:
    - DNS Service: On
    - Resource Records Type: A record
    - A Record:
      - Name: smtplab.net
      - IP Address: 192.168.1.2
</details>

<details>
  <summary>4. On client#1, send an email to client#2</summary>

  - Desktop > Email
  - Confirm by checking the inbox
</details>
