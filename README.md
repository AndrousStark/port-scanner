# 🔍 Python Port Scanner

<div align="center">

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Network](https://img.shields.io/badge/Network-Security-green?style=for-the-badge&logo=wireshark)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

**A Fast and Efficient Network Port Scanner for Security Assessment**

*Discover Open Ports. Identify Vulnerabilities. Secure Networks.*

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Examples](#-examples) • [Documentation](#-documentation)

</div>

---

## 📋 Overview

**Python Port Scanner** is a lightweight, efficient network security tool designed to identify open ports on target systems. Built with Python's native socket library, this scanner provides a simple yet powerful solution for network reconnaissance, security auditing, and penetration testing.

Whether you're a security professional conducting authorized assessments, a system administrator monitoring your infrastructure, or a student learning about network security, this tool offers an intuitive command-line interface for comprehensive port scanning.

---

## ✨ Features

### 🎯 Core Capabilities

- **Multi-Target Scanning** - Scan multiple IP addresses simultaneously
- **Flexible Port Range** - Define custom port ranges (1-65535)
- **Fast Execution** - Efficient socket-based connectivity checks
- **Simple Interface** - User-friendly command-line prompts
- **Real-Time Results** - Instant feedback on open ports
- **Cross-Platform** - Works on Windows, Linux, and macOS

### 🔧 Technical Features

- **Socket Programming** - Native Python socket library for TCP connections
- **Timeout Management** - Configurable connection timeouts
- **Error Handling** - Graceful handling of connection failures
- **Clean Output** - Organized display of scan results
- **Lightweight** - No external dependencies required
- **Educational** - Well-commented code for learning purposes

---

## 🚀 Installation

### Prerequisites

- **Python 3.x** (3.6 or higher recommended)
- **socket library** (included with Python by default)

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/AndrousStark/port-scanner.git

# Navigate to directory
cd port-scanner

# Run the scanner
python port_scanner.py
```

### No Dependencies Required!

This port scanner uses only Python's built-in libraries, so there's no need to install additional packages. Just download and run!

---

## 📖 Usage

### Basic Usage

Simply run the script and follow the interactive prompts:

```bash
python port_scanner.py
```

### Interactive Prompts

#### 1. Enter Target(s)

You'll be prompted to enter one or more targets:

```
[*] Enter Targets To Scan (split them by ,): 
```

**Options:**
- **Single Target**: `192.168.1.1`
- **Multiple Targets**: `192.168.1.1, 10.0.0.1, 8.8.8.8`
- **Hostnames**: `example.com, google.com`
- **Mixed**: `192.168.1.1, example.com, 10.0.0.5`

#### 2. Enter Port Range

Specify how many ports to scan (starting from port 1):

```
[*] Enter How Many Ports You Want To Scan: 
```

**Examples:**
- `100` - Scans ports 1-100
- `1000` - Scans ports 1-1000
- `65535` - Scans all possible ports

---

## 💡 Examples

### Example 1: Single Target Scan

Scanning a single local server for common ports:

```bash
$ python port_scanner.py
[*] Enter Targets To Scan (split them by ,): 192.168.1.1
[*] Enter How Many Ports You Want To Scan: 1000

Scanning Target: 192.168.1.1
-----------------------------------------
[+] Port 22 is open   (SSH)
[+] Port 80 is open   (HTTP)
[+] Port 443 is open  (HTTPS)
[+] Port 3306 is open (MySQL)
-----------------------------------------
Scan Complete for 192.168.1.1
```

### Example 2: Multiple Target Scan

Scanning multiple servers simultaneously:

```bash
$ python port_scanner.py
[*] Enter Targets To Scan (split them by ,): 192.168.1.1, 192.168.1.5, 10.0.0.10
[*] Enter How Many Ports You Want To Scan: 500

Scanning Target: 192.168.1.1
-----------------------------------------
[+] Port 22 is open
[+] Port 80 is open
-----------------------------------------

Scanning Target: 192.168.1.5
-----------------------------------------
[+] Port 21 is open
[+] Port 22 is open
[+] Port 443 is open
-----------------------------------------

Scanning Target: 10.0.0.10
-----------------------------------------
[+] Port 3389 is open
-----------------------------------------
All Scans Complete!
```

### Example 3: Domain Name Scan

Scanning a website:

```bash
$ python port_scanner.py
[*] Enter Targets To Scan (split them by ,): google.com
[*] Enter How Many Ports You Want To Scan: 100

Scanning Target: google.com (142.250.185.46)
-----------------------------------------
[+] Port 80 is open
[+] Port 443 is open
-----------------------------------------
Scan Complete for google.com
```

---

## 🔍 How It Works

### Port Scanning Process

1. **Target Resolution** - Converts hostnames to IP addresses using DNS
2. **Socket Creation** - Creates TCP socket for each port
3. **Connection Attempt** - Tries to establish connection to target:port
4. **Status Check** - Determines if port is open or closed:
   - **Open Port**: Connection successful (returns 0)
   - **Closed Port**: Connection refused or timeout
5. **Result Display** - Shows open ports in real-time

### TCP Connection Method

The scanner uses TCP SYN scanning approach:

```
Client → [SYN] → Server (Port)
   ↓
Server → [SYN-ACK] → Client (Port Open)
   ↓
Client → [RST] → Server (Connection Closed)
```

If the server responds with SYN-ACK, the port is open. Otherwise, it's closed or filtered.

---

## 📊 Common Ports Reference

| Port | Service | Description |
|------|---------|-------------|
| 20-21 | FTP | File Transfer Protocol |
| 22 | SSH | Secure Shell |
| 23 | Telnet | Telnet Protocol |
| 25 | SMTP | Simple Mail Transfer Protocol |
| 53 | DNS | Domain Name System |
| 80 | HTTP | Hypertext Transfer Protocol |
| 110 | POP3 | Post Office Protocol |
| 143 | IMAP | Internet Message Access Protocol |
| 443 | HTTPS | HTTP Secure |
| 3306 | MySQL | MySQL Database |
| 3389 | RDP | Remote Desktop Protocol |
| 5432 | PostgreSQL | PostgreSQL Database |
| 8080 | HTTP-ALT | Alternative HTTP Port |

---

## 🎓 Use Cases

### 🛡️ Security Auditing
- Identify exposed services on network devices
- Verify firewall configurations
- Detect unauthorized open ports
- Assess network security posture

### 🔧 System Administration
- Monitor server port status
- Troubleshoot network connectivity
- Verify service availability
- Document network configurations

### 📚 Educational Purposes
- Learn Python socket programming
- Understand TCP/IP networking
- Practice network security concepts
- Study port scanning techniques

### 🕵️ Penetration Testing
- Reconnaissance phase of security assessments
- Service enumeration
- Attack surface mapping
- Vulnerability identification

---

## 🛠️ Technical Details

### Socket Programming

The scanner leverages Python's `socket` library:

```python
import socket

# Create TCP socket
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Set timeout to avoid hanging
sock.settimeout(1)

# Attempt connection
result = sock.connect_ex((target_ip, port))

# Check result
if result == 0:
    print(f"Port {port} is open")
```

### Connection States

- **connect_ex() = 0** → Port is open and accepting connections
- **connect_ex() ≠ 0** → Port is closed, filtered, or unreachable

### Performance Considerations

- **Timeout Settings**: Default 1 second per port
- **Sequential Scanning**: Scans ports one at a time
- **Network Latency**: Affects scan speed
- **Target Distance**: Remote hosts take longer

---

## ⚙️ Configuration

### Customizing the Scanner

You can modify the script to adjust:

1. **Timeout Duration**
```python
sock.settimeout(2)  # Increase to 2 seconds for slower networks
```

2. **Port Range**
```python
# Modify to scan specific ranges
for port in range(1, 1024):  # Scan well-known ports only
```

3. **Output Format**
```python
# Add more details to output
print(f"[+] Port {port} is OPEN - {get_service_name(port)}")
```

---

## 📈 Performance Tips

### Optimize Scan Speed

1. **Reduce Port Range**: Scan only necessary ports
2. **Adjust Timeout**: Lower timeout for faster networks
3. **Target Local Networks**: Scans complete faster on LANs
4. **Close Unnecessary Applications**: Free up system resources

### Common Port Ranges

- **Well-Known Ports**: 1-1023
- **Registered Ports**: 1024-49151
- **Dynamic Ports**: 49152-65535

---

## ⚠️ Legal and Ethical Usage

### ⚖️ Important Legal Notice

**This tool is intended for LEGAL and AUTHORIZED use only.**

### 🚨 Legal Requirements

- ✅ **Obtain Written Permission** - Always get authorization before scanning
- ✅ **Own Systems Only** - Only scan networks and systems you own
- ✅ **Compliance** - Follow local and international laws
- ✅ **Professional Use** - Use in authorized security assessments
- ✅ **Educational Context** - Use in controlled learning environments

### ❌ Illegal Activities

- ❌ **Unauthorized Scanning** - Scanning without permission is illegal
- ❌ **Network Intrusion** - Attempting to access secured systems
- ❌ **Malicious Intent** - Using for attacks or exploitation
- ❌ **Privacy Violation** - Scanning networks without authorization

### 📜 Legal Disclaimer

**The author and contributors are NOT responsible for:**
- Misuse of this tool
- Unauthorized network scanning
- Illegal activities performed with this software
- Any damages caused by improper use

**Users assume ALL responsibility and liability for their actions.**

---

## 🔒 Security & Privacy

### Scan Detection

Port scanning can be detected by:
- Intrusion Detection Systems (IDS)
- Firewall logs
- Network monitoring tools
- Security Information and Event Management (SIEM) systems

### Best Practices

1. **Authorization First** - Always obtain permission
2. **Rate Limiting** - Don't overwhelm target systems
3. **Logging** - Keep records of authorized scans
4. **Responsible Disclosure** - Report vulnerabilities properly
5. **Legal Compliance** - Follow applicable laws and regulations

---

## 🐛 Troubleshooting

### Common Issues

#### Connection Timeouts
**Problem**: Scans taking too long
**Solution**: Increase timeout value or scan fewer ports

#### Permission Denied
**Problem**: Cannot bind to low ports (<1024)
**Solution**: Run with appropriate permissions (sudo on Linux/Mac)

#### Network Unreachable
**Problem**: Cannot connect to target
**Solution**: Verify network connectivity and target IP

#### Hostname Resolution Failed
**Problem**: Cannot resolve domain names
**Solution**: Check DNS settings or use IP addresses directly

---

## 🚧 Limitations

### Current Limitations

- **No UDP Scanning** - Only TCP ports supported
- **Sequential Operation** - Scans one port at a time
- **Basic Output** - Simple text-based results
- **No Service Detection** - Doesn't identify running services
- **Limited Stealth** - Easily detectable by IDS/IPS

---

## 🗺️ Future Enhancements

### Planned Features

- [ ] **Multi-threading** - Scan multiple ports simultaneously
- [ ] **UDP Support** - Scan UDP ports
- [ ] **Service Detection** - Identify services on open ports
- [ ] **Output Formats** - JSON, XML, CSV export
- [ ] **Banner Grabbing** - Capture service banners
- [ ] **Stealth Mode** - SYN scanning and evasion techniques
- [ ] **Progress Bar** - Visual progress indicator
- [ ] **Logging** - Save results to files
- [ ] **Rate Limiting** - Control scan speed
- [ ] **Custom Port Ranges** - Specify exact port ranges

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the Repository**
2. **Create a Feature Branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit Changes** (`git commit -m 'Add AmazingFeature'`)
4. **Push to Branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Areas for Contribution

- Performance optimizations
- New features (threading, service detection)
- Bug fixes
- Documentation improvements
- Testing and QA

---

## 📚 Learning Resources

### Network Security
- [TCP/IP Protocol Suite](https://www.ietf.org/rfc/rfc793.txt)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [Nmap Documentation](https://nmap.org/book/man.html)

### Python Socket Programming
- [Python Socket Documentation](https://docs.python.org/3/library/socket.html)
- [Real Python - Socket Programming](https://realpython.com/python-sockets/)
- [Python Network Programming](https://www.oreilly.com/library/view/foundations-of-python/9781484243848/)

### Ethical Hacking
- [CEH (Certified Ethical Hacker)](https://www.eccouncil.org/programs/certified-ethical-hacker-ceh/)
- [OSCP (Offensive Security Certified Professional)](https://www.offensive-security.com/pwk-oscp/)
- [HackerOne Disclosure Guidelines](https://www.hackerone.com/disclosure-guidelines)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**MIT License Summary:**
- ✅ Commercial use
- ✅ Modification
- ✅ Distribution
- ✅ Private use

---

## 👨‍💻 Author

<div align="center">

**Aniruddh Atrey**

*Network Security Enthusiast & Python Developer*

[GitHub Profile](https://github.com/AndrousStark) • [Report Issues](https://github.com/AndrousStark/port-scanner/issues)

</div>

---

## 🙏 Acknowledgments

- Python Software Foundation for the excellent socket library
- The cybersecurity community for sharing knowledge
- Inspired by industry-standard tools like Nmap and Masscan
- All contributors and users of this project

---

## 📞 Support

- 📧 **Issues**: [GitHub Issues](https://github.com/AndrousStark/port-scanner/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/AndrousStark/port-scanner/discussions)
- 📖 **Documentation**: [Project Wiki](https://github.com/AndrousStark/port-scanner/wiki)

---

## 📊 Project Stats

<div align="center">

![GitHub stars](https://img.shields.io/github/stars/AndrousStark/port-scanner?style=social)
![GitHub forks](https://img.shields.io/github/forks/AndrousStark/port-scanner?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/AndrousStark/port-scanner?style=social)

</div>

---

## 🌟 Show Your Support

If you find this project useful, please consider:
- ⭐ **Starring** the repository
- 🍴 **Forking** for your own projects
- 📢 **Sharing** with others
- 🐛 **Reporting** bugs and issues
- 💡 **Suggesting** new features

---

<div align="center">

**Built with ❤️ for the Cybersecurity Community**

*Remember: With great power comes great responsibility. Use ethically!*

![Made with Python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)

</div>

---

## 🔐 Security Notice

**Found a security vulnerability?** Please report it privately rather than opening a public issue. Contact the maintainer directly through GitHub.

---

*Python Port Scanner - Simple, Fast, Effective Network Reconnaissance*

**Happy Scanning! 🚀**
