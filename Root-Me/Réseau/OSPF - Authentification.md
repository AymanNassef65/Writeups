**OSPF - Authentification** est une épreuve de sécurité réseau qui porte sur le protocole de routage OSPF (Open Shortest Path First).    
L'objectif est d'analyser une capture de trafic réseau dans le fichier .pcap par **Wireshark**, et on peut utiliser la commande **ettercap** pour extraire les hashs.   
```bash   
ettercap -Tqr ospf_authentication_hash.pcapng   ```
Puis on place le hash dans le fichier **hash.txt** comme ceci:    
```text    
OSPF-224.0.0.5-0$netmd5$0201003002020202000000000000000200000a103c7ec8a4fffffffc000a1201000000280c0000020c00000103030303$debe4e93b3ade8a8bc34302c192ced   ```
Enfin on utilise **John The Ripper** avec **rockyou.txt**:   
```bash   
john hash.txt --wordlist=rockyou.txt    ```
Et on trouve le flag.
