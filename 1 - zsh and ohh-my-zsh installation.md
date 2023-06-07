## Install Zsh and Oh My Zsh on Ubuntu

To install Zsh and Oh My Zsh on Ubuntu, you can follow these steps:

1. Open a terminal by pressing `Ctrl+Alt+T` or by searching for "Terminal" in the application launcher.

2. Update the package list by running the following command:
    ```shell
        sudo apt update
    ```

3. Install Zsh by running the following command:
    ```shell
        sudo apt install zsh
    ```
    You may be prompted to enter your password to authorize the installation.

4. After Zsh is installed, you can set it as your default shell by running the following command:
    ```shell
       chsh -s $(which zsh)
    ```
    You will need to enter your password again to make the change.

5. Close the current terminal session and open a new one to start using Zsh.

6. Now, let's install Oh My Zsh. You can install it by using either curl or wget. Choose one of the following options:

- Using curl:
  ```shell
  sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

- Using wget:
  ```shell
  sh -c "$(wget -O- https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

    The installation script will prompt you to continue. Type "y" and press Enter to proceed.

7. Once the installation is complete, your new Zsh configuration will be active. You can customize it by editing the `~/.zshrc` file.

That's it! You now have Zsh and Oh My Zsh installed on your Ubuntu system. Enjoy using your new shell!
