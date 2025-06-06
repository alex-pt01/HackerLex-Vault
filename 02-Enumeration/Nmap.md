| Topic                  | Command / Description                                                                                     |
|------------------------|----------------------------------------------------------------------------------------------------------|
| **Basic Nmap Scan**    | `nmap IP` (default SYN scan)                                                                              |
| **Skip host discovery**| `-Pn` (skip ping)                                                                                         |
| **Scan all TCP ports** | `-p-` (scan all 65535 TCP ports) OR `--top-ports 65536`                                                  |
| **Fast scan**          | `-F` (scan 100 most common ports)                                                                         |
| **UDP scan**           | `-sU`                                                                                                     |
| **SYN scan (half-open)**| `-sS` (less detectable by IDS) e.g. `sudo nmap IP -sS`                                                   |
| **TCP handshake scan** | `-sT` e.g. `nmap IP -sT`                                                                                  |
| **Service/version info**| `-sV` (probe open ports to determine service/version)                                                    |
| **OS detection**       | `-O`                                                                                                      |
| **Script scan**        | `-sC`                                                                                                     |
| **Aggressive scan**    | `-A` (OS detection, version detection, script scanning)                                                  |
| **Timing templates**   | `-T0` paranoid (slow, IDS evasion)<br>`-T1` sneaky (slow, IDS evasion)<br>`-T2` polite (slow)<br>`-T3` normal (default)<br>`-T4` aggressive (fast)<br>`-T5` insane (very fast) |
| **Increase verbosity** | `-v`                                                                                                      |
| **Output formats**     | `-oN output.txt` (normal human-readable text)<br>`-oX output.xml` (XML format - important)<br>`-oG output.gnmap` (grepable text) |
| **Example command**    | `nmap -Pn -sS -sV -F -T4 $IP -oN output.txt`                                                             |
| **OS Fingerprinting examples** | `nmap -O -Pn IP`<br>`nmap -T4 -sS -sV -O --osscan-guess -p- $IP`<br>`nmap -T4 -sS -sV --version-intensity 8 -O --osscan-guess -p- $IP` |
| **Port state "filtered" meaning** | Target is up but port filtered by firewall                                                        |
| **Import Nmap scan to Metasploit (MSF)** | Run Nmap: `nmap -sV -Pn -oX myscan.xml IP` <br> In MSF console: `db_import myscan.xml` <br> `db_status` to check DB |
