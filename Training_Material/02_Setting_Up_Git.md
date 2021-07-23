Open the terminal. 

Starting at your **home directory** type the following commands to set up your Git account as a user:

`git config --global user.name “X”` : where **X** is your name in Gitlab. For example: if your name is John Smith then on the prompt of **Git Bash** type: `git config --global user.name “John Smith”`

`git config --global user.email “Y”` : where **Y** is same email as used in Gitlab, e.g. if John smith is using this TU Delft Gitlab instance, then the email would be `J.Smith@tudelft.nl`.

`git config --global core.editor “Z“` : where **Z** is the text editor of your preference. For example:  

| Editor     | Git configuration                                             |
|------------|---------------------------------------------------------------|
| **Kate**   | `git config --global core.editor "kate"`                      |
| **Gedit**  | `git config --global core.editor "gedit --wait --new-window"` |
| **Vim**    | `git config --global core.editor "vim"`                       |
| **VSCode** | `git config --global core.editor "code --wait"`               |
| **Emacs**  | `git config --global core.editor "emacs"`                     |

Keep in mind, some editors open **within** the terminal itself (e.g., **Vim** or **nano**) while others will open **outside** the terminal as a separate application (e.g., [**VSCode**](https://code.visualstudio.com/download) or **gedit**). Recommendation: use editors that open **within** the terminal itself. Then you will get used to shorten your **commit** messages.

__________________________
### Parenthesis

There are actually more files Git looks for when configuring your Git instance. The one that defines the `--global` settings refers to the file in your `~/.gitconfig` (or `~/.config/git/config` file if applicable).

Type `git config --list` to see a list of all configuration settings of Git. 

Type `git config --help` to see the help page for Git configuration options.

__________________________

[Previous : Git Intro](01_Git_Intro.md)  

[Next     : Initialize Local Repo](03_Initialize_Local_Repo.md)

