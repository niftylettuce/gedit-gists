# gedit-gists

 **Author:** Nick Baugh ([@niftylettuce](http://twitter.com/#!/niftylettuce)) |
 **Source:** [https://github.com/rocketraman/gist.sh](https://github.com/rocketraman/gist.sh)

 1. Install `xclip` for clipboard copying:

        sudo apt-get install xclip
  
 2. Install `gist.sh`:
  
        curl http://github.com/gmarik/gist.sh/raw/master/gist.sh > gist.sh
        chmod 755 gist.sh
        sudo mv gist.sh /usr/local/bin/ 
        
 3. Add a new entry called `gedit-gists` under `Tools -> Manage External Tools`:
  
        #!/bin/sh
        cat $1 >> /tmp/$GEDIT_CURRENT_DOCUMENT_NAME
        gist.sh -f /tmp/$GEDIT_CURRENT_DOCUMENT_NAME -p | xclip -selection clipboard
        rm /tmp/$GEDIT_CURRENT_DOCUMENT_NAME
        
 4. Set External Tool Options as follows:

    ![Set External Tool Options as follows](http://i.imgur.com/AqNWo.png)
    
 5. Open your file in gedit, then use the hotkey `CTRL+SHIFT+G` to generate and store a Gist URL to your clipboard.
 
 6. You can also select specific parts of a file and use the hotkey.
 
 7. If you would like to modify things (e.g. public vs. private gists) please view the Source link above.
 
 
 ---
 
For more gedit plugins, tools, tricks, and tips: [https://github.com/niftylettuce/gedit-icing](https://github.com/niftylettuce/gedit-icing)
