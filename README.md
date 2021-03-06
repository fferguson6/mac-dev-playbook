# Mac Development Ansible Playbook

This playbook installs and configures most of the software I use on my Mac for web and software development. Some things in macOS are difficult to automate (notably, the Mac App Store and certain tools from Apple), so I still have some manual installation steps, but at least it's all documented here.


*See also*:

  - [Battleschool](http://spencer.gibb.us/blog/2014/02/03/introducing-battleschool) is a more general solution than what I've built here. (It may be a better option if you don't want to fork this repo and hack it for your own workstation...).
  - [osxc](https://github.com/osxc) is another more general solution, set up so you can fork the [xc-custom](https://github.com/osxc/xc-custom) repo and get your own local environment bootstrapped quickly.
  - [MWGriffin/ansible-playbooks](https://github.com/MWGriffin/ansible-playbooks) was the original inspiration for this repository, but this project has since been completely rewritten.

## Installation

  1. [Install Ansible](http://docs.ansible.com/intro_installation.html).
  2. Ensure Apple's command line tools are installed (`xcode-select --install` to launch the installer).
  3. Clone this repository to your local drive.
  4. Run the command `$ ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
  5. Run `ansible-playbook main.yml -i inventory -u [username] -U [username] --ask-sudo-pass` from the same directory as this README file (substitute `[username]` for your macOS account username). Enter your account password when prompted.

My [dotfiles](https://github.com/jamesdmorgan/dotfiles) are also installed into the current user's home directory, including the `.osx` dotfile for configuring many aspects of macOS for better performance and ease of use.

Finally, there are a few other preferences and settings added on for various apps and services.

### Applications/packages to be added:

These are mostly direct download links, some are more difficult to install because of custom installers or other nonstandard install quirks:

  - [iShowU HD](http://downloads.shinywhitebox.com/iShowU_HD_Pro_2.3.7.dmg)

    git clone git://github.com/scrooloose/nerdtree.git


## Testing the Playbook

Many people have asked me if I often wipe my entire workstation and start from scratch just to test changes to the playbook. Nope! Instead, I posted instructions for how I build a [Mac OS X VirtualBox VM](https://github.com/geerlingguy/mac-osx-virtualbox-vm), on which I can continually run and re-run this playbook to test changes and make sure things work correctly.
