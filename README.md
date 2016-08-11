# fastd-git-hook

You need those repositories:

    git clone https://github.com/freifunk-kiel/fastd-git-hook
    git clone git://git.freifunk.in-kiel.de/fastd-peer-keys.git

Add the file `pre-commit` to your `.git/hooks/` folder:

    cp fastd-git-hook/git/hooks/pre-commit fastd-peer-keys/.git/hooks/pre-commit

And make it executable    

    chmod +x fastd-peer-keys/.git/hooks/pre-commit
