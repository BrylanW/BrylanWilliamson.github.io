Lab 05 – SSH Password Attack

## Objective

The objective of this lab was to demonstrate how weak credentials can allow attackers to gain unauthorized access to a system. In this lab, an SSH service running on Metasploitable2 was targeted using password attacks from Kali Linux.

---

## Lab Environment

| Component | Description |
|-----------|-------------|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Target IP | 192.168.56.101 |
| Network Type | VirtualBox Host-Only |

---

# 1. Verify SSH Service

First, the SSH service was verified using Nmap.

Command used:

# Lab 05 – SSH Password Attack

## Objective

The objective of this lab was to demonstrate how weak credentials can allow attackers to gain unauthorized access to a system. In this lab, an SSH service running on Metasploitable2 was targeted using password attacks from Kali Linux.

---

## Lab Environment

| Component | Description |
|-----------|-------------|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Target IP | 192.168.56.101 |
| Network Type | VirtualBox Host-Only |

---

# 1. Verify SSH Service

First, the SSH service was verified using Nmap.

Command used:
nmap -p 22 192.168.56.101


Purpose:

- Confirm that SSH is running on the target machine.

Screenshot:

![SSH Port Scan](screenshots/01-ssh-port-scan.png)

---

# 2. Test SSH Login

A manual SSH connection was attempted to confirm the service was reachable.

Command used:

ssh msfadmin@192.168.56.101


Result:

The system prompted for a password, confirming the SSH service was accessible.

Screenshot:

![SSH Login Test](screenshots/02-ssh-login-test.png)

---

# 3. Attempt Password Attack with Hydra

A password attack was attempted using Hydra.

Command used:
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.101


Purpose:

- Attempt to discover valid SSH credentials using a password list.

---

# Issue Encountered

Hydra failed to connect to the SSH service and returned the following error:

kex error: no match for method server host key algo

Explanation:

Metasploitable2 uses very old SSH encryption algorithms such as:
ssh-rsa
ssh-dss


Modern versions of Kali Linux disable these algorithms by default for security reasons, which prevents Hydra from establishing a connection.

---

# Workaround

Because Hydra could not negotiate the older SSH encryption methods, the brute-force attempt could not proceed normally.

To continue the lab and demonstrate weak credential exploitation, a manual SSH login was performed using known default credentials.

---

# 4. Successful SSH Login

Command used:

ssh msfadmin@192.168.56.101

password:
msfadmin

Verification command:
whoami

Result:
msfadmin

This confirmed successful authentication and remote access to the target system.

Screenshot:

![Successful SSH Login](screenshots/04-successful-ssh-login.png)

---

# Conclusion

This lab demonstrated how weak or default credentials can allow attackers to gain remote access to systems. It also highlighted how modern security configurations may prevent older tools or attacks from functioning due to deprecated encryption algorithms.

---

## Disclaimer

This lab was performed in a controlled virtual environment using intentionally vulnerable machines for educational purposes only.
