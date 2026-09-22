packet analyzer. capture and display network traffic in real time on Unix-like operating systems. also can be use to read pcap file

### read .pcap file
```
tcpdump -r <input.pcap>
```
- `-r` option to input file
- other option
	- `-XX` view Link-Layer Header + Hex & ASCII
	- `-X` view Payload Only (Omits Link-Layer Header):