# Wireshark_TCP_UDP
## TCP
### 1. Capturing Packets
#### Steps:
1. Buka Wireshark
2. Pilih Interface (Wi-Fi, Ethernet, dll)
3. Pergi ke http://gaia.cs.umass.edu/wireshark-labs/alice.txt dan download alice.txt
4. Kemudian ke http://gaia.cs.umass.edu/wireshark-labs/TCP-wireshark-file1.html
5. Start capture
6. Lalu upload alice.txt dan upload filenya
7. Hasilnya seharusnya seperti berikut
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/095c4ce4-9ed3-4c84-814c-cbb3322ca25c)

### 2. Look at the captured trace
#### Steps:
1. Cari paket dengan HTTP method POST dengan filter `http.request.method == "POST"`
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/84badb28-b9d8-4d04-bded-d7f0b190657b)

3. Kemudian, kita bisa lihat bahwa POST request kita terbagi menjadi berbagai paket (dalam contoh 41 paket)
4. Dan, kita dapat mengamati three-way handshake TCP'
5. Lalu, dapat kita amati bahwa client mengirim request dari port 54478 dan IP Address `172.20.10.3`
6. Untuk IP address gaia.cs.umass.edu adalah `128.119.245.12`

### 3. TCP Basics
#### Steps:
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/7ca8928c-3400-4907-9da4-6a7f4cd03c32)
1. Dalam request, tidak terdapat SYN ACK, hanya ada FIN ACK
2. Akan tetapi, untuk melihat Sequence Number dan Acknowledgment Number di bagian TCP
3. Sequence Number dari paket POST adalah `2751537243`
4. Length of the first four payload: 761, 12654, 1454, 2854

### 4. TCP Congestion Control
#### Steps:
1. Untuk menganalisis data sent per unit time, kita dapat membuka Statistics
2. Kemudian, TCP Stream Graphs > Time Sequence (Stevens)
3. Kemudian di bagian bawah kanan, tekan `Switch Directions`
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/c4ef3529-0ab0-4779-a653-5c1d588792fa)

## UDP
- Kita akan menggunakan packet capture di bagian TCP di atas.
### Soal 1
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/c3c63f93-4229-43d5-b39c-f64aec21cdef)
Packet Number: 11
Protocol: UDP
Number of UDP Header Fields: 4 (Source Port, Destination Port, Length, Checksum)
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/33c21748-190d-4d2f-96de-36875a5e7b47)
### Soal 2
Source Port: 2 bytes (16 bits)
Destination Port: 2 bytes (16 bits)
Length: 2 bytes (16 bits)
Checksum: 2 bytes (16 bits)
### Soal 3
Field Length dalam UDP Header adalah panjang dari header + payload dari UDP packet.
### Soal 4
Maximum UDP Payload Length = 65535 byte (16-bit length field) - 8 byte (UDP header) = 65527 bytes
### Soal 5
Largest Port Number: 16 bit = 65535
### Soal 6
Protocol Number: 17
### Soal 7
Pada packet capture, tidak terdapat UDP packet yang saling reply, maka kita akan capture packet yang baru dengan mengcapture `nslookup` command.

![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/330e4dc0-afce-4b17-a398-874a48afc7cc)

Packet Number: 10 dan 11
Relationship: Sending Data diantara 172.20.10.3 dan 142.250.82.101
