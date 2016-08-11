# fastd-git-hook

You need those repositories:

    git clone https://github.com/freifunk-kiel/fastd-git-hook
    git clone git://git.freifunk.in-kiel.de/fastd-peer-keys.git

Add the file `pre-commit` to your `.git/hooks/` folder:

    cp fastd-git-hook/git/hooks/pre-commit fastd-peer-keys/.git/hooks/pre-commit

And make it executable    

    chmod +x fastd-peer-keys/.git/hooks/pre-commit

Now whenever you commit a new key, there is a check if the syntax is ok and if there are no double keys.

Additionally, if you only use small letter key-files, you can uncomment the part at the end that renames all capital letters:

    for f in *; do 
    	NEW="$(echo $f | tr '[A-Z]' '[a-z]')";
    	if [ "$f" != "$NEW" ]; then 
    		git mv -v $f $NEW;
    	fi; 
    done;

