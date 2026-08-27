# Snort IDS Lab

A hands-on Intrusion Detection System (IDS) lab using Snort to detect and monitor network traffic in a virtualized environment.

## Project Overview

This project demonstrates how Snort can be configured with custom detection rules to generate alerts for different types of network traffic.

The lab uses Ubuntu as the Snort IDS system and Windows as a testing machine.

## Lab Environment

| Component | Details |
|---|---|
| IDS | Snort |
| IDS OS | Ubuntu 22.04.5 LTS |
| Testing OS | Windows |
| Network Interface | ens33 |
| Ubuntu IP | 192.168.192.129 |
| Detection Type | Network traffic monitoring |

## Detection Rules

The project contains custom Snort rules for:

- ICMP
- FTP
- SSH
- HTTP

Example:

```text
alert icmp any any -> 192.168.192.129 any (msg:"ICMP Packet found"; sid:1000001; rev:1;)
alert tcp any any -> 192.168.192.129 21 (msg:"FTP Packet found"; sid:1000002; rev:1;)
alert tcp any any -> 192.168.192.129 22 (msg:"SSH Packet found"; sid:1000003; rev:1;)
alert tcp any any -> 192.168.192.129 80 (msg:"HTTP Packet found"; sid:1000004; rev:1;)

## Testing

Network connectivity was tested from Windows to the Ubuntu Snort machine.

### ICMP Test

```text
ping 192.168.192.129

The Windows machine successfully received replies from the Ubuntu system.

### FTP Test

```text
ftp 192.168.192.129

The FTP service responded successfully.

### SSH Test

```text
ssh ankit@192.168.192.129| IDS OS | Ubuntu 22.04.5 LTS |
| Testing OS | Windows |
| Network Interface | ens33 |
| Ubuntu IP | 192.168.192.129 |
| Detection Type | Network traffic monitoring |

## Detection Rules

The project contains custom Snort rules for:

- ICMP
- FTP
- SSH
- HTTP

Example:

```text
alert icmp any any -> 192.168.192.129 any (msg:"ICMP Packet found"; sid:1000001; rev:1;)
alert tcp any any -> 192.168.192.129 21 (msg:"FTP Packet found"; sid:1000002; rev:1;)
alert tcp any any -> 192.168.192.129 22 (msg:"SSH Packet found"; sid:1000003; rev:1;)
alert tcp any any -> 192.168.192.129 80 (msg:"HTTP Packet found"; sid:1000004; rev:1;)

```

## Testing

Network connectivity was tested from Windows to the Ubuntu Snort machine.

### ICMP Test

```text
ping 192.168.192.129
```

The Windows machine successfully received replies from the Ubuntu system.

### FTP Test

```text
ftp 192.168.192.129
```

The FTP service responded successfully.

### SSH Test

```text
ssh ankit@192.168.192.129
```

An SSH connection to the Ubuntu system was successfully established.

## Project Structure

```text
snort-ids-lab/
├── README.md
├── LICENSE
├── .gitignore
├── rules/
│   └── local.rules
├── screenshots/
├── evidence/
└── docs/
```

## Snort Configuration

Test the Snort configuration:

```bash
sudo snort -T -c /etc/snort/snort.conf
```

Run Snort:

```bash
sudo snort -A console -q -u snort -g snort -c /etc/snort/snort.conf -i ens33
```

## Learning Objectives

- Understand IDS concepts
- Configure Snort
- Create custom Snort rules
- Monitor network traffic
- Detect ICMP traffic
- Detect TCP traffic on common service ports
- Analyze IDS alerts
- Practice network security monitoring in a controlled lab

## Disclaimer

This project is intended for educational purposes and authorized laboratory environments only.

Do not use these techniques to monitor or test networks without proper authorization.

## License

This project is licensed under the MIT License.
