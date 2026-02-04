# Branching in Git

Branches allow you to work on different versions of a project independently.
They are one of Git’s most powerful features.

---

## What is a Branch?

A branch is a separate line of development.
It allows you to make changes without affecting the main codebase.

The default branch is usually called `main`.

---

## git branch

Lists, creates, or deletes branches.

List all local branches:
```gitbash
git branch
```

---

## Create a new branch:
```gitbash
git branch branch_name
```
Delete a branch:
```gitbash
git branch -d branch_name
```

---

## git checkout
Switches between branches or commits.
Switch to an existing branch:
```gitbash
git checkout branch_name
```
Create and switch to a new branch:
```gitbash
git checkout -b new_branch_name
```
---

## git merge

Combines changes from one branch into another.
```gitbash
git merge branch_name
```
This command should be run on the branch that will receive the changes.

---
## Best Practice

- Create a new branch for each feature or experiment
- Merge only tested and stable branches into `main`
- Delete branches that are no longer needed

---

# 🇹🇷 

# Git’te Branch Yapısı

Branch’ler, bir projenin farklı sürümleri üzerinde birbirinden bağımsız çalışmanı sağlar.
Git’in en güçlü özelliklerinden biridir.

---

## Branch Nedir?

Branch, ayrı bir geliştirme hattıdır.
Ana kod tabanını etkilemeden değişiklik yapmanı sağlar.

Varsayılan branch genellikle `main` olarak adlandırılır.

---

## git branch

Branch’leri listelemek, oluşturmak veya silmek için kullanılır.

Yerel branch’leri listelemek için:

```gitbash
git branch
```

---

## Yeni bir branch oluşturmak:

```gitbash
git branch branch_adi
```

Bir branch’i silmek için:

```gitbash
git branch -d branch_adi
```

---

## git checkout

Branch’ler veya commit’ler arasında geçiş yapmak için kullanılır.

Mevcut bir branch’e geçmek için:

```gitbash
git checkout branch_adi
```

Yeni bir branch oluşturup ona geçmek için:

```gitbash
git checkout -b yeni_branch_adi
```

---

## git merge

Bir branch’teki değişiklikleri başka bir branch ile birleştirir.

```gitbash
git merge branch_adi
```

Bu komut, değişiklikleri alacak olan branch üzerinde çalıştırılmalıdır.

---

## En İyi Uygulamalar

* Her özellik veya deneme için yeni bir branch oluştur
* Sadece test edilmiş ve kararlı branch’leri `main` branch’ine birleştir
* Artık ihtiyaç duyulmayan branch’leri sil
