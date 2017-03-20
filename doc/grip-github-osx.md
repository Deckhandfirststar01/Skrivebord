How to setup grip and github on osx
===================================

Prequisite
----------

### Install homebrew

Open a terminal and paste the following command to install [homebrew](https://brew.sh/)

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

<img src='/res/doc/grip-github-osx/pre_2.png' />
<img src='/res/doc/grip-github-osx/pre_3.png' />

### Install grip

```
brew install grip
```

<img src='/res/doc/grip-github-osx/pre_4.png' />
<img src='/res/doc/grip-github-osx/pre_5.png' />


### Install textmate

Textmate is a popular textedior for MacOSX. It is not required for editing the spec, if you already have a favourite texteditor feel free to use that instead, as long as it has syntax highlighting every texteditor should be fine.

```
brew install textmate
```
<img src='/res/doc/grip-github-osx/pre_6.png' />
<img src='/res/doc/grip-github-osx/pre_7.png' />

### Setup git name/email

Set up the user name and email address so commits you make have the correct author.

(NOTE: Replace Jon Doe/johndoe@example.com with your name and email. Remember to keep the quotes for the user name because it will contain a space)

`git config --global user.name "John Doe"`

`git config --global user.email johndoe@example.com`

### Setup EDITOR

The default *EDITOR* for OSX is vi/vim, if you are comfortable with vim you can skip this step.

```
echo export EDITOR=`which nano` >> ~/.bash_profile
```

![pre_8.png](/res/doc/grip-github-osx/pre_8.png)

### Create SSH key

An ssh key is used to authenticate and identify your identity for access to the git repository on <https://github.com>, think of it as a more secure username/password.

Create *.ssh* folder

```
mkdir -p .ssh
```


Create a new key

(NOTE: For simplicity we are creating a ssh key without a passphrase, that means everybody with access to your computers harddisk can read your ssh key and gain access to the repository. In this case it doesn't really matter because the key protects access to the specification of an open source programm which will be publicly available sooner or later anyway. Just be aware that this is not the safest way to create an SSH key.)
```
$ ssh-keygen
ENTER
ENTER
ENTER
```
<img src='/res/doc/grip-github-osx/pre_9.png' />


### SSH public key

Copy the content of the key to paste it on <https://github.com>

```
cat ~/.ssh/id_rsa.pub
```
<img src='/res/doc/grip-github-osx/pre_10.png' />

### Add SSH public key

Go to your github settings [https://github.com/settings/profile](https://github.com/settings/profile) (login if necessary).

![](/res/doc/grip-github-osx/github_1.png)


Then click on *SSH and GPG keys* and add a new ssh key via *New SSH key*.

Type in a name for the key (e.g. Jeens Macbook) and then paste the key from [above](#above) in the *key* textarea.

Then click *Add SSH key* to save the new key.

![](/res/doc/grip-github-osx/github_2.png)


The newly added key should show up on the [keys settings page](https://github.com/settings/keys)

![](/res/doc/grip-github-osx/github_3.png)



### Clone repository

After your key has been added you can clone the repository.

The url of the repository is shown after you click the *Clone or download* link on the repository page.

![](/res/doc/grip-github-osx/github_4.png)

If you have the url go back to your terminal and clone the repository:

```
cd ~/Desktop/
git clone git@github.com:wvspee/spec.git
```

![git clone output](/res/doc/grip-github-osx/clone_1.png)

The repository is now ready in *~/Desktop/spec/*
