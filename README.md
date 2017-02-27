# Ivan's Dotfiles

>  Your dotfiles will most likely be the longest project you ever work on.

Quote by Anish Athalye on his
[blog](http://www.anishathalye.com/2014/08/03/managing-your-dotfiles/).

I completely agree with Anish, and thus maintain this repo for my dotfiles.
There are many like them, but these are mine.

## Prerequisites

You will need to have the following installed:

- python: for dotbot
- vim: for vimrc
- zsh: for the shell

## Installation

Clone and run `./install`. This will download
[dotbot](https://github.com/anishathalye/dotbot) and symlink everything into
place. If you don't have ZSH already as your default shell, run
`~/.dotfiles/zsh/setup`

If you would like to only install the ZSH component and nothing else, use
`minstall`. This references `minimal.comf.yaml` and links the `zshrc` and git
hooks only.

If you trust me, you can also do `wget https://smirnov.link/d -O - | sh`. This
pulls the `d` file which clones the repo, runs a full install and tells you how
to install zsh.

### Ansible

There's an [ansible role](https://galaxy.ansible.com/issmirnov/dotfiles/) for this repo. Simply add `issmirnov.dotfiles` as a role.

## Submodules Used

- Dotbot for installation.
- oh-my-zsh for zsh foundation.
- Vundle for vim.

## Points of Interest

- The post commit hook in the [git](git/) directory is very interesting. It
  checks for changes, and depending on which rules are matched will run certain
  commands. Ie, if the zsh folder contains changes we will source zshrc for
  you. With changes to vim we will rerun the vim install script.
- The [i3](i3/) folder contains my solution for managing i3 config across
  multiple machines. My fleet ranges from weak laptops to triple head power
  beasts, and it's annoying to copy paste config. There's more detail in the
  folder. Basically you can add rules for a specific host and factor out common
  config, which gets spliced in dynamically on every pull.
- The [vim](vim/) directory is relatively standalone, and contains my attempt
  at building a sane vim config that isn't compelx enough to launch nukes when
  your cat sneezes on the keyboard. 

## A Note about the License & Copyright:

Unless attributed otherwise, everything is under the MIT license (see LICENSE
for more info).

Some stuff is not from me, and without attribution, and I no longer remember
where I got it from. I apologize for that.

Feel free to copy whatever suits you, and open an issue with a question if you
need some help.
