# Logging into Development Environment

Welcome. Your first goal is to log into specified machine.

- [Logging into Development Environment](#logging-into-development-environment)
  - [Using command-line](#using-command-line)
  - [Using SSH config file](#using-ssh-config-file)

You will be given

- A username, e.g. `YOUR_USER_NAME`
- A `.pem` ssh-key, e.g. `fcai-YOUR_USER_NAME.pem`
- A hostname, e.g. `192.168.50.204`

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

1. Edit your `~/.ssh/config`

    ```text
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
