# GitHub
GitHub, Inc. is a United States-based global company that provides hosting for software development version control using Git. In 2018, it became a subsidiary of Microsoft for US$7.5 billion. It offers the distributed version control and source code management functionality of Git, plus its own features.
>[!info] GitHub Folder Arrangments
> GitHub Login => GitHub Repo => GitHub Branch => files

# SSH key in GitHub
using the ssh protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.
You can access and write data in repositories on GitHub using SSH (Secure Shell Protocol). When you connect via SSH, you authenticate using a private key file on your local machine. For more information about SSH, see [Secure Shell](https://en.wikipedia.org/wiki/Secure_Shell) on Wikipedia.
## Using SSH agent forwarding
To simplify deploying to a server, you can set up SSH agent forwarding to securely use local SSH keys.

## Checking for existing SSH keys
- Before you generate an SSH key, you can check to see if you have any existing SSH keys.
- Before you generate a new SSH key, you should check your local machine for existing keys.
1. Open Terminal.
2. Enter `ls -al ~/.ssh` to see if existing SSH keys are present.
    ```shell
    $ ls -al ~/.ssh
    # Lists the files in your .ssh directory, if they exist
    ```
## Generating a new SSH key and adding it to the ssh-agent
After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.
1. Open Terminal.
    
2. Paste the text below, replacing the email used in the example with your GitHub email address.
    
    ```shell
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
    
    **Note:** If you are using a legacy system that doesn't support the Ed25519 algorithm, use:
    
    ```shell
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```
    
    This creates a new SSH key, using the provided email as a label.
    
    ```shell
    > Generating public/private ALGORITHM key pair.
    ```
    
    When you're prompted to "Enter a file in which to save the key", you can press **Enter** to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ALGORITHM with your custom key name.
    
    ```shell
    > Enter a file in which to save the key (/home/YOU/.ssh/id_ALGORITHM):[Press enter]
    ```
    
3. At the prompt, type a secure passphrase. For more information, see "[Working with SSH key passphrases](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases)."
    
    ```shell
    > Enter passphrase (empty for no passphrase): [Type a passphrase]
    > Enter same passphrase again: [Type passphrase again]
    ```
## Adding a new SSH key to your GitHub account
To configure your account on GitHub.com to use your new (or existing) SSH key, you'll also need to add the key to your account.
1. Copy the SSH public key to your clipboard.
    
    If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.
    
    ```shell
    $ cat ~/.ssh/id_ed25519.pub
    # Then select and copy the contents of the id_ed25519.pub file
    # displayed in the terminal to your clipboard
    ```
    
    **Tip:** Alternatively, you can locate the hidden `.ssh` folder, open the file in your favorite text editor, and copy it to your clipboard.
    
2. In the upper-right corner of any page on GitHub, click your profile photo, then click  **Settings**.
    
3. In the "Access" section of the sidebar, click  **SSH and GPG keys**.
    
4. Click **New SSH key** or **Add SSH key**.
    
5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".
    
6. Select the type of key, either authentication or signing. For more information about commit signing, see "[About commit signature verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)."
    
7. In the "Key" field, paste your public key.
    
8. Click **Add SSH key**.
## Changing a remote repository's url
[Changing a remote repository's URL](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#changing-a-remote-repositorys-url)

The `git remote set-url` command changes an existing remote repository URL.

>[!tip] Tip
>For information on the difference between HTTPS and SSH URLs, see "[About remote repositories](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories)."

## [Switching remote URLs from HTTPS to SSH](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh)

1. Open Terminal.
    
2. Change the current working directory to your local project.
    
3. List your existing remotes in order to get the name of the remote you want to change.
    
    ```shell
    $ git remote -v
    > origin  https://github.com/OWNER/REPOSITORY.git (fetch)
    > origin  https://github.com/OWNER/REPOSITORY.git (push)
    ```
    
4. Change your remote's URL from HTTPS to SSH with the `git remote set-url` command.
    
    ```shell
    git remote set-url origin git@github.com:OWNER/REPOSITORY.git
    ```
    
5. Verify that the remote URL has changed.
    
    ```shell
    $ git remote -v
    # Verify new remote URL
    > origin  git@github.com:OWNER/REPOSITORY.git (fetch)
    > origin  git@github.com:OWNER/REPOSITORY.git (push)
    ```