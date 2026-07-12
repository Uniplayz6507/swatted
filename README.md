# SWATTED v2.2

Async cybersec toolkit — 62 modules across 6 categories.

```
                              ╔═╗
                             ╔╝ ╚╗
                             ╚╝ ╚╝
                             /| |\
                            / | | \
                           |  | |  |
                          /|  | |  |\
                         / |  | |  | \
                        |  |  | |  |  |
                       /|  |  | |  |  |\
                      / |  |  | |  |  | \
                     |  |  |  | |  |  |  |
                    /|  |  |  | |  |  |  |\
                   / |  |  |  | |  |  |  | \
                  |  |  |  |  | |  |  |  |  |
                 /|  |  |  |  | |  |  |  |  |\
                / |  |  |  |  | |  |  |  |  | \
               |  |  |  |  |  | |  |  |  |  |  |
              /| /| /| /| /| /| | |\ |\ |\ |\ |\
             / |/ |/ |/ |/ |/ | | | \| \| \| \| \
            |==|==|==|==|==|==|=|=|==|==|==|==|==|
             \  \  \  \  \  \ | | /  /  /  /  /  /
              \  \  \  \  \  \| |/  /  /  /  /  /
               \  \  \  \  \  | |  /  /  /  /  /
                \  \  \  \  \ | | /  /  /  /  /
                 \  \  \  \  \| |/  /  /  /  /
                  \  \  \  \  | |  /  /  /  /
                   \  \  \  \ | | /  /  /  /
                    \  \  \  \| |/  /  /  /
                     \  \  \  | |  /  /  /
                      \  \  \ | | /  /  /
                       \  \  \| |/  /  /
                        \  \  | |  /  /
                         \  \ | | /  /
                          \  \| |/  /
                           \  | |  /
                            \ | | /
                             \| |/
                              \|/
```

## requirements

- python 3.12 (required — bytecode is version-locked)
- aiohttp (`pip install aiohttp` or `uv run --with aiohttp`)
- optional system tools: `dig`, `whois`, `traceroute`

## install

```bash
# easiest — uv handles everything
uv run --with aiohttp python3.12 swatted.py

# or pip
pip install aiohttp
python3.12 swatted.py
```

system deps (optional — some modules use these):
```bash
# arch
pacman -S bind whois traceroute
# debian
apt install dnsutils whois traceroute
```

## run

```bash
uv run --with aiohttp python3.12 swatted.py
```

## modules (62)

| category | count | modules |
|----------|-------|---------|
| RECON | 11 | subdomain enum, DNS dump, zone transfer, WHOIS, geoip, reverse DNS, traceroute, MAC vendor, email security, wayback harvester, net info |
| SCAN | 18 | port scanner, ping sweep, header grab, dir brute, tech fingerprint, SSL cert, WAF detector, HTTP methods, robots.txt, status batch, favicon hash, cloud buckets, GraphQL, cookies, takeover check, JS extractor, link scanner, email harvester |
| EXPLOIT | 11 | security headers, CORS, clickjacking, SQLi probe, XSS arsenal, host header injection, open redirect, param reflection, rate limit, smuggling, cache deception |
| CRYPTO | 7 | hash gen, hash cracker, hash ID, HMAC, JWT decoder, password gen, password strength |
| UTILS | 7 | encode, decode, CIDR calc, IP info, Caesar cipher, UUID gen, UA dumper |
| PAYLOAD | 8 | command injection, LFI, SSRF, XXE, SQLi arsenal, reverse shells, web shells, race condition |

## commands

```
web <url>     full web audit (zero prompts)
full <domain> everything (recon + subdomains + web audit)
a             batch recon (dns + whois + geoip)
h             help
cls           clear screen
0 / q         quit
<number>      run that module
<keyword>     fuzzy-match module name
```

## features

- pulsing diamond banner with gradient SWATTED
- animated boot sequence (matrix rain, decrypt, glitch, scanline)
- bordered UI with color-coded categories
- fully async (aiohttp + asyncio)
- single file, zero config
