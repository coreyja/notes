# nmap

#### Basic Usage

```bash
nmap $TIP
```

#### Do default script Scan

```bash
nmap -sC $TIP
```

#### Get the versions of services

```bash
nmap -sV $TIP

# We can also combine the above two
nmap -sC -sV $TIP
```

#### All Ports

```bash
nmap -p- $TIP

# -p is for port at - is an infinite range basically. You can also do things like
# -p 5-10
```
