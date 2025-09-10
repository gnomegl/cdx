# cdx

[![basher install](https://www.basher.it/assets/logo/basher_install.svg)](https://www.basher.it/package/)

internet archive cdx api search for historical web data

## install

```bash
basher install gnomegl/cdx
```

## usage

```bash
cdx example.com
```

search wayback machine captures and historical urls.

## options

- `--from` - start date (YYYYMMDD)
- `--to` - end date (YYYYMMDD)
- `--limit` - max results
- `--filter` - filter expression
- `-j, --json` - json output

## requirements

- curl
- jq