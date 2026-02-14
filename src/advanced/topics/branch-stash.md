# Branch Operations and the Stash Concept (TR & EN)
---
## 🇬🇧  Branch Operations and the Stash Concept
- If you are working with a team, you make the expected changes on a new branch. Afterwards, you merge this branch with the main branch, which is master. In this lesson, we cover many topics related to branch operations.

- Sometimes, after committing, you write hundreds of lines of code. Then suddenly, you may need to make changes to a previous version of the code you wrote. In this case, you need to save the commands you wrote somewhere. In scenarios like this, git stash saves us from a very important problem.

If you are working with a team, you are expected to make changes on a **new branch**. After completing your development on this branch, you merge the branch you created with the **main branch**.

This section covers:
- Creating branches
- Switching branches
- Deleting branches
- Merging branches
- Handling merge conflicts
- Understanding and using stash

--- 
### 1. What is a Branch?
A branch allows you to work independently without affecting the main codebase.

---
### 2. Creating a Branch
```gitbash
git branch feature-login
```

✔️ Create + switch:
```gitbash
git checkout -b feature-login
```

✔️ Modern Git:
```gitbash
git switch -c feature-login
```
---

### 3. Switching Branches
```gitbash
git checkout feature-login
```

✔️ Modern Git:
```gitbash
git switch feature-login
```

---
### 4. Listing Branches
```gitbash
git branch
```

✔️ Remote branches:
```gitbash
git branch -r
```

✔️ All branches:
```gitbash
git branch -a
```

---
### 5. Deleting Branches
```gitbash
git branch -d feature-login
```

✔️ Force delete:
```gitbash
git branch -D feature-login
```

--- 
### 6. Merging Branches
Switch to main:
```gitbash
git checkout main
```

✔️ Merge:
```gitbash
git merge feature-login
```
----

### 7. Merge Conflicts
Conflicts occur when the same lines are changed in two branches.

✔️ Resolve by:
- Editing the file
- Removing conflict markers
- Saving
- Committing:
```gitbash
git add .
git commit -m "Resolve merge conflict"
```
---

### 8. Stash Concept
- Git stash: It saves the changes we've made since our last commit and brings them back when we need them.
Sometimes you need to temporarily save your changes without committing them. This is where git stash becomes extremely useful.

### 8.1 Creating a Stash
```gitbash
git stash
```

✔️ With message:
```gitbash
git stash push -m "Login form draft"
```


### 8.2 Listing Stashes
```gitbash
git stash list
```


### 8.3 Applying a Stash
```gitbash
git stash apply
```

✔️ Specific stash:
Changes are reverted to the desired state but are not removed from the list.
```gitbash
git stash apply stash@{1}
```


### 8.4 Deleting a Stash
```gitbash
git stash drop stash@{0}
```

✔️ Clear all:
```gitbash
git stash clear
```


### 8.5 Pop (Apply + Delete)
It goes back to the last commit and deletes the most recent change while doing so, and the changes do not appear in the list.
```gitbash
git stash pop
```

###  Modern Git

- Create a branch → git switch -c feature
- Switch branches → git switch feature
- Restore a file → git restore file.txt
- Restore staged changes → git restore --staged file.txt


---

### Modern Git vs Classic Git

| Action                | Classic Git (Legacy)           | Modern Git (Recommended)      |
|------------------------------|------------------------------|-----------------------------|
| Create + switch branch         | `git checkout -b feature`    | `git switch -c feature`     |
| Switch branches             | `git checkout feature`       | `git switch feature`        |
| Revert file to previous state  | `git checkout -- file.txt`   | `git restore file.txt`      |
| Undo staged changes         | `git reset HEAD file.txt`    | `git restore --staged file.txt` |
| Reset working directory   | `git checkout .`             | `git restore .`             |
| Modify commit content  | Same                         | Same (`git commit --amend`) |
| Delete / reset commit         | Same                         | Same (`git reset`)          |
| Stash operations              | Same                         | Same (`git stash`)          |

---

# 🇹🇷 Branch İşlemleri ve Stash Kavramı 
- Bir ekip ile beraber çalışıyorsanız sizden beklenen değişiklikleri oluşturacağınız yeni bir branch (dal) üzerinde yaparsınız. Daha sonrasında bu oluşturduğunuz branch’ i ana branch olan master ile birleştirirsiniz. İşte bu ders içerisinde branch işlemlerine dair birçok konuyu ele alıyoruz.

- Bazen Commit işlemi yaptıktan sonra yüzlerce satır komut yazarsınız. Sonra birden yazdığınız kodlardan önceki versiyon üzerinde değişiklik yapmanız gerekebilir. Bu durumda bu yazdığınız komutları bir yere saklamanız gerekir. İşte bu tarz senaryolarda git stash bizi çok önemli bir sorundan kurtarıyor.

