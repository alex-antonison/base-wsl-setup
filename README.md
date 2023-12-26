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

2. Set up Linux Environment (you can see these in the [setup_linux.sh](./setup_linux.sh) file)

    a. Install [Oh My Bash](https://github.com/ohmybash/oh-my-bash)

    b. Install [Python build dependencies](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)

3. Install Python

    a. Setup pyenv by first cloning it to your home directory

       git clone https://github.com/pyenv/pyenv.git $HOME/.pyenv

    b. Add pyenv to your PATH by copying this into your bashrc file.

       echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
       echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
       echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
    
    c. With pyenv installed, you can then install the latest version of a specific version of Python with
      
       pyenv install 3.11

4. Setup [Serverless.com](https://www.serverless.com/)

   a. Install nvm (this will be used to install other packages)
    
       curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash

   b. You will need to source your `source .bashrc` file to get nvm added to your path

   c. Install node

       nvm install node

   d. Install Serverless

       npm install -g serverless


5. Setup [Docker](https://docs.docker.com/desktop/install/windows-install/)

    a. Follow instructions for installing Docker Desktop [Install Docker on Windows](https://docs.docker.com/desktop/install/windows-install/)

6. Setup [Terraform](https://www.terraform.io/)

    a. Clone [tfenv](https://github.com/tfutils/tfenv) whcih is a utility to install terraform

       git clone --depth=1 https://github.com/tfutils/tfenv.git ~/.tfenv
       echo 'export PATH="$HOME/.tfenv/bin:$PATH"' >> ~/.bashrc

    b. Source your .bashrc file `source .bashrc`
    c. Run `tfenv install 1.6.6` to install the 1.6.6 version of terraform
    d. Run `tfenv global 1.6.6` to set your global version of terrafrom to 1.6.6

7. Setup [awscli](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html) by running the [setup_aws_cli.sh](./setup_aws_cli.sh)
