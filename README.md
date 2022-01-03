# ctree
ctree - command line christmas tree
[![Screenshot-from-2021-12-29-20-00-47.png](https://i.postimg.cc/X7M6RTr9/Screenshot-from-2021-12-29-20-00-47.png)](https://postimg.cc/mhSnMpNr)
------

It is small python script that prints a christmas tree in terminal.

It is colourful and always gives you a different tree with different
decorations varying in position with three colours, more colours and
decorations can be easilty added by looking into code.

A great script to be added in your **unixporn** screenshot.

------

### Installation
#### Linux
use these commands in terminal :
```shell
git clone https://github.com/RohanKP1/ctree.git
cd ctree/
sudo mv ctree.py /usr/bin/ && chmod +x /usr/bin/ctree.py
```

#### macOS
use these commands in terminal :
```shell
git clone https://github.com/RohanKP1/ctree.git
cd ctree/
sudo mv ctree.py /usr/local/bin/ && chmod +x /usr/local/bin/ctree.py
```

### How to run
Simply type `ctree.py` in terminal and `Enter`.

### Animating the tree
Add the parameter `--animate` or `-a` to animate the tree in an infinite loop (use `ctrl+c` to stop). This may fail to
work in embedded terminals (e.g. PyCharm).
```shell
ctree.py -a
```
