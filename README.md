# Network-Scan-task
port scanning using Nmap
Task 1: Local Network Port Scan

Objective To discover open ports on devices within the local network using Nmap and understand the security implications of exposed services. This exercise builds basic network reconnaissance skills.

Tools Used -Nmap: For scanning the network and identifying open ports (Optional) Wireshark: For capturing and analyzing packets

Scan Findings The following ports were found to be open on one or more devices in the local network: •Port 135 (TCP) – Microsoft RPC •Port 139 (TCP) – NetBIOS Session Service •Port 445 (TCP) – Microsoft-DS / SMB

command Used

nmap -sS 192.168.1.0/24(target ip) -oN local_scan.txt

Explanation: -sS: Performs a stealth TCP SYN scan

192.168.1.0/24: Scans all IPs in your local subnet

-oN local_scan.txt: Saves output to a readable text file

Security Risks of Open Ports

Port 135 – Microsoft RPC Function: Handles remote procedure calls in Windows.

Risk: Can be exploited for remote code execution.

Mitigation: Block external access; allow only trusted hosts.

Port 139 – NetBIOS Session Service Function: Used for legacy file/printer sharing (NetBIOS).

Risk: Susceptible to information leakage, enumeration, and spoofing.

Mitigation: Disable NetBIOS over TCP/IP unless required.

Port 445 – Microsoft SMB Function: Used for file sharing in Windows environments.

Risk: Commonly exploited in ransomware attacks (e.g., WannaCry).

Mitigation: Block at firewall, patch systems regularly, disable SMBv1.

Security Recommendations Disable unnecessary services (especially on ports 139 and 445).

Apply OS and security patches.

Use host firewalls to restrict port access.

Monitor network traffic for unusual activity.
