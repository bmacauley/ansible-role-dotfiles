# ansible-role-dotfiles
Installs a set of dotfiles from a Git repository. By default it installs the bmacauley/dotfiles. You can use other dotfiles by changing the configuration.

![Build status](https://travis-ci.org/bmacauley/ansible-role-homebrew.svg?branch=master)

## Requirements
- Git

## Role variables
Default variables are in `defaults/main.yml`

```
dotfiles_repo: "https://github.com/bmacauley/dotfiles.git"
```
The git repository containing the dotfiles. Dotfiles should be laid out within the root directory of the repository


```
dotfiles_repo_accept_hostkey: no
```
Add a hostkey for the repo url if not added. If ssh_opts contains "-o StrictHostKeyChecking=no", this parameter is ignored.


```
dotfiles_repo_local_destination: "~/.dotfiles"
```
The local path where the `dotfiles_repo` will be cloned


```
dotfiles_home: "~"
```
The home directory where dotfiles will be linked. Generally, the default should work, but in some circumstances, or when running the role as sudo on behalf of another user, you may want to specify the full path.


```
dotfiles_files:
  - .bash_profile
  - .gitignore
  - .inputrc
  - .vimrc
```
The files from the `dotfiles_repo` that will be linked to the `dotfiles_home`

## Dependencies
none

## Example playbook
```
- hosts: localhost
  roles:
    - { role: ansible-role-dotfiles }
```


## License

MIT

## Author

Brian Macauley brian.macauley@gmail.com

Based on [geerlingguy/ansible-role-dotfiles](https://github.com/geerlingguy/ansible-role-dotfiles)
