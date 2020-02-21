## How to Install Parity

To setup the Parity on a Ubuntu 18.04 server follow the steps:
- Copy files to server (i.e. SFTP via Filezilla)
    - config.toml
    - parity.service
    - setup.sh
- Run the below commands

```
chmod +x ./setup.sh

./setup.sh
```

While the setup script is running, it will attempt to install Rust and that will prompt user input. 
Enter "1" to Proceed with installation (default) - unless you have a specific need.

### Cheat Sheet: Parity Ethereum and Bitcoin Core: 
You can find some useful commands on the post below:

https://medium.com/@danielmontoyahd/cheat-sheet-parity-and-bitcoin-core-c370163fca44