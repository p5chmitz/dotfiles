# About
Use this cheat sheet when setting up a new Linux install. Most instructions use the `apt` package manager for Debian (12). 

# Basic system function
    1. Set up your user as a sudoer
        1. su -
        2. sudo usermod -aG sudo <username>
        3. Reboot
    2. Install curl if not already: sudo apt install curl
        1. sudo apt install curl

# Software development environment(s)
    1. Install Rust
        1. Run the published curl/bash script
        2. Update Rust with rustup update
    2. Install terminal font The current Alacritty config in my dotfiles is configured for Hack by Nerd Fonts
        1. Download and extract the tarball from Nerd Fonts
        2. Extract and place the extracted folder into /usr/local/share/fonts/
    3. Install Alacritty You can either install Alacritty with Rust or build it from source
        1. cargo install alcaritty
        OR
        1. Clone the repo into a suitable directory
        2. Set Rust to a stable version and update it
        3. Install dependencies according to distro
        4. Build the program with cargo build —release
        5. Check for successful installation with infocmp alacritty
        6. Make a tray entry 
            1. Copy the program to /usr/local/bin
            2. Put the icon in /usr/share/pixmaps/ as Alacritty.svg
            3. Make a desktop entry as extra/linux/Alacritty.desktop
            4. Update the desktop DB
        7. Configure Alacritty with GH dotfiles member
    4. Configure Shell prompt with Starship
        1. Download/update Starship: curl -sS https://starship.rs/install.sh | sh
        2. Configure Starship with GH dotfiles member
    5. Set up Git SSH
        1. (See headyimage Git remotes workflow)
    6. Install Neovim
        1. Install base application from tarball
            1. Download the tarball
            2. Make sure you have a clean slate rm -rf /opt/nvim
            3. Extract the tarball into /opt/ sudo tar -C /opt -xzf nvim-{system}-{version}.tar.gz
            4. Add the extracted location to PATH in .bashrc (or similar) export PATH=“$PATH:/opt/nvim-{system}-{version}/bin”
            5. You may have to close your session or logout and log back in for changes to take
        2. Install package manager (Plug)
            1. Create a .config/nvim/autoload directory
            2. Create a .config/nvim/autoload/plug.vim file
            3. Download the plug.vim file from http://github.com/junegunn/vim-plug, place it in the plug.vim file, save and exit
        3. Configure Neovim
            1. Create a .config/nvim/init.vim file
            2. Place the contents of a pre-configured repo version that uses Plug or write your own
            3. Save and exit
        4. Set up LSPs
            1.	For Rust, install rust-analyzer:
                Assuming you already have a Neovim config/package manager set up for rust-analyzer, simply run rustup component add rust-analyzer and reboot your machine. If you get a LUA error, check for completion functionality in the init.vim script

# Vidya
    1. Install Steam
        1. Edit package list with: sudo nano /etc/apt/sources.list
        2. Add contrib to http://deb.debian.org line
        3. Enable multi-architecture setups with: sudo dpkg —add-architecture i386
        4. Install the Steam installer with: sudo apt install steam-installer
        5. Install additional Vulkan and 32-bit titles: sudo apt install mesa-vulkan-drivers libglx-mesa0:i386 mesa-vulkan-drivers:i386 libgl1-mesa-dri:i386
        6. Install by running: steam

# Photography
    1. Install Darktable

# General UX
1.	Configure navigation and keyboard settings
1.	Map caps lock to control with tweaks > Keyboard & Mouse > Additional Layout Options
2.	Map move workspace right and left with ctrl + l and ctrl + h respectively
3.	Set dark mode
4.	Install xcel (copying to clipboard)
2.	Desktop Only: Configure RGB elements with OpenRGB

