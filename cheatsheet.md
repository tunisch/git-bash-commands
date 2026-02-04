# Git Cheatsheet

Quick reference for commonly used Git commands.

---

## Repository Setup

- Initialize a repository
```bash
git init
```
---

## Clone a remote repository
```gitbash
git clone URL

```

## Status & Staging

check repository status:

```gitbash
git status  
```

stage a file:

```gitbash
git add file  
```
stage all changes:

```gitbash
git add .       
```

unstage a file:

```gitbash
git reset file           
```
---

## Commit

commit staged changes:
```gitbash
git commit -m "message" 
```
view commit history:
```gitbash
git log                 
```
---

## Branching

list branches:
```gitbash
git branch
```               
create a branch:
```gitbash
git branch branch-name          
```
switch branch:
```gitbash
git checkout branch-name        
```
create & switch branch:
```gitbash
git checkout -b branch-name
```

merge a branch:
```gitbash
git merge branch-name         
```
---

## Remote

list remotes:
```gitbash
git remote -v     
```
Add a remote repository:
```gitbash
git remote add origin URL
```
Push commits to remote:
```gitbash
git push origin main     
```
---

## Diff
Show unstaged changes:
```gitbash
git diff       
```
Show staged changes:
```gitbash
git diff --st
```

Compare two commits:
```gitbash
git diff commitA..commitB
```

---

# 🇹🇷 
# Git Hızlı Başvuru (Cheatsheet)

Sık kullanılan Git komutları için hızlı referans.

---

## Repository Oluşturma

* Yeni bir repository başlatma

```bash
git init
```

---

## Uzak (Remote) Repository Klonlama

```gitbash
git clone URL
```

---

## Durum & Stage İşlemleri

Repository durumunu kontrol etme:

```gitbash
git status
```

Bir dosyayı stage etme:

```gitbash
git add file
```

Tüm değişiklikleri stage etme:

```gitbash
git add .
```

Bir dosyayı staged durumdan çıkarma:

```gitbash
git reset file
```

---

## Commit

Stage edilmiş değişiklikleri commit etme:

```gitbash
git commit -m "mesaj"
```

Commit geçmişini görüntüleme:

```gitbash
git log
```

---

## Branch İşlemleri

Branch'leri listeleme:

```gitbash
git branch
```

Yeni bir branch oluşturma:

```gitbash
git branch branch-name
```

Branch değiştirme:

```gitbash
git checkout branch-name
```

Branch oluşturup geçme:

```gitbash
git checkout -b branch-name
```

Branch birleştirme (merge):

```gitbash
git merge branch-name
```

---

## Remote İşlemleri

Remote'ları listeleme:

```gitbash
git remote -v
```

Remote repository ekleme:

```gitbash
git remote add origin URL
```

Commit'leri remote'a gönderme:

```gitbash
git push origin main
```

---

## Diff

Stage edilmemiş değişiklikleri gösterme:

```gitbash
git diff
```

Stage edilmiş değişiklikleri gösterme:

```gitbash
git diff --st
```

İki commit'i karşılaştırma:

```gitbash
git diff commitA..commitB
```