Bir ekip ile beraber çalışıyorsanız, sizden beklenen değişiklikleri **yeni bir branch (dal)** üzerinde yapmanızdır. Bu branch üzerinde geliştirmelerinizi tamamladıktan sonra, oluşturduğunuz branch’i **ana branch (main)** ile birleştirirsiniz.

Bu bölümde aşağıdaki konuları ele alıyoruz:

- Yeni branch oluşturma  
- Branch’ler arasında geçiş  
- Branch silme  
- Branch birleştirme (merge)  
- Çakışmalar (conflicts)  
- Stash kavramı ve kullanım senaryoları  

---

## 1. Branch Nedir?

Branch, projede bağımsız bir çalışma alanı oluşturmanızı sağlar.  Ana kodu bozmadan yeni özellikler geliştirebilirsiniz.

---

## 2. Branch Oluşturma

```gitbash
git branch feature-login
```

✔️ Hem oluşturup hem geçmek için:
```gitbash
git checkout -b feature-login
```

✔️ Modern Git ile:
```gitbash
git switch -c feature-login
```

---
## 3. Branch’ler Arasında Geçiş
```gitbash
git checkout feature-login
```

✔️ Modern Git:
```gitbash
git switch feature-login
```

---
## 4. Branch Listeleme
```gitbash
git branch
```

✔️ Remote branch’ler:
```gitbash
git branch -r
```

✔️ Tümü:
```gitbash
git branch -a
```
---

## 5. Branch Silme
```gitbash
git branch -d feature-login
```

✔️ Zorla silme:
```gitbash 
git branch -D feature-login
```

---
## 6. Branch Birleştirme (Merge)
Önce ana branch’e geç:
```gitbash
git checkout main
```

✔️ Sonra merge et:
```gitbash
git merge feature-login
```

---
## 7. Çakışmalar (Conflicts)
Merge sırasında aynı satır iki branch’te değiştiyse conflict oluşur.

✔️ Çözüm adımları:
- Dosyayı aç
- <<<<<<<, =======, >>>>>>> işaretlerini temizle
- Düzeltilmiş halini kaydet
- Commit et:
```gitbash
git add .
git commit -m "Resolve merge conflict"
```

---

## 8. Stash Kavramı
- Git stash : En son ki yaptigimiz committen itibaren yaptigimiz degisiklikleri bir kosede saklayip ihtiyacimiz oldugu zamanda bunlari bize getirmeye yarar.
Bazen commit yapmadan geçici olarak değişiklikleri saklamak istersiniz.

**Örneğin:**

- Yüzlerce satır kod yazdınız
- Ama aniden başka bir branch’te acil bir düzeltme yapmanız gerekiyor
- Commit yapmak istemiyorsunuz
İşte bu durumda git stash hayat kurtarır.

---
## 8.1 Stash Oluşturma
```gitbash
git stash
```

✔️ Mesajlı stash:
```gitbash
git stash push -m "Login form draft"
```

---
## 8.2 Stash Listesini Görmek
```gitbash
git stash list
```

**Örnek çıktı:**
```gitbash
stash@{0}: On feature-login: Login form draft
stash@{1}: On main: Fix navbar
```

---
## 8.3 Stash Uygulama (Geri Getirme)
```gitbash
git stash apply
```

✔️ Belirli stash’i uygulamak:
Istenilen stashe geri gider degisiklikler uygulanir ama listeden silinmezler.
```gitbash
git stash apply stash@{1}
```
---

## 8.4 Stash Silme
```gitbash
git stash drop stash@{0}
```

✔️ Tüm stash’leri silmek:
```gitbash
git stash clear
```
---

## 8.5 Stash Pop (Uygula + Sil)
Son commit e geri gider ve giderken en son ki yapilan degisikligi siler ve listede degisiklikler gozukmez.
```gitbash
git stash pop
```

## Modern Git vs Classic Git

| İşlem / Action                | Klasik Git (Eski)           | Modern Git (Önerilen)      |
|------------------------------|------------------------------|-----------------------------|
| Branch oluştur + geç         | `git checkout -b feature`    | `git switch -c feature`     |
| Branch değiştirme            | `git checkout feature`       | `git switch feature`        |
| Dosyayı eski haline döndürme | `git checkout -- file.txt`   | `git restore file.txt`      |
| Staged değişiklikleri geri al| `git reset HEAD file.txt`    | `git restore --staged file.txt` |
| Çalışma dizinini sıfırlama   | `git checkout .`             | `git restore .`             |
| Commit içeriğini değiştirme  | Aynı                         | Aynı (`git commit --amend`) |
| Commit silme / reset         | Aynı                         | Aynı (`git reset`)          |
| Stash işlemleri              | Aynı                         | Aynı (`git stash`)          |

##  Modern Git

- Branch oluşturma → git switch -c feature
- Branch değiştirme → git switch feature
- Dosya geri alma → git restore file.txt
- Staged geri alma → git restore --staged file.txt



