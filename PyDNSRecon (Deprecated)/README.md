# PyDNSRecon

A tool that collects DNS records from the 3 resources and tools that create unique findings

## Setup

Add your Censys.io censys API ID and secret to env variables

```bash
export censys_API_ID=<censys_API_ID>
export censys_secret=<censys_secret>
```

## Running with Docker (Local build)

Building Docker image

```
docker build -t pydnsrecon .
```

Running Docker container

```
docker run -e censys_API_ID=$censys_API_ID -e censys_secret=$censys_secret -it pydnsrecon <target>
```

Running PyDNSRecon and passing the censys api id and secret (Can be either strings or env variables)

## Running with Docker (Docker Hub)

```
docker run -e censys_API_ID=$censys_API_ID -e censys_secret=$censys_secret -it sneakerhax/pydnsrecon <target>
```

Start image pulled from Docker Hub and run PyDNSRecon

## Example usage

```
$ docker run -it pydnsrecon site.com
    ____        ____  _   _______ ____
   / __ \__  __/ __ \/ | / / ___// __ \___  _________  ____
  / /_/ / / / / / / /  |/ /\__ \/ /_/ / _ \/ ___/ __ \/ __ \
 / ____/ /_/ / /_/ / /|  /___/ / _, _/  __/ /__/ /_/ / / / /
/_/    \__, /_____/_/ |_//____/_/ |_|\___/\___/\____/_/ /_/
      /____/

by: sneakerhax

[+] Running Censys.io certificate search on site.com
[+] Running Amass on site.com
[+] Running Crt.sh search site.com
[+] Printing 5 discovered DNS records
dev.site.com
staging.site.com
admin.site.com
test.site.com
beta.site.com
```