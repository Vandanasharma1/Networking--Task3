# Networking--Task3

project:
  title: Network Analysis Report
  environment: Windows
  tool_used: Command Prompt (CMD)
  user: Suresh

objective:
  description: >
    Analyze the network configuration of a Windows system using
    Command Prompt. The task includes IP configuration analysis,
    connectivity testing, DNS resolution, open port inspection,
    traceroute analysis, and network failure simulation.

system_details:
  operating_system: Windows
  interface_type: Wi-Fi / Ethernet
  shell: CMD

ip_configuration:
  command:
    - ipconfig /all
  observations:
    - System assigned a private IPv4 address (192.168.x.x)
    - Subnet mask defines the local network range
    - Default gateway configured for external communication
    - DNS servers are assigned
  conclusion: >
    The system has a valid IP configuration and is properly connected
    to the local network.

connectivity_test:
  commands:
    - ping 8.8.8.8
    - ping google.com
  observations:
    - Ping to public IP was successful
    - Ping to domain name was successful
    - No packet loss observed
  conclusion: >
    The system has stable internet connectivity and functional DNS.

dns_analysis:
  command:
    - nslookup google.com
  observations:
    - DNS server responded successfully
    - Domain name resolved to IP address
  conclusion: >
    DNS resolution is working correctly.

open_ports_and_services:
  commands:
    - netstat -ano
    - tasklist | findstr <PID>
  observations:
    - Multiple ports found in LISTENING and ESTABLISHED states
    - Each port is associated with a valid process ID
  conclusion: >
    Active network services are running and ports are used by
    legitimate applications.

traceroute_analysis:
  command:
    - tracert google.com
  observations:
    - Multiple hops observed between source and destination
    - Initial hops belong to local router and ISP
    - No abnormal delays detected
  conclusion: >
    Network routing is functioning correctly.

network_failure_simulation:
  steps:
    - Open network connections using ncpa.cpl
    - Disable active network adapter
    - Test connectivity using ping
    - Re-enable network adapter
  observations:
    - Ping failed when adapter was disabled
    - Ping succeeded after adapter was re-enabled
  conclusion: >
    System behaves correctly during network failure and recovery.

final_conclusion:
  summary: >
    The network analysis confirms that the system is correctly
    configured with valid IP addressing, stable connectivity,
    working DNS, normal routing behavior, and expected response
    to network failures.

key_learnings:
  - CMD provides essential tools for network troubleshooting
  - IP configuration, DNS, and connectivity are separate layers
  - Open ports should be monitored for security
  - Network failure simulation improves troubleshooting skills
