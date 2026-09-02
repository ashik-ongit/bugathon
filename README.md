cat << 'EOF' > README.md
# Los Pollos Hermanos University - CTF Challenge

Multi-tier web exploitation room designed for TryHackMe / Bugathon.

## Task 1: Level 0 — Reconnaissance & Credential Recovery
1. How many TCP ports are open on the target machine? (`2`)
2. What service is listening on port 80? (`http`)
3. What version of Apache HTTP Server is running on port 80? (`2.4.52`)
4. What hidden file lists search engine directives on the web root? (`robots.txt`)
5. Which internal directory is explicitly disallowed in robots.txt? (`/admin_backup/`)
6. What is the recovered staging email address found in the recon notes? (`student@lphu.edu`)
7. **Flag 0**: `{blue_stuff}`

## Task 2: Level 1 — Diagnostic Abuse & Remote Foothold
1. What internal diagnostic endpoint is revealed upon inspecting the network console? (`/faculty_diag.html`)
2. What error message is displayed when attempting to inject a basic space (` `) or semicolon (`;`)? (`WAF: Malicious Characters Detected! Forbidden tokens: [space], [;], [cat]`)
3. What internal Bash environment variable allows bypassing whitespace filtering? (`${IFS}`)
4. Which blacklisted standard file-reading binary triggers the filter when executed? (`cat`)
5. What hidden directory inside `/var/www` contains the staging flag artifact? (`.secret_core`)
6. What command alternative to `cat` can be used to read the protected file? (`tac`)
7. **Flag 1**: `{blue_stuff}`
EOF
