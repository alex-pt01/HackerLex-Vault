
> Passive Reconnaissance is the process of gathering information about a target without directly interacting with its systems.
Example: Checking DNS records, WHOIS data, public GitHub leaks, or using Google Dorks.



| Tool/Method                  | Command/URL                                                                                                           | Description                                                       |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **WHOIS**                    | `whois DOMAIN` / [who.is](https://who.is)                                                                             | Domain info: registrar, dates, name servers, privacy              |
| **DNS Lookup**               | `host DOMAIN`, `dig DOMAIN`, [dnsdumpster.com](https://dnsdumpster.com)                                               | DNS records: A, MX, NS, CNAME, PTR                                |
| **SSL Cert Search**          | [crt.sh](https://crt.sh)                                                                                              | Lists SSL certificates issued for a domain (including subdomains) |
| **Subdomain Enumeration**    | `sublist3r -d DOMAIN -e google,yahoo` <br> `amass enum -passive -d DOMAIN`                                            | Enumerates subdomains from public sources                         |
| **Email Harvesting**         | `theHarvester -d DOMAIN -b all`                                                                                       | Collects emails, names, IPs from public sources                   |
| **Google Dorking**           | See [GHDB](https://www.exploit-db.com/google-hacking-database)                                                        | Search for exposed files, directories, login portals, etc.        |
| **Site Technology**          | [Netcraft](https://sitereport.netcraft.com), [BuiltWith](https://builtwith.com), [Wappalyzer](https://wappalyzer.com) | Info about server, frameworks, front/back-end tech                |
| **Web Archives**             | [Wayback Machine](https://archive.org/web/)                                                                           | See older versions of the site                                    |
| **robots.txt / sitemap.xml** | `/robots.txt`, `/sitemap.xml`                                                                                         | List of disallowed/allowed indexed directories                    |
| **Pwned Emails**             | [haveibeenpwned.com](https://haveibeenpwned.com)                                                                      | Check if email/passwords were leaked                              |
| **HTTrack**                  | GUI / `webhttrack`                                                                                                    | Download the entire structure of a website                        |
| **VirusTotal**               | [virustotal.com](https://www.virustotal.com)                                                                          | Can reveal DNS history and subdomains                             |
