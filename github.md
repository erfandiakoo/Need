1. Setup `ssh` key on your pc (skip this step if you already have it)
    * Run this command with your email address instead of `your_email@example.com` .
    ```
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```
    * Start the ssh-agent in the background.
    ```
    eval "$(ssh-agent -s)"
    ```
    * Add your SSH private key to the ssh-agent and store your passphrase in the keychain.
    ```
    ssh-add -K ~/.ssh/id_rsa
    ```
    
2. Copy `ssh` key to clipboard
    * Run the command below to copy the ssh key to your clipboad
    ``` 
    pbcopy < ~/.ssh/id_rsa.pub 
    ```
3. Test github setup
     * Run the command below to terminal
     ```
     ssh -T git@github.com
     ```
