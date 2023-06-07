# Installing NVM in ubuntu

## To install NVM (Node Version Manager) on Ubuntu, you can follow these steps:




## Steps

### 1. Open a terminal on your Ubuntu system. (`Ctrl + Alt + T`)

### 2. Update the package lists for upgrades and new package installations:
   
   ```shell
   sudo apt update
   ```

### 3. Install the dependencies needed to build NVM and Node.js:
   
   ```shell
   sudo apt install build-essential libssl-dev
   ```

### 2. Download the NVM installation script using cURL:
   
   ```shell
   wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
   ```
   Alternatively, you can use wget to download the installation script:
   
   ```shell
   wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
   ```

### 3. The installation script will add the necessary NVM environment variables to your ~/.bashrc or ~/.bash_profile file. To apply these changes, run:


   ```shell
   source ~/.bashrc
   ```
   or
   ```shell
   source ~/.bash_profile
   ```
   ### if you are using `zsh` or `oh-my-zsh` shell.
   ```shell
   source ~/.zshrc
   ```


### 4. Verify that NVM is installed correctly by running:
   
   ```shell
   nvm --version
   ```
   It should display the version number of NVM.

### 5. Now, you can install the desired Node.js version using NVM. For example, to install the latest LTS version of Node.js, run:
   
   ```shell
   nvm install --lts
   ```

### 6. You can also install a specific version by specifying it instead of --lts. For example:
   
   ```shell
   nvm install 18
   ```

### 7. Once installed, you can set the default Node.js version to use:
   
   ```shell
   nvm alias default <version>
   ```

### 8. NVM commands 
    ```shell
        vijay@MSI:/mnt/c/Users/vijay$ nvm -v
            0.39.3

        vijay@MSI:/mnt/c/Users/vijay$ nvm list
            ->     v18.15.0
            default -> lts/* (-> v18.15.0)
            iojs -> N/A (default)
            unstable -> N/A (default)
            node -> stable (-> v18.15.0) (default)
            stable -> 18.15 (-> v18.15.0) (default)
            lts/* -> lts/hydrogen (-> v18.15.0)
            lts/argon -> v4.9.1 (-> N/A)
            lts/boron -> v6.17.1 (-> N/A)
            lts/carbon -> v8.17.0 (-> N/A)
            lts/dubnium -> v10.24.1 (-> N/A)
            lts/erbium -> v12.22.12 (-> N/A)
            lts/fermium -> v14.21.3 (-> N/A)
            lts/gallium -> v16.20.0 (-> N/A)
            lts/hydrogen -> v18.15.0
        
        vijay@MSI:/mnt/c/Users/vijay$ nvm use 18
            Now using node v18.15.0 (npm v9.5.0)
        
        vijay@MSI:/mnt/c/Users/vijay$ nvm alias default 18
            default -> 18 (-> v18.15.0)
        
    ```


    ### Official Docs - https://github.com/nvm-sh/nvm#installing-and-updating