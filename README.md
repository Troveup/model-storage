# Trove Model Repo

A collection of Trove model designs in our proprietary json format. We are experimenting with this as a replacement for google drive because

- git protocol will likely be more robust, multiple problems with google drive failing to sync
- maintain unambiguous versioning information, models are frequently updated to correct issues

## Organization

Every distinct design is bundled into its own directory which contains the source blend file, any generated json artifacts, any images or pdfs that describe the dimensions or appearance of the model concept, and any other files relevant to that model. The name of the directory should roughly correlate to the official name of the design, prefixed with the category type of that design. For example, the bar ring design would have its blend file, concept sketches, and json output stored in a directory called `ring_bar`. Sometimes it is beneficial to keep multiple blend files with varying levels of detail, it is best practice to only keep the final exportable blend file directly in the folder and to place any additional helper blend files in a subdirectory called `scratch`.

Model directories are further organized into different folders depending on their relation to other models. For instance, a group of thematically similar designs would be bundled in a collection since they would likely be released simultaneously as a unit. A group of models belonging to the Arrow Collection might be grouped as such:

	collection_arrow/
		ring_arrow/
			arrow_ring.blend
			arrow_ring.json
			arrow_ring_spec.pdf
			...
		bracelet_arrow/
			...
		necklace_arrow/
			...
		neclace_arrow_inverted/
			...

The top level folders signal the development status of the models. As models/collections change status they should be moved to the appropriate folder. If only one item in a collection needs to move, create a duplicate collection parent folder

- concepts - Designs that are in a very early stage of ideation and may still change dramatically before it is appropriate to invest in modelling them
- todo - Designs that are ready to be modelled or in progress. There will be subfolders for each person working on modelling, if you are working on something move it into your subfolder to avoid wasting time from multiple people modelling the same design
- qa - Designs that have been modelled and the final json artifact generated, but have yet to be fully QA'd before releasing to production
- live - Designs that are currently on production
- fixing - Designs that have been released to production but have had a serious defect discovered. Similar to qa but more urgent

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