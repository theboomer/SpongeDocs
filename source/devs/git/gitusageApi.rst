=======================
Git-Fu for SpongeAPI
=======================

1. ``cd SpongeAPI``

#. ``git pull``

.. tip::
    Bring the master branch current before branching.  ``git pull`` brings the branch (master at this point) up to date before branching it.

#. ``git checkout -b feature/new-branch-name``

.. tip::
    The name of the branch should follow a convention.  Please use a name with a pattern ``feature/new-branch-name``.  Good examples:  ``feature/network-packet``, `feature/user-commands``.  Not good examples:  ``feature/fixes``, ``feature/trying-something``.

#.  Work with the files, create files, etc..  Do work in the branch.

#.  When done working with the files check that the module will compile.  This would be a good idea before even making
    the commit.

.. tip::
    Run ``gradle compileJava`` to run a simple build of the source files.  The IDE may provide a means to compile. Always check that the changes compile with gradle.  Do not depend on the IDE only.

#.  When proven that the build of the new branch of the SpongeAPI is ok then commit.  Ensure the current working directory is SpongeAPI else ``git status`` will miss checking for files that may be part of the commit.

#.  ``git status``

#.  Look for files that are noted as not staged for commit.   Add the
    files that need to be staged for commit.

#.  ``git add <file>``

#.  Check for unstaged files.  Check for untracked files via ``git status``

#.  When all the files are staged for commit, then commit.

#.  ``git commit``

#.  Edit the commit message.  This message should be short and concise.

#.  Now that the commit is made, push this commit to the repository.  Push commits to the SpongeAPI before commit and push to the implementation (Sponge).

#.  ``git push``

.. tip::
    If this is the first time pushing a commit for this new branch then the branch is not on the upstream remote.  You may see this warning:

    ``fatal: The current branch YourBranchName has no upstream branch.``

To push the current branch and set the remote as upstream, use

    ``git push --set-upstream origin YourBranchName``


#.  Once the commit is pushed to the repository, then open a pull request on GitHub for the SpongeAPI project.

#.  If this commit to the SpongeAPI is part of a set of changes that affect the Sponge implementation then go to
the documentation for handling the changes to Sponge :doc:`gitusage`.


