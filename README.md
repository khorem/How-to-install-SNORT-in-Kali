# How-to-install-SNORT-in-Kali
Guide d'installation de SNORT sous kali

## ✨ Backup kali's sources.list

```bash
$ mv /etc/apt/sources.list /etc/apt/sources.list.bak
```

<br />

### 👉 Remove updates 

```bash
$ find /var/lib/apt/lists -type f -exec rm {} \;
```

<br />

### 👉 Change sources.list content

```bash
$ sudo nano /etc/apt/sources.list
```
Paste content given below
> 
deb [arch=arm64] http://ports.ubuntu.com/ubuntu-ports focal main restricted universe multiverse
deb [arch=arm64] http://ports.ubuntu.com/ubuntu-ports focal-updates main restricted universe multiverse
deb [arch=arm64] http://ports.ubuntu.com/ubuntu-ports focal-security main restricted universe multiverse
deb [arch=i386,amd64] http://us.archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse
deb [arch=i386,amd64] http://us.archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb [arch=i386,amd64] http://security.ubuntu.com/ubuntu focal-security main restricted universe multiverse

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

<br />

### 👉 Add the specified public keys

```bash
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3B4FE6ACC0B21F32
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 871920D1991BC93C
```

<br />

### 👉 Update

```bash
$ sudo apt update
$ sudo apt install snort
```

<br />

