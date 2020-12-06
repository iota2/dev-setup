# iota2

> Making Imaginations, Real

<i2.iotasquare@gmail.com>

```
 ██╗ ██████╗ ████████╗ █████╗ ██████╗
 ██║██╔═══██╗╚══██╔══╝██╔══██╗╚════██╗
 ██║██║   ██║   ██║   ███████║ █████╔╝
 ██║██║   ██║   ██║   ██╔══██║██╔═══╝
 ██║╚██████╔╝   ██║   ██║  ██║███████╗
 ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝
```

[![BSD licensed](https://img.shields.io/badge/license-GPL3-blue.svg)](https://raw.githubusercontent.com/iota2/dev-setup/master/LICENSE)


# Powerline on bash:

[Powerline Shell details](https://medium.com/@ike_okonkwo/setting-up-powerline-on-ubuntu-18-04-a87866577781)


### Install powerline shell
```
pip install powerline-shell
```

### Configuring bash
Add the following code snippet to `~/.bashrc` file:
```
# >>> powerline-shell initialize >>>
function _update_ps1() {
    PS1=$(powerline-shell $?)
}

if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
# <<< powerline-shell initialize <<<
```

### Update Configuration File
Powerline-shell is customizable through the use of a config file. This file is expected to be located at ~/.config/powerline-shell/config.json. You can generate the default config at this location using:
```
mkdir -p ~/.config/powerline-shell && \
powerline-shell --generate-config > ~/.config/powerline-shell/config.json
```
And replace `~/.config/powerline-shell/config.json` with the reference file.


# Adding Fonts:
### Clone
```
git clone https://github.com/powerline/fonts.git --depth=1
```

### Install Fonts:
```
cd fonts
./install.sh
```

### clean-up a bit
```
cd ..
rm -rf fonts
```

### Configurations using `fontconfig`:
In some distributions, Terminess Powerline is ignored by default and must be explicitly allowed.
A `fontconfig` file is provided which enables it. use the files provided under fontconfig/ of the repo
```
cp fontconfig/50-enable-terminess-powerline.conf  ~/.config/fontconfig/conf.d/
```
For changes to take place run:
```
fc-cache -vf
```

# License
> `GNU GPU v3` <br>
> This program is free software; you can redistribute it and/or
> modify it under the terms of the GNU General Public License
> as published by the Free Software Foundation; either version 3
> of the License, or (at your option) any later version.
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.

**Free Software, Hell Yeah!**

