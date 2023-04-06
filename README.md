# mygit


Open the Terminal application on your Mac.

Check to see if you already have an existing SSH key by entering the following command in the Terminal:

ls -al ~/.ssh

If you see files with names like id_rsa or id_dsa and id_rsa.pub or id_dsa.pub, then you already have an SSH key pair. Skip to Step 6.

If you don't have an SSH key pair, generate one by entering the following command in the Terminal:

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

This will create a new SSH key pair with a 4096-bit RSA encryption and your email address as a comment.

When prompted, enter a filename to save the key pair. You can use the default filename (id_rsa) or specify a different name.

You will be prompted to enter a passphrase for the private key. This is an optional security measure, but it's highly recommended to use one. Make sure to remember this passphrase, as you will need it every time you use your SSH key.

Add your SSH key to the ssh-agent by entering the following command in the Terminal:

eval "$(ssh-agent -s)"

This will start the ssh-agent in the background.

Add your SSH private key to the ssh-agent by entering the following command in the Terminal:

ssh-add -K ~/.ssh/id_rsa

This will add the private key to the ssh-agent and store the passphrase in the macOS keychain.

Copy the SSH public key by entering the following command in the Terminal:

pbcopy < ~/.ssh/id_rsa.pub

This will copy the contents of your public key to the clipboard.

Go to your GitHub account settings and click on "SSH and GPG keys" in the left sidebar.

Click on "New SSH key".

Enter a title for your SSH key (e.g., "MacBook Pro").

Paste your SSH public key into the "Key" field.

Click on "Add SSH key".

You're now all set up to use SSH with GitHub on your Mac!
