# Basic Git Commands

This document covers the most commonly used Git commands for daily work.
These commands form the core workflow of Git.

---

## git init

Initializes a new Git repository in the current directory.
It creates a hidden `.git` folder that Git uses to track changes.

```gitbash
git init
```
---

## git status

Displays the current state of the working directory and staging area.
It shows modified, staged, and untracked files.

```gitbash
git status
```

---

## git add

Adds new or modified files to the staging area.

Add a specific file:

```gitbash
git add file_name
```
Add all changes:

```gitbash
git add .

```

---

## git rm

Removes files from Git tracking.

Remove a file but keep it locally: Remove a file completely:

```gitbash
git rm --cached file_name

```

Remove a file completely:
```gitbash
git rm file_name
```

---

## git commit

Saves staged changes to the local repository as a new snapshot.

```gitbash
git commit -m "descriptive commit message"

```
Each commit has a unique ID and represents a stable version of the project.

---
## git reset (basic)

Removes files from the staging area without deleting changes.

```gitbash
git reset file_name
```
This is useful when you staged a file by mistake.


# 🇹🇷 

# Temel Git Komutları

Bu doküman, günlük çalışmalarda en sık kullanılan Git komutlarını kapsar.
Bu komutlar Git’in temel çalışma akışını oluşturur.

---

## git init

Bulunulan dizinde yeni bir Git repository başlatır.
Git’in değişiklikleri takip etmesi için gizli bir `.git` klasörü oluşturur.

```gitbash
git init
```

---

## git status

Çalışma dizini ve staging alanının güncel durumunu gösterir.
Değiştirilmiş, staged edilmiş ve izlenmeyen dosyaları listeler.

```gitbash
git status
```

---

## git add

Yeni veya değiştirilmiş dosyaları staging alanına ekler.

Belirli bir dosyayı eklemek için:

```gitbash
git add dosya_adi
```

Tüm değişiklikleri eklemek için:

```gitbash
git add .
```

---

## git rm

Dosyaları Git takibinden kaldırmak için kullanılır.

Dosyayı silmeden sadece Git takibinden çıkarmak için:

```gitbash
git rm --cached dosya_adi
```

Dosyayı tamamen silmek için:

```gitbash
git rm dosya_adi
```

---

## git commit

Staging alanındaki değişiklikleri yerel repository’ye yeni bir kayıt olarak kaydeder.

```gitbash
git commit -m "aciklayici commit mesaji"
```

Her commit benzersiz bir kimliğe (ID) sahiptir ve projenin kararlı bir sürümünü temsil eder.

---

## git reset (temel)

Dosyaları staging alanından çıkarır ancak yapılan değişiklikleri silmez.

```gitbash
git reset dosya_adi
```

Yanlışlıkla staged edilen dosyaları geri almak için kullanılır.
