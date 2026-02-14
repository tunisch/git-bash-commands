# 📄 Commit, Diff, Log, Amend — TR & EN (Bilingual Documentation)
---
## 🇬🇧 Commit, Diff, Log, Amend (English)
Git uses commits to save your changes as a version in the project history. This document explains all essential and advanced commit operations.

### 1. What is a Commit?
A commit saves your current changes as a version snapshot.

✔️ Creating a commit
```gitbash
git add .
git commit -m "Message"
```
---
### 2. Viewing Commit History (git log) and to get the commit ID 

✔️ Basic log
```gitbash
git log
```

✔️ To go to the desired commit in the list 

```gitbash
git log -n <1,2,3..>
```

✔️ One-line summary

```gitbash
git log --oneline
```

✔️ Graph view
```gitbash
git log --oneline --graph --decorate --all
```

---

### 3. Viewing Differences (git diff)
✔️ Working directory vs last commit
```gitbash
git diff
```

✔️ Staged changes vs last commit
```gitbash
git diff --staged
```

✔️ Compare two commits
```gitbash
git diff <commit1-id> <commit2-id> <file_name>
```
---

### 4. Reverting a Commit (git revert)
`revert` creates a new commit that undoes a previous commit.
```gitbash
Run `git log`, copy the hash code of the commit you want to revert, then perform the revert and write the hash code next to it. 
git revert <commit-id>
```

---

### 5. Deleting Commits (git reset)
⚠️ Warning: reset rewrites history.

✔️ Remove last commit (keep changes)
```gitbash
git reset --soft HEAD~1
```

✔️ Remove last commit (unstage changes)
```gitbash
git reset --mixed HEAD~1
```

✔️ Remove last commit completely
```gitbash
git reset --hard HEAD~1
```

✔️ Used to delete the last commit
This command always targets the last commit.
- HEAD = the commit you are currently on
- HEAD~1 = the previous commit
- HEAD~2 = two commits ago
- HEAD~3 = three commits ago

---

### 6. Changing Commit Message (git commit --amend)

✔️ Change message
```gitbash
git commit --amend -m "New message"
```

✔️ Add forgotten file
```gitbash
git add file.txt
git commit --amend
```

---

### 7. Editing Commit Content
```gitbash
git add .
git commit --amend
```
---

### 8. Summary Table

| Action                  | Command                 |
|-------------------------|-------------------------|
| View commit history     | `git log`               |
| View differences        | `git diff`              |
| Revert commit           | `git revert`            |
| Delete commit           | `git reset`             |
| Change commit message   | `git commit --amend`    |

---

## 🇹🇷 Commit, Diff, Log, Amend (Türkçe)
Git’te yaptığınız değişiklikleri bir versiyon olarak kaydetmek için commit işlemi yapılır. Bu dokümanda commit ile ilgili tüm temel ve ileri seviye konuları ele alıyoruz.

### 1. Commit Nedir?
Commit, çalışma dizininde yaptığınız değişiklikleri kalıcı bir versiyon olarak kaydetmenizi sağlar.
✔️ Commit oluşturma
```gitbash
git add .
git commit -m "Mesaj"
```

---
### 2. Commit Listesini Görmek (git log) ve commit id alabilmek icin 
✔️ Basit log
```gitbash
git log
```

✔️ Istenilen siradaki kayita gitmek icin 

```gitbash
git log -n <1,2,3..>
```

✔️ Tek satırlık özet
```gitbash
git log --oneline
```

✔️ Grafik görünümü
```gitbash
git log --oneline --graph --decorate --all
```

---
### 3. Commit Farklarını Görmek (git diff)
✔️ Çalışma dizini ile son commit arasındaki fark
```gitbash
git diff
```

✔️ Staged dosyalar ile son commit arasındaki fark
```gitbash
git diff --staged


✔️ İki commit arasındaki fark
```gitbash
git diff <commit1-id> <commit2-id> <dosya_adi>
```
---

### 4. Commit Geri Alma (git revert)
`revert`, geçmişteki bir commit’i silmeden, onu geri alan yeni bir commit oluşturur.
```gitbash
git log `yapilir oradaki geri alinmasi istenen commitin hash code u kopyalanip sonra revert yapilir ve yapilirken hash coduda yanina yazilir` 
git revert <commit-id>
```

---
### 5. Commit Silmek (git reset)
⚠️ Dikkat: reset geçmişi değiştirir.

✔️ Son commit’i silmek (değişiklikleri korur)
```gitbash
git reset --soft HEAD~1
```

✔️ Son commit’i silmek (unstaged yapar)
```gitbash
git reset --mixed HEAD~1


✔️ Son commit’i tamamen silmek
```gitbash
git reset --hard HEAD~1
```

✔️ Son commit’i silmek için kullanılır
Bu komut her zaman son commit’i hedef alır.
- HEAD = bulunduğun commit
- HEAD~1 = bir önceki commit
- HEAD~2 = iki commit önce
- HEAD~3 = üç commit önce

---

### 6. Commit Mesajını Değiştirmek (git commit --amend)
✔️ Mesajı değiştirmek
```gitbash
git commit --amend -m "Yeni mesaj"
```

✔️ Unutulan dosyayı eklemek
```gitbash
git add dosya.txt
git commit --amend
```

---

### 7. Commit İçeriğini Değiştirmek
```gitbash
git add .
git commit --amend
```
---

### 8. Özet Tablo

| Action                     | Command                 |
|----------------------------|-------------------------|
| Commit listesi             | `git log`               |
| Commit farkları            | `git diff`              |
| Commit geri alma           | `git revert`            |
| Commit silme               | `git reset`             |
| Commit mesajı değiştirme   | `git commit --amend`    |











