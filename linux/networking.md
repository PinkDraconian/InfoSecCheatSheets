# Most used:
- Listen for pings: `tcpdump -i tun0 icmp and icmp[icmptype]=icmp-echo`

# TCPDump
- Listen for pings: `tcpdump -i tun0 icmp and icmp[icmptype]=icmp-echo`
- Show interfaces: `tcpdump -D`
- Listen on an interface: `sudo tcpdump -i <INTERFACE> -XA`
- Read data from pcap: `tcpdump -f <file.pcap> -XA host <IP> and port <PORT>`
- Writing data to pcap: `sudo tcpdump -i <INTERFACE> -w <file.pcap>``
