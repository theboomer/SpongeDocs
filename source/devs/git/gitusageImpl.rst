================================
Git Usage for Sponge Implementation
================================

After cloning the Sponge project as per the instructions :doc:`gitusage` under enlisting the Sponge source,
the developer can start to work.

Note:  ``Mixin``, and ``SpongeAPI`` are two submodules of the Sponge project.  Before commits to Sponge, make sure
to test, and ``commit`` and ``push`` the changes to either Mixin and/or SpongeAPI *before* making commits and pushing
changes to Sponge.   When changes to SpongeAPI and/or Mixin are done, the ``git status`` within Sponge will show
unstaged commits that refer to the submodule(s).  ``git add SpongeAPI`` and/or ``git add Mixin`` if those submodules
appear in the status as unstaged commits.

If the work that is about to occur involves changes to both implementation AND the API please STOP HERE and go look
at :doc:`gitusageApi`. 


1. ``cd Sponge``

#. ``git pull``

.. tip::
    The developer should bring master branch current before branching.  ``git pull`` brings the branch (master at this point) up to date before branching it.

#. ``git checkout -b YourBranchName``

.. tip::
    The name of the branch should follow a convention.  Please use a name with a pattern ``feature/added-feature``.  Good examples:  ``feature/network-packet``, `feature/user-commands``.  Not good examples:  ``feature/fixes``, ``feature/trying-something``.  

#.  Work with the files, create files, etc..  Work in the branch. (Use ``git branch`` to list the branch that is current)

#.  When done working with the files check that the
    module will compile.  This would be a good idea before even making
    the commit.

.. tip::
    Run ``gradle compileJava`` to run a simple build of the source files.

#.  When convinced that the build of the branch of the Sponge is
    ok then commit. 

#.  ``git status``

#.  Look for files that are noted as not staged for commit.   Add the
    files that need to be staged for commit.

#.  ``git add FILE(s)``

#.  Since you're working with the implementation, there is a chance that
    your work also included work in the API.  It's OK to work in both
    at the same time.  The trick is to make sure when you commit and push
    you do so that the pointers for which version of SpongeAPI are matched
    to your version of the branch (your commit).  To ensure that, before
    you finish commit on your implementation work, double check the status
    of the working area.  You may need to add the submodules to the commit.

#.  ``git add SpongeAPI``    (May be required)
#.  ``git add Mixin``        (May be required)
#.  ``git status``           (Look for unstaged commits.  You should have already commited your SpongeAPI changes and pushed them before moving forward with the implementation commit and push).

#.  ``git commit``

#.  Edit the commit message.  This message should be short and concise.

#.  Now that you've made the commit, you can push this commit to the 
    repository.

#.  ``git push``

.. tip::
    If this is the first time you're pushing a commit for this new branch then the branch is not on the upstream remote.  You may see this warning:

    ``fatal: The current branch YourBranchName has no upstream branch.``
    
    To push the current branch and set the remote as upstream, use

    ``git push --set-upstream origin YourBranchName``

#.  Once your commit is pushed to the repository, then you can open
    a pull request

