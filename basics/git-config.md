# Using Github without password

In this tutorial, you will learn how to clone a repository from GitHub to a Linux server using SSH, set up an SSH key on GitHub so that you can push changes to the remote repository, and push changes from the local to the remote repository.

## A. Setting up the SSH Key

Before you can clone the repository, you need to set up an SSH key on your GitHub account.

1. On the Linux server, navigate to the `.ssh` directory by running the command `cd ~/.ssh`

2. Once in the `.ssh` directory, run `cat id_rsa.pub` to display your SSH key. The key should start with `ssh-rsa` and end with `=<your_email_address>`. 

3. Copy the entire public key string.

4. Log in to your GitHub account, go to **Settings > SSH and GPG keys**, and click on the green button labeled **New SSH key** in the upper-right corner. 

<img src="./img/ssh-add-key.png" width="600"/>

5. In the **Key** section, paste the SSH key that you copied earlier.

6. Give the key a title, such as **fcai**.

7. Click the **Add SSH key** button.

8. To test your SSH key, run `ssh -T git@github.com` on the Linux server. Type `yes` if prompted, and you should see the message
   
```bash
# Hi <your Github username>! You've successfully authenticated, but GitHub does not provide shell access." 
```

## B. Cloning the Repository via SSH

Once you have set up your SSH key, you can clone the repository to your local machine.

1. On the Linux server, navigate to the directory where you want to clone the repository. For example, you can run `cd ~/Documents` to navigate to your Documents directory.

2. Copy the SSH link for the repository that you want to clone. You can find this link by going to your repository on GitHub, clicking the **Code** button, and selecting the SSH option.

<img src="./img/git-page.png" width="600"/>

3. To clone the repository, run the following command: `git clone <repo-ssh-path>`.

4. If the repository has been cloned successfully, you'll see a new directory with the name of your repository.

## C. Pushing Changes to the Remote Repository

After cloning the repository, you can make changes to the files and push them to the remote repository.

1. On the Linux server, navigate to the repository directory by running `cd ~/Documents/<your_repository>`.

2. Create a new branch by running `git checkout -b <new-branch-name>`.

3. Make any changes to the files in the repository.

4. Add the changes to the local Git repository by running `git add .`.

5. Commit the changes by running `git commit -m "<commit message>"`.

6. Push the changes to the remote repository by running `git push origin -u <new-branch-name>`.

7. If the push was successful, you can go to the remote GitHub repository and see the changes you've made.

Congratulations! You have successfully learned how to clone repositories, set up SSH keys, and push changes to remote repositories using GitHub on a Linux machine.

If you are unsuccessful in any above steps, please ask for help.
