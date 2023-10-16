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

