# Tor-EncryptedTraffic-dataset (ISCX-Tor2016)
To be sure about the quantity and diversity of this dataset, we defined a set of tasks to generate a representative dataset of real-world traffic. We created three users for the browser traffic collection and two users for the communication parts such as chat, mail, FTP, p2p, etc. For the non-Tor traffic we used previous benign traffic from our [**VPN Project**](https://github.com/ahlashkari/VPN-EncryptedTraffic-dataset) and for the Tor traffic we used 7 traffic categories:

Browsing: Under this label we have HTTP and HTTPS traffic generated by users while browsing (Firefox and Chrome).
Email: Traffic samples generated using a Thunderbird client, and Alice and Bob Gmail accounts. The clients were configured to deliver mail through SMTP/S, and receive it using POP3/SSL in one client and IMAP/SSL in the other.

Chat: The chat label identifies instant-messaging applications. Under this label we have Facebook and Hangouts via web browser, Skype, and IAM and ICQ using an application called pidgin.

Audio-Streaming: The streaming label identifies audio applications that require a continuous and steady stream of data. We captured traffic from Spotify.

Video-Streaming: The streaming label identifies video applications that require a continuous and steady stream of data. We captured traffic from YouTube (HTML5 and flash versions) and Vimeo services using Chrome and Firefox.

FTP: This label identifies traffic applications whose main purpose is to send or receive files and documents. For our dataset we captured Skype file transfers, FTP over SSH (SFTP) and FTP over SSL (FTPS) traffic sessions.

VoIP: The Voice over IP label groups all traffic generated by voice applications. Within this label we captured voice-calls using Facebook, Hangouts and Skype.

P2P: This label is used to identify file-sharing protocols like Bittorrent. To generate this traffic we downloaded different .torrent files from the Kali linux distribution and captured traffic sessions using the Vuze application. We also used different combinations of upload and download speeds.

# Capturing process and content
The traffic was captured using Wireshark and tcpdump, generating a total of 22GB of data. To facilitate the labeling process, as we explained in the related published paper, we captured the outgoing traffic at the workstation and the gateway simultaneously, collecting a set of pairs of .pcap files: one regular traffic pcap (workstation) and one Tor traffic pcap (gateway) file.

Later, we labelled the captured traffic in two steps. First, we processed the .pcap files captured at the workstation: we extracted the flows, and we confirmed that the majority of traffic flows were generated by application X (Skype, ftps, etc.), the object of the traffic capture. Then, we labelled all flows from the Tor .pcap file as X.

ISCXFlowMeter has been written in Java for reading the pcap files and create the csv file based on selected features. The UNB CIC Network Traffic (Tor-nonTor) dataset consists of labeled network traffic, including full packet in pcap format and csv (flows generated by ISCXFlowMeter) also are publicly available for researchers.

    Traffic: Content
    Web Browsing: Firefox and Chrome
    Email: SMPTS, POP3S and IMAPS
    Chat: ICQ, AIM, Skype, Facebook and Hangouts
    Streaming: Vimeo and Youtube
    File Transfer: Skype, FTP over SSH (SFTP) and FTP over SSL (FTPS) using Filezilla and an external service
    VoIP: Facebook, Skype and Hangouts voice calls
    P2P: uTorrent and Transmission (Bittorrent)

# License
The ISCXTor2016 dataset is publicly available for researchers. If you are using our dataset, you should cite our related research paper which outlining the details of the dataset and its underlying principles:

    Arash Habibi Lashkari, Gerard Draper-Gil, Mohammad Saiful Islam Mamun and Ali A. Ghorbani, "Characterization of Tor Traffic Using Time Based Features", In the proceeding of the 3rd International Conference on Information System Security and Privacy, SCITEPRESS, Porto, Portugal, 2017.

# Download Link
http://205.174.165.80/CICDataset/ISCX-Tor-NonTor-2017/
