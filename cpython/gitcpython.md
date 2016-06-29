# GitHub and patches

## Creating a patch

1. Clone the "semi-official" CPython repo on GitHub:

        $ git clone https://github.com/python/cpython.git

2. Change directory to cpython:

        $ cd cpython

3.  Create and checkout a branch to work on the issue fix:

        $ git checkout -b fix_issue

4. Make changes to fix the issue.

5. Commit the changes:

        $ git add file1 file2 file3
        $ git commit -m"Commit message"
        $ git log --pretty=oneline -3

6. Create the patch (Note: this creates a patch of the differences between the
   master branch and the feature branch)

        $ git format-patch master --stdout > fix_issue.patch

## Testing a patch

    $ git apply --stat fix_issue.patch

    $ git apply --check fix_issue.patch

## Accepting a patch

    $ git am --signoff < fix_issue.patch
