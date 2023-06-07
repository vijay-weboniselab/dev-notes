# Change Theme of ZSH shell

## [Oh My Zsh Themes Directory](URL "https://github.com/ohmyzsh/ohmyzsh/wiki/Themes")

## You can follow these steps:

1. Open a terminal on your system. backup the .zshrc file.
   ```shell
   cp ~/.zshrc ~/.backup_zshrc
   ```

2. Locate the `~/.zshrc` file. This is the configuration file for Oh My Zsh. You can open it in a text editor using the following command:
   ```shell
   nano ~/.zshrc
   ```
   note: you can use any editor eg. gedit ~/.zshrc

3. Look for the line that sets the `ZSH_THEME` variable. It will look like this:
   ```shell
   ZSH_THEME="robbyrussell"
   ```

   The `ZSH_THEME` variable determines the currently active theme. In this example, the theme is set to `robbyrussell`. Note the name of the current theme, as you'll need it to revert back if desired.

4. To change the theme, you can assign a different theme name to the `ZSH_THEME` variable. Oh My Zsh provides a variety of themes to choose from. You can find the available themes in the `themes/` directory of the Oh My Zsh installation.

   You can browse the themes directory by running the following command:
   ```shell
   ls ~/.oh-my-zsh/themes/
   ```

   This will list all the available theme files. Each theme file has a `.zsh-theme` extension.

5. Choose the theme you want to use and modify the `ZSH_THEME` line in the `~/.zshrc` file accordingly. For example, to set the theme to `bira`, you would update the line as follows:
   ```shell
   ZSH_THEME="bira"
   ```
   you can get the theme names from [Oh My Zsh Themes Directory](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

6. Save the changes to the `~/.zshrc` file and close the text editor.

7. To apply the new theme, either restart your terminal or run the following command:
   ```shell
   source ~/.zshrc
   ```

   The new theme should now be applied to your Oh My Zsh shell.

8. To check and `download` all the available list of themes please visit [Oh My Zsh Themes Directory](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes):


Remember, if you want to revert back to the previous theme or choose a different theme in the future, you can follow the same steps and update the `ZSH_THEME` variable accordingly.