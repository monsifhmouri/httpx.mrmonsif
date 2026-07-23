# httpx.mrmonsif 🕷️

![banner](https://img.shields.io/badge/HTTP--SCANNER-Made%20By%20MrMonsif-orange)  
**HTTP Security Scanner with Technology & WAF Detection**

## Overview

`httpx.mrmonsif` is a fast and advanced HTTP scanner built with Go, focused on red team operations, bug bounty, reconnaissance, and WAF fingerprinting.

-  Fast concurrent scanning
-  Automatic technology detection (`X-Powered-By`, `Server`, etc.)
-  WAF detection (Cloudflare, Akamai, etc.)
-  Colored output with filters
-  Detects suspicious behaviors (e.g., rate limits, blocked URLs)

---

##  Installation

### From Source (Go 1.19+ Required)

```bash
git clone https://github.com/monsifhmouri/httpx.mrmonsif.git
cd httpx.mrmonsif

# For Windows:
go build -o httpx.mrmonsif.exe main.go

# For Linux:
go build -o httpx.mrmonsif main.go
chmod +x httpx.mrmonsif
````

---

##  Usage

### On Windows

```bash
cat targets.txt | httpx.mrmonsif.exe -t 50 -tech -security
```

### On Linux

```bash
cat targets.txt | ./httpx.mrmonsif -t 50 -tech -security
# or
./httpx.mrmonsif -t 50 -tech -security < targets.txt
```

### Flags

| Flag        | Description                        |
| ----------- | ---------------------------------- |
| `-t`        | Threads count (default: 10)        |
| `-tech`     | Enable technology detection        |
| `-security` | Enable security header check       |
| `-v`        | Enable verbose mode (more details) |

---

## 📂 Example Output

```bash
[200] http://target.com [cloudflare] [Tech: WordPress, PHP] [Time: 212ms]
[403] https://api.vuln.com [akamai] [Tech: []] [Time: 321ms]
```

---

##  Structure

```bash
├── core/
│   ├── scanner.go       # Main scanner logic
│   ├── output.go        # Output formatter
│   └── headers.go       # Security header checks
├── pkg/
│   └── technologies/
│       └── detector.go  # Tech detector
├── main.go
├── go.mod
└── targets.txt
```

---

##  Author
![My Avatar](./my_avatar.jpg)
**Created by [MrMonsif](https://www.instagram.com/httpx.mrmonsif/)**

---
