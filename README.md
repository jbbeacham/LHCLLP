# LHCLLP
This is the central repo for the white paper for the LHC LLP Community initiative.  Welcome!

Here, the master branch is the main branch, and all changes should be made by you, a chapter editor or core contributor, by branching from master and then pushing those changes back to master, where they will show up as a pull request (a "merge request" for those familiar with, for example, gitlab) which will then be reviewed and merged into master.  Since it's unlikely that two people will be working on the same file at the same time (and you are encouraged to communicate among your chapter's editors to reduce conflicts), merge conflicts should be rare.

So a standard workflow for us would be the following:

# Setup a directory where you'll do your git stuff
mkdir WhitePaper
cd WhitePaper/
git clone https://github.com/jbbeacham/LHCLLP.git
cd LHCLLP
git init

# Then whenever you want to edit something, do the following:

# Make sure your local copy is up-to-date with master
git pull origin master

# You can always check which branch you're on
git branch -vvv

# Create a new, local branch from master and then "checkout" that branch, i.e., switch to it so you can work on it
git checkout -b James_Edit_v01 master --no-track

# Now check which branch you're on
git branch -vvv

# Now make some changes
emacs -nw tex/ExperimentCoverage.tex

# Note that you can compile the tex using pdftex in this directory like normal, to look at the pdf, since the pdf is *not* being tracked by github (and please don't "add" it at this point), nor are the log files, etc., being tracked.
pdflatex doc.tex

# Now check that git knows what's changed, etc.
git status

# Now "add" the file you just changed, i.e., tell git to include the file you just edited when you "commit" these changes
git add tex/ExperimentCoverage.tex

# Now see how the output of "git status" has changed
git status

# Cool.  Now "commit" the changes.
git commit -m "Good description of these changes."

# Now "push" this commit.
git push origin -u James_Edit_v01

# Now you can go to the github page, notice that the most recent activity has been a push from this branch, and then click the button to create a pull request, which will bring it to my attention for merging into the master branch.

# Then when you want to make another edit, do the same, but first make sure your local copy of master is up-to-date.
git pull origin master
git checkout master
git pull

# Then start again with...
git checkout -b James_Edit_v02 master --no-track

# ...and continue as above.



