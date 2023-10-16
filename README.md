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
#### Soal 1
Cari paket dengan HTTP method POST dengan filter `http.request.method == "POST"`
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/84badb28-b9d8-4d04-bded-d7f0b190657b)
Port `54478` dan IP Address `172.20.10.3`
### Soal 2
Untuk IP address `gaia.cs.umass.edu adalah` `128.119.245.12`

### Soal 3
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/0851ce47-153a-4fc8-ae78-02deddb76a79)
Sequence Number: 2903203422
SYN Flag: 0x002
SACK dapat digunakan di SYN Segment

### Soal 4
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/57a32fa6-6109-4998-ac07-3b19aa5d03ec)
Sequence Number: 1637555458
Acknowledgement: 1238883282
SYNACK Flag: 0x012
Acknowledgement Number adalah sequence number dari paket TCP berikutnya.

### Soal 5
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/9322d3bc-605f-483d-8077-024a038985db)
Sequence Number: 1239023989
alice.txt: 153028 bytes
Packet Payload: 12321 bytes
Ada 23 reassembled TCP Segments

### Soal 6
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/47cd7650-9c29-417d-ae80-170b302efe24)

- First segment was sent on the 5.093565s mark
- First ACK time: 5.095600s
- RTT First: 0.318125000s
- RTT ACK: 0.318125000s
- EstimatedRTT: 0.318125000s
### Soal 7
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/d3156c28-f42d-4c3c-944e-9271ecb0c088)
Length: 32 + 739 = 761
Length: 32 + 12622 = 12654
Length: 32 + 4222 = 4254
Length: 32 + 5622 = 5654

### Soal 8
Minimum: 131583

### Soal 9
Ada, retransmission segments bisa dicari lewat sequence number.

### Soal 10
![image](https://github.com/Mikask1/Wireshark_TCP_UDP/assets/88318140/1c27c141-7df3-4c62-a8ef-87ec5c770cd6)
The data varies from 707-11200 bytes.

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
