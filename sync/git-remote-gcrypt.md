# Notes

[GNU Privacy Guard-encrypted git remote](https://github.com/spwhitton/git-remote-gcrypt)

## Install

```shell
apt install git-remote-gcrypt
```

## Usage

```shell
git init
git remote add cryptremote gcrypt::rsync://example.com:repo
git config remote.cryptremote.gcrypt-participants "KEY1 KEY2"
git config remote.cryptremote.gcrypt-publish-participants true
git pull cryptremote
``

Clone repository to new directory
```shell
git clone gcrypt::rsync://example.com:repo
```

Migrate exisiting repository to encrypted local repository
```
git init --base ~/git/gcrypt/repo.git
git remote set-url origin gcrypt::~/git/gcrypt/repo.git
git push --all
```

## Alternative SSH Port
See .ssh/config
```
Host example.com
  Hostname example.com
  Port XXXX
```

## See Also

* [DIY encrypted Git repository](https://daveparrish.net/posts/2018-06-12-DIY-encrypted-Git-repository.html)
* [Migrate Private GIT Repositories to GCrypt](https://www.alwaysrightinstitute.com/gcrypt/)
