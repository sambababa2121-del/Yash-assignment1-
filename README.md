# Yash-assignment1-
The procedure involves safely scanning your authorized local network using Nmap to identify IPs, open ports, services, and OS details, saving outputs for analysis. Wireshark can capture supporting packets. Document risks and remediation, organize results in a GitHub repo with README and report, and ensure no sensitive data is exposed.
Got it — below is a clear, plain-language **description** of each part of the step-by-step procedure I gave earlier. I’ll explain *why* each step matters and *what you’ll get* from it.

# Description of the procedure

## ⚠️ Important safety & legal notes

A short explanation: scanning networks can disturb devices and is illegal if done without permission. This section tells you to only scan machines you own or have explicit authorization to test, and to avoid aggressive/exploitative tools. It prevents you from getting into legal trouble or causing outages.

## Prep — what you need

Why: make sure you have the right tools and accounts before you start.
What it lists: the target machine (on the same LAN), Nmap (scanner), optional Wireshark (packet capture), GitHub (to submit results), and a local folder to collect outputs. These items give you the environment to scan, analyze, document, and submit results.

## 1) Identify your local IP and network range

Why: you must know your device’s IP and subnet to target the correct network range.
What it does: shows commands (`ipconfig`, `ifconfig`, `ip addr`) to find your IPv4 address and subnet mask. From those you calculate the network (e.g., `192.168.1.0/24`) so you don’t accidentally scan the wrong network.

## 2) Install Nmap (quick)

Why: Nmap is the main tool used in the assignment.
What it does: tells you how to install Nmap on Windows, Linux, and macOS. With Nmap installed you can start discovering hosts and services.

## 3) Run a safe initial scan of the whole LAN (TCP SYN scan)

Why: to quickly discover which hosts are up and which ports are responding.
What it does: offers a common Nmap command (`-sS -T4`) to scan a `/24` network and save output. It explains options and gives a note about skipping host discovery (`-Pn`) if pings are blocked. This is your reconnaissance step — light and fast.

## 4) Save comprehensive results (all ports + versions) for a single host of interest

Why: once you find an interesting host, you want detailed information about it.
What it does: gives a heavier command (`-p- -sV -O`) to scan all ports, determine service versions, and try OS detection. It also explains `-oA` so you save outputs in multiple formats for later analysis. This step is deeper, slower, and provides the evidence needed for the report.

## 5) Use non-intrusive NSE scripts (optional, but be careful)

Why: Nmap’s scripting engine can gather extra harmless info (banners, default creds checks, etc.).
What it does: shows how to run safe scripts (`--script=banner`, `-sC`) and warns not to run intrusive or exploit scripts unless you have permission. Use these to enrich findings without breaking anything.

## 6) Capture packets with Wireshark while scanning (optional, useful for analysis)

Why: packet captures validate scanner findings and let you inspect the actual network traffic (handshakes, banners, anomalies).
What it does: tells you how to choose an interface, apply capture or display filters, run captures while scanning, and save `.pcapng`. Wireshark helps you show proof (screenshots, specific packet examples) in your report.

## 7) Document and analyze results

Why: raw scan outputs are not enough — analysis explains the implications.
What it does: tells you what to record for each host: IP/hostname, open ports, service versions, OS, packet-capture highlights, and a short risk assessment plus remediation suggestions. This turns your technical outputs into actionable findings.

## 8) What to include in your GitHub repo (folder structure & files)

Why: assignment requires submission — a clear repo makes it easy for reviewers to understand and reproduce your work.
What it does: suggests a logical project structure (README, scans, report, screenshots), explains the essential files to include, and notes a README should contain reproduction steps and warnings about authorization.

## 9) Example Git commands to create & push the repo

Why: gives the exact commands you need to create the repo locally and push it to GitHub.
What it does: lists `git init`, `git add`, `git commit`, `git remote add`, and `git push` commands so you can upload everything you collected and share the URL in the assignment form.

## 10) Short answers to the interview questions (use these when asked)

Why: the assignment likely includes interview-style questions; short, precise answers save time and prepare you for viva.
What it does: provides concise definitions and explanations for common concepts (open ports, SYN scan, risks, TCP vs UDP, securing ports, firewall role, port scanning purpose, and how Wireshark helps). Use these as scriptable answers.

## 11) Final checklist before submission

Why: a quick pre-submission checklist reduces the chance you forget an important file or step.
What it does: lists items to verify — raw outputs, pcap files, screenshots, the report, README, repository push, and that you filled the submission form.

# Quick advice / tone for writing the report

* Be factual and reproducible: include exact commands and dates/times for scans.
* Highlight only non-sensitive data in public repos — don’t upload credentials, private keys, or raw PCAPs that contain secrets. If a pcap contains credentials, redact or omit it.
* Use screenshots (Nmap output, Wireshark filters) to make findings easy to verify.

---
