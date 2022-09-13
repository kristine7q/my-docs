# MAC SETUP

_Sep 2, 2022_ _BY KRISTINE_

> Reference: [swyx blog](https://www.swyx.io/new-mac-setup-2021), [robin blog](https://www.robinwieruch.de/mac-setup-web-development/)

## STEP 1 OS Settings

1. Dock
   1. Remove most application from the dock
   2. Middle size magnification and Smaller dock
   3. OFF "show recent applications in dock"
   4. ON "show indicators for open applications"
   5. OFF menu bar "Automatic hide desktop and full screen"
2. Battery
   1. ON "Show percentage"
3. Display
   1. Nightshift
4. Siri
   1. Disable
5. Trackpad
   1. Tap to click
   2. Tracking speed 9/10
6. Keyboard-Text
   1. disable "Capitalize word automatically"
   2. disable "Add full stop with double-space"
   3. disable "Use smart quotes and dashes"
   4. use " for double quotes
   5. use ' for single quotes
7. Spotlight
   1. Disable Spotlight except for Applications and System Preferences
8. Mission Control
   1. Hot Corners: disable all
9. Finder
   1. Sidebar on locations
   2. Hide all Tags
   3. Show all Filename Extensions
   4. Search the current folder
   5. view show tab/path/status bar
   6. Command + Shift + . (period) to make the hidden files appear.
10. Dictionary
    1. Add chinese simplified dictionary
    2. Delete wiki and apple dictionary
11. Sharing
    1. Change computer name
12. Terminal

    1. Change terminal user name

       ```shell
       sudo scutil --set ComputerName "newname"
       sudo scutil --set LocalHostName "newname"
       sudo scutil --set HostName "newname"
       ```

    2. Default show hidden files

       ```shell
       defaults write com.apple.finder AppleShowAllFiles YES
       ```

## STEP 2 Homebrew

Install [homebrew](https://brew.sh/) as package manager for macOS, paste that command line in the terminal. Remember to set `$PATH` in `.zprofile`

> Refer: [Install Homebrew](https://mac.install.guide/homebrew/3.html)

Install GUI applications:

```shell
brew install --cask \
iterm2 \
visual-studio-code \
sublime-text \
docker  \
discord \
figma \
imageoptim \
eul \
alfred \
google-drive
```

Install terminal applications :

```shell
brew install \
node \
wget \
exa \
git \
autojump \
nvm \
pnpm \
commitizen \
graphicsmagick
```

Install other apple apps: `xnip`, `google drive`

Install node app:

```shell
npm install -g typescript \
ts-node
```

## STEP 3 Set Iterm2 Terminal

1. Make iterm2 Default Term
2. Preference
   1. General ->
      1. Window
         1. unselect "Native full screen windows"
      2. Startup
         1. Use System Window Restoration Setting
         2. select "close windows when closing an app"
      3. Closing
         1. Unselect "Confirm 'Quit iTerm2'"
   2. Appearance
      1. Windows: select "Hide scrollbar"
      2. Tabs:
         1. unselect "Show tab bar in fullscreen"
         2. Select "flash tab bar when switching tabs in fullscreen"
         3. Dimming: Unselect all dimming
   3. Profiles -> window
      1. Transparency: 30
      2. Style: full screen
      3. Screen: main screen
   4. Profiles -> Advanced
      1. Semantic History -> Open with editor ... -> VS Code
   5. [Open new split pane with current directory](https://apple.stackexchange.com/questions/337377/iterm2-split-vertically-with-current-profile-with-same-working-directory/337386#337386)
   6. [Natural Text Editing](https://apple.stackexchange.com/questions/337377/iterm2-split-vertically-with-current-profile-with-same-working-directory/337386#337386)
3. Install [Oh-my-zsh](https://ohmyz.sh/#install)

   1. Homebrew Install [Starship](https://starship.rs/) as new terminal theme.

      ```shell
      brew install starship
      echo 'eval "$(starship init zsh)"' >> ~/.zshrc
      ```

   2. Install and use the new font in iTerm2: Preferences -> Profile -> Text -> Font: monoid-nerd-font.

      ```shell
      brew tap homebrew/cask-fonts
      brew install --cask font-monoid-nerd-font
      ```

   3. Download oh-my-zsh plugins, clone that git repo to default zsh directory, and set plugin in `.zshrc`

      - [zsh-completions](https://github.com/zsh-users/zsh-completions)
      - [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
      - [Zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

## STEP 4 Set VS Code

Download Extensions:

- Gitlens
- Auto Import
- Auto Close Tag
- Auto Close Tag
- EditorConfig
- eslint
- prettier
- Better Comments
- import cost
- Highlight Matching Tag
- color highlight
- ES7+ React/Redux/React-Native/JS snippets, react refactor
- vscode-styled-components
- color picker
- leetcode
- The Doki Theme
- background
- prettier-eslint
- Markdown Preview Enhanced
- markdownlint
- markdown all in one
- Code Spell Checker

JSON settings:

```json
{
  "security.workspace.trust.untrustedFiles": "open",
  "files.autoSave": "afterDelay",
  "files.trimTrailingWhitespace": true,
  "explorer.confirmDelete": false,
  "explorer.compactFolders": false,
  "workbench.startupEditor": "none",
  "workbench.statusBar.visible": true,
  "workbench.editor.enablePreview": false,
  "workbench.editor.restoreViewState": true,
  "terminal.integrated.fontFamily": "Monoid Nerd Font",
  "editor.fontFamily": "Monoid Nerd Font",
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": false,
  "editor.renderWhitespace": "none",
  "editor.scrollBeyondLastLine": true,
  "editor.minimap.enabled": false,
  "editor.find.seedSearchStringFromSelection": "selection",
  // syntax highlighting
  "files.associations": {
    ".env*": "makefile"
  },
  // prettier
  "prettier.singleQuote": true,
  "prettier.printWidth": 120,
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascriptreact]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  // eslint
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "eslint.validate": ["javascript"],
  "javascript.validate.enable": false,
  "javascript.updateImportsOnFileMove.enabled": "never",
  "typescript.updateImportsOnFileMove.enabled": "never",
  // auto generated
  "explorer.confirmDragAndDrop": false,
  "js/ts.implicitProjectConfig.checkJs": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "extensions.ignoreRecommendations": true,
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "workbench.colorTheme": "Bearded Theme Coffee Reversed",
  "[markdown]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "window.zoomLevel": -1
}
```

## STEP 5 Set Github

For terminals, set global name and email

```shell
git config --global user.name Kristine
git config --global user.email kristine.7q@gmail.com
```

Set SSH Keys for github

1. create a new SSH key in the `~/.ssh` folder:

   ```shell
   mkdir ~/.ssh
   cd ~/.ssh
   ssh-keygen -t ed25519 -C "github"
   # use file name: github
   # use passphrase
   ```

2. In your `~/.ssh/config` file, add the new SSH key, so that it can get picked up for every terminal session automatically:

   ```shell
   Host *
     AddKeysToAgent yes
     UseKeychain yes
     IdentityFile ~/.ssh/github
   ```

3. Add SSH key to MacOS' keychain:

   ```shell
   ssh-add --apple-use-keychain ~/.ssh/github
   ```

4. Add the public key to your GitHub settings via the website or via the GitHub CLI via

   ```shell
   # use GitHub's CLI
   brew install gh
   gh auth login
   ```
