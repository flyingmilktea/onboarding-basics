# Logging into Development Environment

You will be given

- A username, e.g. `YOUR_USER_NAME`
- A `.pem` ssh-key, e.g. `fcai-YOUR_USER_NAME.pem`
- A hostname, e.g. `192.168.50.204`

Your goal is to log into specified machine
1. using command-line
2. using SSH config file
3. using VSCode remote-ssh plugin

## Using command-line

You are going to make your first manual attempt to connect, if anything is not working, please talk to us.

1. Make sure you have SSH installed in your local machine

    SSH client should be pre-installed on MacOS and most Linux distro, for Windows, use WSL2 to install a Linux distro.

    ```bash
    ssh -V

    #> OpenSSH_8.0p1, OpenSSL 1.1.1g FIPS  21 Apr 2020
    # Any version should work
    ```

2. Move ssh-key into `~/.ssh` and set permission

    ```bash
    chmod 400 ~/.ssh/fcai-YOUR_USER_NAME.pem
    ```

3. Attempt to login using command line
   
    ```bash
    ssh -i ~/.ssh/fcai-YOUR_USER_NAME.pem YOUR_USER_NAME@192.168.50.204

    #> The authenticity of host '[192.168.50.204] ([192.168.50.204])' can't be established.
    #> ECDSA key fingerprint is SHA256:.....
    #> Are you sure you want to continue connecting (yes/no/[fingerprint])? 

    yes

    #> Warning: Permanently added '[192.168.50.204]' (ECDSA) to the list of known hosts.
    #> Last login: Mon May 23 06:55:19 2022 from 192.168.xxx.xxx
    #> [YOUR_USER_NAME@node4 ~]$ 
    ```

## Using SSH config file

You can create an alias for this set of ssh login configuration using ssh config file

1. Edit your ~/.ssh/config

    ```
    Host fcai4
        HostName 192.168.50.204
        IdentityFile ~/.ssh/fcai-YOUR_USER_NAME.pem
        User YOUR_USER_NAME
    ```

2. Attempt to login using the alias

    ```bash
    ssh fcai4

    #> Last login: Mon May 23 06:55:19 2022 from 192.168.xxx.xxx
    #> [YOUR_USER_NAME@node4 ~]$ 
    ```

## Using VSCode remote-ssh plugin

Remote-ssh plugin allows you to work at remote machine as if it is local, it handles most operations e.g. file, terminal, port forwarding automatically.

We assume you to already have VSCode installed.

### Install remote-ssh plugin

1. search for this plugin name `ms-vscode-remote.remote-ssh`
2. Press install

### Attempt to connect to remote

As you have already set ssh-config, login is simple

1. Press `ctrl+shift+P` and type `SSH`
2. click `Remote-SSH: Connect to Host...`
3. type `fcai4`

You should check that, now
- VSCode is showing files at remote, not your local machine
- Your terminal at the remote machine
