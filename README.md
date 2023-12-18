# Setup WSL

This guide assumes you have set up your computer for running WSL and have Ubuntu installed.

1. Set up ssh key file for github

    a. Create an ssh key file for github. When prompted for name call it github

       cd ~/.ssh
       ssh-keygen -t rsa -C "email"

    b. Create a `config` file

        touch ~/.ssh/config
        

    c. Put the following in your config file

       Host github.com
           IdentityFile ~/.ssh/github

    d. Set permissions

       chmod 700 ~/.ssh && chmod 644 ~/.ssh/config && chmod 600 ~/.ssh/github

2. Set up Linux Environment

    a. Install [Oh My Bash](https://github.com/ohmybash/oh-my-bash)

    b. Install [Python build dependencies](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)

3. Install Python

    a. Setup pyenv by first cloning it to your home directory

       git clone https://github.com/pyenv/pyenv.git $HOME/.pyenv

    b. Add pyenv to your PATH by copying this into your bashrc file.

       echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
       echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
       echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
    