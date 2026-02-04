# Remote Repository Operations

This document explains how to work with remote repositories.

Remote repositories allow you to share your code and collaborate with others.

---

## What is a Remote Repository?

A remote repository is a version of your project hosted on the internet
(e.g. GitHub, GitLab, Bitbucket).

Your local repository communicates with the remote repository using Git commands.

---

## git clone

Creates a local copy of a remote repository.

```gitbash
git clone repository_url
```
This command:

- Downloads the entire project
- Automatically sets the remote name as `origin`

---
## git remote

Manages connections to remote repositories.

Add a remote repository:
```gitbash
git remote add origin remote_url
```

List remote repositories:
```gitbash
git remote -v
```

--- 
## git push

Sends local commits to the remote repository.
```gitbash
git push origin main
```

- origin → remote repository name
- main → branch name

---
## main vs master

Older Git versions used master as the default branch.
Modern Git uses `main`.

Always check your branch name before pushing.


## Common Mistake

Trying to push before committing changes.
Git only pushes committed snapshots.

---

# 🇹🇷 
# Remote Repository İşlemleri

Bu doküman, remote repository’lerle nasıl çalışılacağını açıklar.

Remote repository’ler, kodunuzu paylaşmanızı ve başkalarıyla birlikte çalışmanızı sağlar.

---

## Remote Repository Nedir?

Remote repository, projenizin internet üzerinde barındırılan bir sürümüdür
(örneğin GitHub, GitLab, Bitbucket).

Yerel repository, Git komutları aracılığıyla remote repository ile iletişim kurar.

---

## git clone

Bir remote repository’nin yerel bir kopyasını oluşturur.

```gitbash
git clone repository_url
```

Bu komut:

* Projenin tamamını indirir
* Remote adını otomatik olarak `origin` olarak ayarlar

---

## git remote

Remote repository bağlantılarını yönetmek için kullanılır.

Remote repository eklemek için:

```gitbash
git remote add origin remote_url
```

Remote repository’leri listelemek için:

```gitbash
git remote -v
```

---

## git push

Yerel commit’leri remote repository’ye gönderir.

```gitbash
git push origin main
```

* origin → remote repository adı
* main → branch adı

---

## main ve master Arasındaki Fark

Eski Git sürümlerinde varsayılan branch adı `master` idi.
Modern Git sürümlerinde varsayılan branch adı `main` olarak kullanılır.

Push işleminden önce branch adını mutlaka kontrol edin.

---

## Sık Yapılan Hata

Commit atmadan push yapmaya çalışmak.
Git sadece commit edilmiş değişiklikleri remote repository’ye gönderir.
















