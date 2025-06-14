# VM-NMAP
Virtual Machine Setup and Network Scanning

GOAL: The goal for this project was to understand and learn how-to install and set up a VirtualBox with Kali Linux and Execute a Network Scanning using 5 common Nmap scans along with explanations for the flags used in each:

1. To determine which hosts are up on a network
Command: Nmap -sP Command
![CommandNmap1](https://github.com/user-attachments/assets/260bfdf5-6fa5-4f35-9496-4134f573cb17)


Why It’s Used: This scan is primarily used to identify live hosts on a network without triggering a more intrusive port scan. It's often the first step to establish a baseline of active devices in an environment.

Information to Look For: List of live hosts.
Unexpected devices on the network (indicating unauthorized access or rogue devices).

2. Basic Port Scan
Command: nmap -p 80,443 [target IP]
Flag Explanation: The -p flag specifies which ports to scan (e.g., ports 80 and 443 for HTTP and HTTPS).

Why It’s Used: This scan targets specific ports to identify if common services, like web servers, are accessible on a host. This can reveal what services are running and whether these ports are unexpectedly open.

Information to Look For: 
  Open ports that indicate running services.
  Services that shouldn’t be accessible externally (e.g., database or management interfaces).

3.Service Version Detection
Command: nmap -sV [target IP]
Flag Explanation: The -sV flag attempts to detect the versions of services running on open ports.

Why It’s Used: Service version detection helps identify the exact version of software running on a target. This is essential for vulnerability assessment, as specific versions may have known vulnerabilities.

Information to Look For: 
  Service names and version numbers.
  Deprecated or vulnerable software versions.

4.Full TCP Scan
Command: nmap -sT [target IP]
Flag Explanation: The -sT flag initiates a full TCP connection scan, providing accurate results but is noisier.

Why It’s Used: A full TCP scan (also known as a connect scan) establishes a complete TCP handshake with each port, making it more reliable in detecting open services compared to a SYN scan.

Information to Look For:
  Comprehensive list of open ports and running services.
  High number of unexpected open ports.


5. Aggressive Scan
Command: nmap -A [target IP]
Flag Explanation: The -A flag enables aggressive scanning, combining multiple advanced scanning techniques into one command.

Techniques Included:
  -Operating System Detection (-O): Attempts to identify the OS of the target, providing insight into the system type and potential vulnerabilities.
  -Service Version Detection (-sV): Determines the versions of services running on open ports, useful for vulnerability identification.
  -Script Scanning (-sC): Runs a set of default Nmap Scripting Engine (NSE) scripts for vulnerability detection, like checking for misconfigurations or weak authentication.
  -Traceroute: Maps the network route to the target, useful for identifying intermediary devices and understanding the network topology.
  -Why It’s Used: This scan is ideal for gathering a comprehensive view of a target in one command, especially during a deep assessment or when facing time constraints.

Information to Look For:
  -Detailed service and version information.
  -Operating system and network layout.
  -Script output that highlights potential vulnerabilities.
