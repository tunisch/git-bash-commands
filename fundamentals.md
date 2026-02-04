# Git Fundamentals

This document explains the core concepts of Git.

Understanding these fundamentals is essential before using Git commands.

---

## What is Git?

Git is a distributed version control system.

It allows developers to track changes in files, collaborate with others, and safely manage project history.

---

## Git File States

Git tracks files by moving them through different states.

### Untracked
Files that are newly created and not yet tracked by Git.

### Tracked
Files that Git is already tracking.
Tracked files can be modified, staged, or committed.

### Unstaged
Tracked files that have been modified but not added to the staging area.

### Staged
Files that are added to the staging area and ready to be committed.

### Deleted
Files that are removed from the working directory but still tracked by Git.

---

## Git Workflow (Lifecycle)

Git works in three main areas:

1. **Working Directory**  
   Where you edit and modify files.

2. **Staging Area**  
   Where you prepare changes before committing.

3. **Local Repository**  
   Where committed snapshots are stored.

Changes flow like this:

Working Directory → Staging Area → Local Repository

---

## Commit

A commit is a snapshot of the project at a specific point in time.

Each commit has a unique ID, which allows you to return to any previous version safely.

---

## HEAD

`HEAD` is a pointer that represents the current commit you are working on.

When you switch branches or commits, `HEAD` moves accordingly.

---

## Why These Concepts Matter

Without understanding these fundamentals:

- Commands feel confusing
- Mistakes are harder to fix
- Git becomes frustrating instead of powerful

Mastering these concepts makes Git predictable and safe to use.

# 🇹🇷 Türkçe

## Git Nedir?

Git, dağıtık bir versiyon kontrol sistemidir.  

Dosyalardaki değişiklikleri takip etmeyi, ekip halinde çalışmayı ve proje geçmişini güvenli şekilde yönetmeyi sağlar.

---

## Git Dosya Durumları

Git, dosyaları farklı durumlar arasında taşıyarak takip eder.

### Untracked (İzlenmeyen)
Yeni oluşturulmuş ve Git tarafından henüz takip edilmeyen dosyalardır.

### Tracked (İzlenen)
Git tarafından takip edilen dosyalardır.  
Bu dosyalar değiştirilebilir, staged edilebilir veya commit edilebilir.

### Unstaged (Hazırlanmamış)
Takip edilen ancak staging alanına eklenmemiş, değiştirilmiş dosyalardır.

### Staged (Hazırlanmış)
Staging alanına eklenmiş ve commit edilmeye hazır dosyalardır.

### Deleted (Silinmiş)
Çalışma dizininden silinmiş ancak Git geçmişinde hâlâ takip edilen dosyalardır.

---

## Git Çalışma Akışı (Yaşam Döngüsü)

Git üç ana alanda çalışır:

1. **Working Directory (Çalışma Dizini)**  
   Dosyaların düzenlendiği ve değişikliklerin yapıldığı alan.

2. **Staging Area (Hazırlık Alanı)**  
   Commit öncesinde değişikliklerin hazırlandığı alan.

3. **Local Repository (Yerel Depo)**  
   Commit’lerin kaydedildiği alan.

Değişikliklerin akışı şöyledir:

Working Directory → Staging Area → Local Repository

---

## Commit

Commit, projenin belirli bir andaki anlık görüntüsüdür.  

Her commit benzersiz bir kimliğe (ID) sahiptir ve bu sayede projede güvenli şekilde geçmişe dönülebilir.

---

## HEAD

`HEAD`, üzerinde çalışılan mevcut commit’i gösteren bir işaretçidir. 

Branch veya commit değiştirildiğinde `HEAD` de buna göre hareket eder.

---

## Bu Kavramlar Neden Önemli?

Bu temeller anlaşılmadan:

- Komutlar karmaşık gelir
- Hataları düzeltmek zorlaşır
- Git güçlü değil, sinir bozucu olur

Bu kavramlara hâkim olmak Git’i öngörülebilir ve güvenli hale getirir.
