# Section-containing: A Cisco style section matching tool

# Install
Copy "section-containing" file to the /usr/bin/ dir, or any other dir in your $PATH. Make sure the execute bit is set on the file

Currently no automated install option is provided.

## Usage examples
### Match router config
```
# cat ios.txt | section-containing "dhcp pool"
ip dhcp pool vlan1
   network 10.0.1.0 255.255.255.0
   default-router 10.0.1.1 
ip dhcp pool vlan2
   network 10.0.2.0 255.255.255.0
   default-router 10.0.2.1 
ip dhcp pool vlan3
   network 10.0.3.0 255.255.255.0
   default-router 10.0.3.1 
```

### Match YAML
```yaml
# cat docker-compose.yml  | section-containing web
  web:
    build: .
    ports:
      - "8000:5000"
    volumes:
      - .:/code
    environment:
      FLASK_DEBUG: "true"
```

### Match formatted json
```json
# cat config.json | section-containing "server"
    "server": {
        "port": 80,
        "auth": false,
        "trusted_domains": [
            "goverment-secrets.example.com",
            "docs.mkultra.com"
        ]
        },
```

