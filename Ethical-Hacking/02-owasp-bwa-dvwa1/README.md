
# Lab 02 – OWASP BWA (DVWA)

## Objective

The objective of this lab was to practice identifying and exploiting common web application vulnerabilities using Damn Vulnerable Web Application (DVWA) inside the OWASP Broken Web Applications VM.

The focus areas were:

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection

All testing was performed in an isolated virtual lab environment.

---

## Lab Environment

| Component | Configuration |
|------------|---------------|
| Hypervisor | Oracle VirtualBox |
| Attacker | Kali Linux |
| Target | OWASP BWA (DVWA) |
| Target IP | 192.168.56.103 |
| Security Level | Low |

---

# 1️⃣ SQL Injection

### Vulnerable Page
DVWA → SQL Injection

### Payload Used

```sql
1' OR '1'='1
