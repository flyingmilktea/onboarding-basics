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

1. Install remote-ssh plugin

    search for this plugin name `ms-vscode-remote.remote-ssh`, press `install`

    ![image](https://user-images.githubusercontent.com/20808792/169720542-91b4c11a-7110-4c81-b89a-23ac6ae5ce74.png)

2. Connect to remote using remote-ssh plugin

    As you have already set ssh-config, login is simple

    - Press `ctrl+shift+P` and type `SSH`

    ![image](https://user-images.githubusercontent.com/20808792/169720752-ab955e77-3e36-4ae6-aded-4db099e8dcc4.png)

    - click `Remote-SSH: Connect to Host...` and type `fcai4`

    ![image](https://user-images.githubusercontent.com/20808792/169720789-da5d88fb-208d-47fc-94b8-fff946a01432.png)

    A new VSCode window should open.
    
    You should check that in this window
    - VSCode open file `ctrl+k ctrl+o` is showing files at remote, not your local machine
    - VSCode terminal `` ctrl+` `` at the remote machine
