# Git Server Setup

> This guide explains how to set up a simple Git server using SSH on Ubuntu.

---------

## 1. Install Git

For installation see 01_git_install.md

Check installation:

``` bash
git --version
```

-----------

## 2. Create a Git User

Create a dedicated user for hosting repositories:

``` bash
sudo adduser --disabled-login --gecos 'Git Version Control' git
```

or if adduser command does not exist:

```bash
sudo useradd -m -r -s /usr/bin/git-shell git
```


------

## 3. Create a Bare Repository

Bare repositories are used as central remotes:

``` bash
sudo mkdir -p /srv/git/myproject.git
sudo chown -R git:git /srv/git/myproject.git

cd /srv/git/myproject.git
sudo -u git git init --bare
```

-----------------------------

## 4. Configure SSH Access

There are 2 options:

Option 1:

```bash
ssh-copy-id
```

Option2:
Create SSH directory:

``` bash
sudo mkdir /home/git/.ssh
sudo vi /home/git/.ssh/authorized_keys
```

Paste users' public keys (`id_rsa.pub`) into `authorized_keys`.

Set correct permissions:

``` bash
sudo chown -R git:git /home/git/.ssh
sudo chmod 700 /home/git/.ssh
sudo chmod 600 /home/git/.ssh/authorized_keys
```

---------------

## 5. Clone the Repository (Client Side)

``` bash
git clone git@yourserver:/srv/git/myproject.git
```

Or add as remote:

``` bash
git remote add origin git@yourserver:/srv/git/myproject.git
git push -u origin master
```

------------

## 6. Optional: Web Interface

### Option A: Gitea (lightweight)

Download and install (in your home folder):

``` bash
git clone https://github.com/go-gitea/gitea.git
```

> build the software

```bash
cd gitea
make build
```

```bash
chmod +x gitea
sudo mv gitea /usr/local/bin/
```

Run:

``` bash
gitea web
```

Open in browser:

http://yourserver:3000

-----------

## Notes

-   Use SSH keys for secure access
-   Store repositories in `/srv/git/`
-   Backup your repositories regularly
-   For multiple users, consider tools like Gitea or GitLab

-------------
