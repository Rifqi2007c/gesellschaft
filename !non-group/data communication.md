### component of data communication and fuction of each component
- #### message
	the information (data) to  be communicated. text, number, picture, sound, video, etc or combination
- #### sender
	the device that send the message. computer, workstation, telephone handset, video camera, etc
- #### reciever
	the device that recieve the message. computer, workstation, telephone handset, video camera, etc
- #### medium
	the physical path for the transmssion. copper wire, fiber-optic cable, lazer, radio waves, etc
- #### protocol
	the set of rule that govern data communication. agreement between the communication devices

### OSI layer and fuction of each layer
- #### layer 1: physical
	transmitting individual bits from one node to the next
- #### layer 2: data link
	transmitting individual fram frames one node to the next
- #### layer 3: network
	delivery of packet from the original source to the final destination
- #### layer 4: transport
	delivery of a message from one process to another
- #### layer 5: session
	maintain, establishes and synchonizes the interaction between communication system
- #### layer 6: presentation
	syntax and sematic of the information exchanged between two systems
- #### layer 7: aplication
	providing services to the user

### radio wave characteristics and aplication
- omni directional
- sender and reciever do not have to aligned (susceptible to interference)
- sky propagation
- can penetrate walls (low and medium frequencies)
- using omni directional antennas
#### aplication
- multicasting (one sender, many receivers)
	- such as AM and FM radio, television, maritime radio, cordless phone, paging

### Ipv4 convert binary to dotted-decimal

| bit position        | 8th | 7th | 6th | 5th | 4th | 3rd | 2nd | 1st |
| ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| value($n \times 2$) | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
example:
- 10000001 00001011 00001011 11101111
solution:
$$128+64+32+0+8+4+2+1=239$$
$$0+0+0+0+8+0+2+1=11$$
$$0+0+0+0+8+0+2+1=11$$
$$128+0+0+0+0+0+0+1=129$$
$$129.11.11.239$$
solution in table form (for easy tracking):

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | ans |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 1   | 0   | 1   | 1   | 1   | 1   | 239 |
| 0   | 0   | 0   | 0   | 1   | 0   | 1   | 1   | 11  |
| 0   | 0   | 0   | 0   | 1   | 0   | 1   | 1   | 11  |
| 1   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 129 |
ans= 129.11.11.239

### Ipv4 convert dotted-decimal to binary
example: 111.56.45.78
solution:
$$111 < 129=0$$
$$111 \underline >64=1,111-64=47$$
$$47 \underline > 32=1,47-32=15$$
$$15<16=0$$
$$15 \underline>8=1,15-8=7$$
$$7 \underline >4=1,7-4=3$$
$$3 \underline >2=1,3-2=1$$
$$1 \underline >1=1$$
$$111=01101111$$
do this for the rest

table form solution (for easy tracking)

| value/position | checking                        | ans |
| -------------- | ------------------------------- | --- |
| 128            | $111<128$                       | 0   |
| 64             | $111 \underline > 64,111-64=47$ | 1   |
| 32             | $47 \underline > 32,47-32=15$   | 1   |
| 16             | $15<16$                         | 0   |
| 8              | $15 \underline > 8,15-8=7$      | 1   |
| 4              | $7 \underline > 4,7-4=3$        | 1   |
| 2              | $3 \underline > 2,3-2=1$        | 1   |
| 1              | $1 \underline > 1$              | 1   |
ans= 111 = 01101111