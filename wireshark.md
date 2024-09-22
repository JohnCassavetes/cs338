### Jeremy Gautama

# ===== DAYTIME =====
1. The three-way handshake:
    ```bash
    1	192.168.64.2	129.6.15.28	    TCP	    40610 → 13 [SYN] Seq=0 Win=32120 Len=0 MSS=1460 SACK_PERM TSval=1747383631 TSecr=0 WS=128
    2	129.6.15.28	    192.168.64.2	TCP	    13 → 40610 [SYN, ACK] Seq=0 Ack=1 Win=65535 Len=0 MSS=1382 WS=64 SACK_PERM
    3	192.168.64.2	129.6.15.28	    TCP	    40610 → 13 [ACK] Seq=1 Ack=1 Win=32128 Len=0
    ```
2. Destination Port: 40610

3. The client needs a port so that it can communicate with the endpoint of the network connection.

4. The frame that contains the actual date and time is the DAYTIME Response
    ```bash
    4	129.6.15.28	    192.168.64.2	DAYTIME	    DAYTIME Response
    ```
5. SYN is Synchronize: it initiates the connection for the three-way handshake. ACK is Acknowledgement: it acknowledges the transaction of the data or connection request.

6. The Daytime Server. This is because in 5, the server (port 13) sends a Finish Acknowledgement [FIN, ACK] to client (port 40610).
    ```bash
    5	129.6.15.28	    192.168.64.2	TCP		    13 → 40610 [FIN, ACK] Seq=52 Ack=1 Win=66368 Len=0
    ```

# ===== HTTP =====

1. There are 8 open TCP connections. I can tell by counting them after filtering with `tcp.flags.syn == 1`.

2. Yes. The homepage request was made by my Kali (192.168.64.2) to the host (172.233.221.124). Here's the frame below:

    ```bash
    28	192.168.64.2	172.233.221.124	HTTP	GET /index.html HTTP/1.1
    ```
    I found this by using the filter `http.request`.

3. Yes. The photograph request was made by my Kali (192.168.64.2) to the host (172.233.221.124). Here's the frame below:

    ```bash
    32	192.168.64.2	172.233.221.124	HTTP	GET /jeff-square-colorado.jpg HTTP/1.1
    ```
