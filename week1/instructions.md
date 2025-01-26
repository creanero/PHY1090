# Activity for Topic 1: Introduction to the Course 

## Part 1: Accessing HPC Resources

### If you are unfamiliar with using the command line

Complete the “*using Linux*” exercises in the “*Additional Resources*” section of the course and return here.

### Access the Command Line on your local computer:

Open Terminal (Mac/Linux) or PowerShell (Windows)

### Connect with the portal computer Frank

Enter the following command in the terminal on your own computer. Replace `[username]` with the username you were given by Ray Murphy.

```
ssh -X [username]@www.physics.dcu.ie
```

Enter the password you were given by Ray Murphy when prompted. This will not be the same as the password you use for your DCU account.

### Connect to the HPC Cluster Cheetah.

Enter the following command. Replace [username] with the username you were given by Ray Murphy.

```
ssh -X [username]@cheetah.physics.dcu.ie
```

Enter the password you were given by Ray Murphy when prompted. This will not be the same as the password you use for your DCU account.

### Check you have access to the MPI commands.

Enter the following command.  This will show you where the `mpicc` compiler is located, and demonstrate that you have access to it.

```
which mpicc
```

You should see `/usr/bin/mpicc` as a response.

Enter the following command.  This will show you where the `mpiexec` runtime is located, and demonstrate that you have access to it.

```
which mpiexec
```

You should see `/usr/bin/mpiexec` as a response
 
## Part 2: Accessing GitHub

### If you are unfamiliar with using GitHub

Complete the “*Git for Physicists*” exercises in the “*Additional Resources*” section of the course and return here.

### Create a github repository for your code
Use a web browser and go to [github.com](https://github.com/). If needed log in using your credentials.

Use the web interface to create a new repository for this module called `HPQC`.  

Switch to the terminal screen where you’re logged in to `cheetah` from above.

Make a new directory for your repo and switch to it with the following commands:

```
mkdir HPQC
cd HPQC
```

Then, follow the instructions on the web browser under the heading “*…or create a new repository on the command line*”.

### Using the repository
You will use this directory for code exercises in this module.  You should make a separate subdirectory each week by using the `mkdir` and `cd` commands shown above
You should keep this directory synchronised with github by frequently using the git commands

```
git add [changed file]
git commit -m "A meaningful commit message"
git push
```

### Accessing the github demonstration materials

Return to your home directory by entering the following command

```
cd ~
```

Clone my repository by using git clone as below

```
git clone https://github.com/creanero/PHY1090
```

## Part 3: Configure your GitHub Security
### Set up SSH security for cheetah
The following instructions are taken from this [github tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

In the Cheetah Terminal Window, Paste the text below, replacing the email used in the example with your GitHub email address.

```
ssh-keygen -t ed25519 -C your_email@example.com
```

When you're prompted to "`Enter a file in which to save the key`", press *Enter* to accept the default file location. At the prompt, type a secure passphrase.

Enter the following command to start the SSH Agent.

```
eval "$(ssh-agent -s)"
```

Add your SSH private key to the ssh-agent.

```
ssh-add ~/.ssh/id_ed25519
```

### Link the SSH key to your GitHub Account
The following instructions are taken from [this github tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui#adding-a-new-ssh-key-to-your-account).
In the cheetah terminal window, enter the following command

```
cat ~/.ssh/id_ed25519.pub
```

Copy the text that appears on the screen.  It should look something like, though the jumble of text in the middle will be longer

```
ssh-ed25519 drbhn?+--+12cbAAShDAF your_email@example.com
```

In your web browser, go to GitHub, click your profile photo, then click ⚙ *Settings*.

In the “*Access*” section of the sidebar, click “*SSH and GPG keys*.”

Click *New SSH key*.

In the “*Title*” field, write `Cheetah`

In the “*Key type*” drop-down menu, select *Authentication Key*

In the “*Key*” field, paste your public key.

Click *Add SSH key*.

If prompted, confirm access to your account on GitHub.

### You will now be able to move on to Activity 3: Demonstrate access to resources.

