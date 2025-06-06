## 🔍 Useful Google Dorks for Passive Reconnaissance

| Purpose                  | Dork Example                                                                 |
|--------------------------|------------------------------------------------------------------------------|
| **Sensitive Files**      | `site:example.com filetype:pdf`                                             |
|                          | `site:example.com filetype:xls OR xlsx`                                     |
|                          | `site:example.com filetype:txt`                                             |
|                          | `site:example.com filetype:sql`                                             |
|                          | `site:example.com filetype:env`                                             |
| **Keywords in Text**     | `site:example.com intext:"password"`                                        |
|                          | `site:example.com intext:"confidential"`                                    |
|                          | `inurl:login`                                                               |
|                          | `intitle:index.of`                                                          |
| **Public Code/Leaks**    | `site:github.com "example.com"`                                             |
|                          | `site:gitlab.com "example.com"`                                             |
|                          | `site:pastebin.com "example.com"`                                           |
| **Admin & Panels**       | `site:example.com intitle:"admin"`                                          |
|                          | `site:example.com inurl:"/admin"`                                           |
|                          | `site:example.com inurl:"/phpmyadmin"`                                      |
| **Exposed Directories**  | `intitle:"index of" "backup"`                                               |
|                          | `intitle:"index of" ".git"`                                                 |
|                          | `intitle:"index of" "config"`                                               |
| **Combined Search**      | `site:example.com filetype:pdf intext:confidential`                         |
| **Generic Leak Search**  | `inurl:wp-content/uploads filetype:sql`                                     |
