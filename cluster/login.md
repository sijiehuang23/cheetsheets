# Password less login

1. Open up local terminal and type
   ```bash
    cd ~/.ssh
   ```
2. Generate a public key 
   ```bash
    ssh-keygen -t rsa
   ```
3. Show the key in terminal 
    ```bash
    cat id_rsa.pub
    ```
    Copy the output. It'd be looking something like this
    ```bash
    ssh-rsa AAAAQABAAAB7TfohAm7VGj5n5qapD8DZX+lwFYlXQVufgodskvx/qNCXG81DN3PKpliWWB07PrcANRhSKkhFQHyL1XBQTWji0uvManq0AxQEzn1Z5C3prJIHcL3bmGzrvXgFK+BtdV9Wrd59/D6TiNpkrl7 your-local-ID@EN4147378IMAC.local
    ```
4. Login the cluster
    ```bash
    cd ~/.ssh/
    vi authorized_keys
    ```
    Paste the copied local key to the file and save.