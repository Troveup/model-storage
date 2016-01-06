# Trove Model Repo

A collection of Trove model designs in our proprietary json format. We are experimenting with this as a replacement for google drive because

- git protocol will likely be more robust, multiple problems with google drive failing to sync
- maintain unambiguous versioning information, models are frequently updated to correct issues

## Usage

I'll write this when I figure it out.

## Setup

### Windows

Download git for windows here:

	https://git-scm.com/download/win

Installing this first allows git-lfs extension to automatically detect the proper installation path. Download the git-lfs installer here:

	https://git-lfs.github.com/

Then start a git bash shell and run the following command:

	git lfs install

Now, still within the bash shell, navigate to the directory within which you would like to store the model repository, and clone the repo. In this example we'll store it in a Trove folder on the desktop:

	cd /c/users/ian/Desktop/Trove
	git clone https://github.com/Troveup/model-storage.git

### Linux

Ensure that git is installed, use a package manager install command if you don't have it. I found the directions for installing git-lfs via the packagecloud service to not work so I would recommend downloading one of the binaries from this page under Downloads:

	https://github.com/github/git-lfs/releases

Untar the archive and use the included setup script to put the executables in globally accessible location:

	tar xzf <tar file name>
	cd git-lfs-1.1.0/
	chmod +x install.sh
	sudo ./install.sh