# cdx - CDX Archive Search

[![Basher](https://img.shields.io/badge/basher-install-brightgreen)](https://github.com/basherpm/basher)

Query the Internet Archive's CDX API to search for historical web data and archived URLs.

## Features

- **Historical Search**: Find archived versions of websites
- **Flexible Filtering**: Filter by MIME type, date, and more
- **Multiple Output Formats**: JSON, CSV, or plain text
- **Archive URLs**: Get direct links to archived pages
- **Subdomain Support**: Search domain and all subdomains
- **Result Limiting**: Control the number of results returned

## Installation

### Using Basher

```bash
basher install gnomegl/cdx
```

### Manual Installation

```bash
git clone https://github.com/gnomegl/cdx.git
cd cdx
chmod +x cdx
# Add to PATH or copy to /usr/local/bin
```

## Usage

### Basic Usage

```bash
# Search for archived pages of a domain
cdx example.com

# Get archive URLs instead of original URLs
cdx -a example.com

# Search domain and all subdomains
cdx -c example.com
```

### Options

- `-a` - Show archive URLs instead of original URLs
- `-c` - Match domain and all subdomains (*.domain.com)
- `-d` - Show only the original URL
- `-f <type>` - Filter by MIME type (e.g., text/html, application/pdf)
- `-l <number>` - Limit number of results
- `-o <format>` - Output format: json, csv (default: text)

### Examples

```bash
# Find all archived pages with limit
cdx -l 50 example.com

# Search for PDF files only
cdx -f application/pdf example.com

# Get archive URLs for subdomains in JSON format
cdx -a -c -o json example.com

# Search for specific file types
cdx -f text/css example.com
```

## Output Formats

### Default (Text)
```
timestamp original_url mimetype statuscode digest
```

### Archive URLs (-a flag)
```
http://web.archive.org/web/20210101000000/http://example.com/
```

### JSON (-o json)
```json
[
  {
    "timestamp": "20210101000000",
    "original": "http://example.com/",
    "mimetype": "text/html",
    "statuscode": "200",
    "digest": "ABC123..."
  }
]
```

### CSV (-o csv)
Comma-separated values suitable for spreadsheet import.

## Common Use Cases

- **Security Research**: Find historical versions of websites
- **Digital Archaeology**: Discover old content and pages
- **Content Analysis**: Track changes over time
- **Backup Discovery**: Find archived versions of lost content
- **OSINT**: Gather intelligence from historical web data

## Requirements

- `curl` - For making HTTP requests to the CDX API

## CDX API Reference

This tool queries the Internet Archive's CDX Server API. For more information about the underlying API, visit:
https://github.com/internetarchive/wayback/tree/master/wayback-cdx-server

## License

MIT License
