# gedit-gists

 **Author:** Nick Baugh ([@niftylettuce](http://twitter.com/#!/niftylettuce)) |

 1. Install `xclip` for clipboard copying:

        sudo apt-get install xclip

 2. Install `gista` (**Note:** this requires [node](https://github.com/joyent/node) and [npm](https://github.com/isaacs/npm)):

        npm install -g gista

 3. Add a new entry called `gedit-gists` under `Tools -> Manage External Tools`:

        #!/bin/sh
        if [ -d "$HOME/bin" ]; then PATH="$HOME/bin:$PATH"
        fi
        export PATH=$HOME/local/node/bin:$PATH
        if [ -n "${GEDIT_CURRENT_DOCUMENT_NAME+x}" ]; then
        cat $1 | gista -pn $GEDIT_CURRENT_DOCUMENT_NAME -d "Gist created using https://github.com/niftylettuce/gedit-gists" | xclip -selection clipboard
        else
        cat $1 | gista -pd "https://github.com/niftylettuce/gedit-gists" | xclip -selection clipboard
        fi
        echo "Successfully created gist (URL is copied to clipboard)"

 4. Set External Tool Options as follows: // TODO: replace this

    ![Set External Tool Options as follows](http://i.imgur.com/yqurh.png)

 5. Open your file in gedit, then use the hotkey `CTRL+SHIFT+G` to generate and store a Gist URL to your clipboard.

 6. You can also select specific parts of a file and use the hotkey.

 7. If you would like to modify things (e.g. public vs. private gists) please view the Source link above.


 ---

For more gedit plugins, tools, tricks, and tips: [https://github.com/niftylettuce/gedit-icing](https://github.com/niftylettuce/gedit-icing)
