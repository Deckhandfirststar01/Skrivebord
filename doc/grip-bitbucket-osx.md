How to setup grip and bitbucket on osx
===================================

Prequisite
----------

### Install homebrew

Open a terminal and paste the following command to install [homebrew](https://brew.sh/)

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

![](/res/doc/grip-bitbucket-osx/pre_2.png)
![](/res/doc/grip-bitbucket-osx/pre_3.png)

### Install grip

```
sudo brew install grip
```

![](/res/doc/grip-bitbucket-osx/pre_4.png)
![](/res/doc/grip-bitbucket-osx/pre_5.png)


### Install textmate

Textmate is a popular textedior for MacOSX. It is not required for editing the spec, if you already have a favourite texteditor feel free to use that instead, as long as it has syntax highlighting every texteditor should be fine.

```
sudo brew install textmate
```
![](/res/doc/grip-bitbucket-osx/pre_6.png)
![](/res/doc/grip-bitbucket-osx/pre_7.png)

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

![pre_8.png](/res/doc/grip-bitbucket-osx/pre_8.png)

### Create SSH key

An ssh key is used to authenticate and identify your identity for access to the git repository on <https://bitbucket.org>, think of it as a more secure username/password.

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
![](/res/doc/grip-bitbucket-osx/pre_9.png)


### SSH public key

Copy the content of the key to paste it on <https://bitbucket.org>

```
cat ~/.ssh/id_rsa.pub
```
![](/res/doc/grip-bitbucket-osx/pre_10.png)

### Add SSH public key

Go to your bitbucket settings <https://bitbucket.org/account/user/USERNAME/> (replace, USERNAME with your actual user name, login if necessary).

![](/res/doc/grip-bitbucket-osx/bitbucket_1.png)


Then click on *SSH keys* and add a new ssh key via *Add key*.

![](/res/doc/grip-bitbucket-osx/bitbucket_2_1.png)

Type in a name for the key (e.g. Jeens Macbook) and then paste the key from [above](#above) in the *key* textarea.

Then click *Add key* to save the new key.

![](/res/doc/grip-bitbucket-osx/bitbucket_2_2.png)


The newly added key should show up on the *keys settings page* <https://bitbucket.org/account/user/USERNAME/ssh-keys/>

![](/res/doc/grip-bitbucket-osx/bitbucket_3.png)



### Clone repository

After your key has been added you can clone the repository.

The url of the repository is shown after you click the *Clone or download* link on the repository page.

![](/res/doc/grip-bitbucket-osx/bitbucket_4.png)

If you have the url go back to your terminal and clone the repository:

```
$ cd ~/Desktop/
$ git clone git@bitbucket.org:adblockplus/spec.git
yes
```

(NOTE: type yes and press ENTER if git asks you whether you want to continue connecting)

![git clone output](/res/doc/grip-bitbucket-osx/clone_1.png)

The repository is now ready in *~/Desktop/spec/*
