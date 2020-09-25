---
title: "Getting started with GitHub"
keywords: sample homepage
tags: [getting_started]
sidebar: mydoc_sidebar
permalink: index.html
toc: false
summary: These brief instructions will help you get started with pushing documentation to the website. 
header:
    image: "/images/github01.JPG"
---

## GitHub Account

Follow these instructions to set up your github account.

### 1. Create a GitHub account

Go to github.com. [link](https://www.github.com) Click on the **Sign up** button and follow the instructions to create your account. 

### 2. Install GitBash for Windows

Go to https://git-scm.com/downloads. [link](https://git-scm.com/downloads) Select the Windows version and follow instruction to download. You can select the default options throughout the installation wizard. 

### 3. Authentication

Now that you have your Github account created, the first step is to connect your machine to your Github account through an SSH key. With an SSH key, Github is able to authenticate you automatically every time you try to manipulate your repository without the need to provide your username or password, which is super convenient.
To create an **SSH** key, simply follow the steps outlined below:
1. Launch Git Bash.
2. Type the following, replacing "<your email address>" with the email address that is linked to your Github account, and hit Enter:

```
ssh-keygen -t rsa -b 4096 -C "<your email address>" serve
```
This will generate a new **SSH** key.
3. Next, you will be prompted to enter a directory to save the key. I simply press Enter to accept the default location, which is a .ssh folder in the home directory. In other words, you will be able to locate the key in “~/.ssh/id_rsa”.
4. You will then be prompted to choose a passphrase. I prefer not to have a passphrase; so just press Enter and Enter again to confirm the empty passphrase.
Now, if you navigate to the .ssh subdirectory, i.e., if you run the following in the Git Bash terminal,
```
cd ~/.ssh
```
and then,
``
ls
``
to the list the contents of the .ssh subdirectory, you should find “id_rsa” and “id_rsa.pub” in the list of contents, where “id_rsa” is the private version of your key and “id_rsa.pub” is the public version of your key.
5. Finally, you will need to add the SSH key to the ssh-agent, which is meant to help with the authentication process. To do that, first you need to start the ssh-agent, so run the following in the Git Bash terminal:
```
eval "$(ssh-agent -s)"
```
And then add the key to the agent by running the following in the Git Bash terminal:
```
ssh-add ~/.ssh/id_rsa
```
### 4. Add the Key to Your Github Account
The next step is to add the SSH key to your Github account. The first thing to do, is to run the following in the Git Bash terminal:
```
cat ~/.ssh/id_rsa.pub | clip
```
What this does is it copies the public version of your key to the clipboard buffer.

Then, go to your Github account, and click your profile pic in the top right corner of your Github account and select “Settings” from the drop-down menu, as shown below:

{% include image.html file="github01.JPG" %}

Under Personal settings, select “SSH and GPG keys”, as shown below:
{% include image.html file="github02.JPG" %}

On the next page, click the button to add a new SSH key to your account, as shown below:
{% include image.html file="github03.png" %}

This will start a new form where you will have to add the key and give it a name as well.
{% include image.html file="github04.png" %}

For the title, you give the key a name that describes the machine associated with it. So, if it is your personal computer, then you can name it “Personal-Computer”, as shown below:
{% include image.html file="github05.png" %}

Then, select the Key field, and press Ctrl-v to paste the key from the clipboard buffer. The pasted key should have your email address at the end, as shown below:
{% include image.html file="github06.png" %}

Finally, click the “Add SSH key” to complete the process of adding the SSH key to your Github account.

### 5. Clone the ramlab repository 
Now that your machine is linked to your Github account, and Github is confident that any manipulation of any of your repositories coming from your machine would be initiated by you, let’s go ahead and clone the RAMLab Github repository.

Go to the RAMLab  github website (https://github.com/ramlab-robotics/ramlab). [link](https://github.com/ramlab-robotics/ramlab)
1. Copy the URL of the repo by pressing on the **Code** green button and clicking on the clipboard as shown below:
{% include image.html file="github07.JPG" %}
2. In the GitBaash terminal type ``cd`` to go to your home directory and then ``cd ~/Documents``. 
3. In the Documents folder clone the repository by typing ``git clone [URL]`` replace URL with the URL that was copied from github. 
4. Open your files and check that the repository has been added to the Documents folder.

### 6. Add a sidebar topic

1. Open the repo in your word editor of choice (I recommend Visual Studio Code https://code.visualstudio.com/download. [link](https://code.visualstudio.com/download))
The file structure should look like this:
{% include image.html file="github08.JPG" %}
2. Open the ``mydoc_sidebar.yml`` file located inside of data>sidebars as shown below: {% include image.html file="github09.JPG" %}
3. Create an entry called **How-to** with two page items as shown below. Create a url for each page. e.g. ``url: /arduino_odrive_instructions.html`` this will be the url where we will provide the content.
 {% include image.html file="github10.JPG" %}

### 7. Create a page

 1. Create a file called ``mydoc_howto_arduino_odrive.md'' , for example, inside of pages > mydoc. 
 2. Add specified parameters and attributes to the top of the file like this:
 ```
---
title: ODrive Arduino Instructions
tags: [tutorials]
keywords: 
last_updated: September 24, 2020
summary: 
sidebar: mydoc_sidebar
permalink: arduino_odrive_instructions.html
folder: mydoc
---
 ```

 Make sure the ``permalink`` attribute matches the url created for the sidebar and ppulate with the approprote tags, keywords, summary etc.

 3. Add the documentation below the ``---`` lines.

 For guidance, look at the page templates inside of ``pages > mydoc``

### 8. Push Changes

 1. Save the changes made to your files inside of the repo

 2. Inside of GitBash ``cd`` into the repo. ``cd ~/Documents/ramlab``

 3. Add all changes from the working directory to the staging directory using the command ``git add -A``

 4. Commit all changes and add a comment describing the changes made using the command ``git commit -m "Created a How-to page"``

 5. Push changes to github using the command ``git push https://'ramlab-robotics':'[password]'@github.com/ramlab-robotics/ramlab``
 Replace [passsword] with the github password for the ramlab-robotics account. To request this password email ramlab.robotics@gmail.com with your name and UIC UIN

### 9. Check changes published

 Once you have pushed your changes it may take a couple of minutes for them to be reflected on the website. Visit https://ramlab-robotics.github.io/ramlab/. [link](https://ramlab-robotics.github.io/ramlab/) or refresh this page to see the changes.

 