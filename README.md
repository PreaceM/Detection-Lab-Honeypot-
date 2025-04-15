# Detection Lab (Honeypot)
## Objective

The Honeypot Implementation project aimed to create a controlled environment for observing real-world cyber attacks by deploying and managing a Cowrie SSH/Telnet honeypot. The focus was on capturing and analyzing attacker behavior through log data, including brute-force attempts and command executions. This hands-on experience provided valuable insight into threat detection, common attack patterns, and the practical use of honeypots in cybersecurity research and intrusion detection.
## Skills Learned

<ul>
  <li><strong>Honeypot Deployment:</strong> Set up Cowrie (SSH/Telnet honeypot) to simulate vulnerable systems and capture attacker behavior.</li>
  <li><strong>Attack Analysis:</strong> Monitored brute-force attempts, command execution, and common attack patterns via honeypot logs.</li>
  <li><strong>Docker Proficiency:</strong> Deployed Cowrie in a Docker container with custom port mapping (2222:2222).</li>
  <li><strong>VM Networking:</strong> Configured inter-VM SSH communication using non-standard ports; tested root vs. non-root access.</li>
  <li><strong>SSH Security:</strong> Analyzed authentication behaviors and logged unauthorized login attempts for threat detection.</li>
  <li><strong>Linux Command Line:</strong> Executed commands to manage VMs, containers, and honeypot operations from terminal.</li>
  <li><strong>Log Analysis:</strong> Interpreted Cowrie logs to identify malicious activity and intrusion patterns.</li>
  <li><strong>Cybersecurity Insight:</strong> Gained hands-on experience in using honeypots for threat research and intrusion detection.</li>
</ul>

## Tools Used


#### Tools & Commands Used in Cowrie Honeypot Lab

- **Cowrie Honeypot** - Medium-interaction SSH/Telnet honeypot to log attacker behavior
- **Docker** - Containerization platform for deploying Cowrie
- **VirtualBox** - Hypervisor for managing Linux VMs
- **Linux Terminal** - Primary OS environment for configuration

#### SSH Testing & Attacks
- `ssh -p 2222 root@localhost` - Direct root login attempts
- `ssh -p 2222 localhost` - Non-root login tests
- `ssh -sV` - SSH version probing

#### Privilege Escalation
- `sudo su` - Gained root access for testing
- `whoami` - Verified user context

#### File System Navigation
- `ls` - Directory listing
- `cd ..` - Filesystem navigation

#### Network Tools
- `ifconfig` - Network interface checks
- `ip addr` - IP address verification

#### Log Analysis
- Cowrie logs - Attack monitoring
- `cat`/`grep`/`tail` - Log parsing
  
# Steps
## Honeypot Demo Video
<a href="https://youtu.be/MRZokWDKacI" target="_blank">
  <img src="https://img.youtube.com/vi/MRZokWDKacI/maxresdefault.jpg" 
       alt="Cowrie Honeypot Demo" 
       width="600" 
       style="border: 1px solid #24292e;">
</a>

*Ref 1: Video showing the honeypot implementation proccess.*
### Cowrie Honeypot Project Implementation

#### Implementation Steps

1. **Set Up Virtual Environment**
   - Created Linux VMs using VirtualBox
   - Configured network settings using `ifconfig`/`ip addr`

2. **Deploy Cowrie Honeypot**
   - Installed Docker on the host VM
   - Launched Cowrie container with port mapping `2222:2222`

3. **Test SSH Connections**
   - Attempted root access via `ssh -p 2222 root@localhost`
   - Tested non-root login with `ssh -p 2222 localhost`
   - Probed SSH version using `ssh -sV`
   
   > **Brute Force Testing**: Conducted password brute-force attempts against non-root accounts to test honeypot detection capabilities.

4. **Simulate Attacker Activity**
   - Executed basic commands (`ls`, `cd ..`)
   - Verified user context with `whoami`
   - Escalated privileges using `sudo su`

5. **Monitor & Analyze Results**
   - Reviewed Cowrie honeypot logs
   - Observed captured attacker behavior including brute-force attempts

> **Note**: This implementation focuses on core steps while maintaining security testing best practices. Brute-force testing was conducted in a controlled lab environment.

![Screenshot 2025-04-13 152333](https://github.com/user-attachments/assets/f74b2d0f-2551-4f6c-871a-98419e7a53fb)
*Ref 2: Login attempt where the attacker is being warned of a potential man-in-the-middle attack (on their end).*
