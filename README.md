# Local DNS Resolver

A lightweight DNS server implementation using Python socket programming for intercepting and resolving domain name queries.

## Features

- **UDP Socket Communication**: Handles DNS queries using UDP protocol
- **Domain Filtering**: Blocks access to specified domains with customizable blacklist
- **Local Caching**: Stores DNS records locally to reduce lookup latency for frequently accessed domains
- **Upstream Forwarding**: Forwards unresolved queries to upstream DNS servers (Google DNS: 8.8.8.8)

## Technical Implementation

- **Protocol**: DNS over UDP (Port 53)
- **Language**: Python 3
- **Core Libraries**: `socket`, `struct`
- **DNS Record Types**: Supports A records (IPv4 addresses)

## How to Run

### Prerequisites
- Python 3.x
- Administrator/root privileges (required for binding to port 53)

### Usage

**On Linux/macOS:**
```bash
sudo python3 dns_server.py
```

**On Windows (PowerShell as Administrator):**
```powershell
python dns_server.py
```

## Project Structure

```
DNS-Server/
├── dns_server.py          # Main DNS server implementation
├── report.md              # Detailed technical report
└── README.md              # This file
```

## Key Components

1. **Query Interception**: Listens on UDP port 53 for incoming DNS queries
2. **Domain Blacklist**: Blocks unwanted domains (e.g., ads, malicious sites)
3. **Cache Management**: Implements TTL-based caching for improved performance
4. **Response Construction**: Builds valid DNS response packets following RFC 1035

## Testing

Test the server using `nslookup` or `dig`:

```bash
# Test domain resolution
nslookup example.com 127.0.0.1

# Test blocked domain
nslookup blocked-site.com 127.0.0.1
```

## Course Information

- **Course**: ECE4016 - Computer Networks
- **Institution**: The Chinese University of Hong Kong, Shenzhen
- **Date**: Fall 2024

## License

This project is for educational purposes only.
