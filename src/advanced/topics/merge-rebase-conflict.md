# Merge vs Rebase Differences & Handling Conflicts  (EN & TR)

## 🇬🇧 | Merge vs Rebase Differences & Conflict Resolution
When working on two different branches, there are two main ways to combine them:  **merge** and **rebase**.  

Both achieve the same goal—bringing changes together—but they work very differently.

This section also covers **conflict resolution**, which happens when Git cannot automatically decide which change is correct.

---

## 1. What is Merge?

`git merge` combines two branches by creating a **new merge commit**.

**Example**
```bash
git switch main
git merge feature-login
```

✔️ What merge does
- Keeps full commit history
- Shows exactly when branches diverged
- Creates a merge commit
- Safe for team collaboration


✔️ Merge History Example
```bash
A --- B --- C --- D (main)
       \ 
        E --- F (feature)


After merge:
A --- B --- C --- D --- M (main)
       \           /
        E --- F ---
```
---

## 2. What is Rebase?
git rebase rewrites commit history by placing your commits on top of another branch.
✔️ Example
```bash
git switch feature-login
git rebase main
```

✔️ What rebase does
- Creates a linear history
- Removes merge commits
- Makes history cleaner
- Rewrites commit IDs (dangerous on shared branches)


✔️ Rebase History Example
```bash
Before:
A --- B --- C (main)
       \
        D --- E (feature)


After:
A --- B --- C --- D' --- E' (feature)
```

---

## 3. Merge vs Rebase Summary (EN)

| Feature / Behavior        | Merge                     | Rebase                         |
|---------------------------|---------------------------|--------------------------------|
| History style             | Non-linear (branching)    | Linear (clean)                 |
| Creates merge commit      | Yes                       | No                             |
| Rewrites history          | No                        | Yes                            |
| Safe for team use         | Yes                       | Only on local branches         |
| Recommended for           | Team collaboration         | Personal feature branches      |

---

## 4. What is a Conflict?
A conflict happens when:
- Two branches modify the same line
- Git cannot decide which version is correct
Example conflict markers:
```bash
<<<<<<< HEAD
Your changes
=======
Other branch changes
>>>>>>> feature-login
```
----

## Conflict Resolution Summary (EN)

| Step                     | Description                                      |
|--------------------------|--------------------------------------------------|
| 1. Detect conflict       | Git shows conflict markers in the file          |
| 2. Open the file         | Locate `<<<<<<<`, `=======`, `>>>>>>>`          |
| 3. Choose version        | Keep yours, theirs, or combine                  |
| 4. Clean markers         | Remove conflict markers and save                |
| 5. Mark resolved         | `git add .`                                     |
| 6. Complete operation    | Merge: `git commit` / Rebase: `git rebase --continue` |

---

## 5. How to Resolve Conflicts

✔️ Step 1 — Open the file

Find the conflict markers:
```bash
<<<<<<<
=======
>>>>>>>
```

✔️ Step 2 — Choose the correct version

You can keep:
- Your version
- Their version
- A combination

✔️ Step 3 — Remove conflict markers
Save the cleaned file.

✔️ Step 4 — Mark as resolved
```bash
git add .
```

✔️ Step 5 — Complete the merge or rebase

For merge:
```bash
git commit
```

✔️ For rebase:
```bash
git rebase --continue
```
---

## 🇬🇧 Advanced Git Topics — Summary Tables (English)
## Cherry-pick Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Apply a single commit onto another branch        |
| Command                     | `git cherry-pick <commit-id>`                    |
| Use case                    | Hotfix, selective commit transfer                |
| Rewrites history            | Yes (creates new commit ID)                      |
| Safe for team use           | Yes, if used carefully                           |

---

## Fast-forward Merge Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Move branch pointer forward without merge commit |
| Command                     | `git merge feature` (if no divergence)           |
| Creates merge commit        | No                                               |
| History style               | Linear                                           |
| Recommended for             | Simple feature merges                            |

---

## No-FF (No Fast-forward) Merge Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Force creation of merge commit                   |
| Command                     | `git merge --no-ff feature`                      |
| Creates merge commit        | Yes                                              |
| History style               | Non-linear                                       |
| Recommended for             | Team workflows, PR history clarity               |

---


## Interactive Rebase Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Edit, reorder, squash, or delete commits         |
| Command                     | `git rebase -i <commit-id>`                      |
| Rewrites history            | Yes                                              |
| Recommended for             | Cleaning commit history before merge             |

---

## Squash Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Combine multiple commits into one                |
| Command (rebase)            | `git rebase -i HEAD~3` → mark commits as `squash`|
| Command (merge)             | `git merge --squash feature`                     |
| Result                      | One clean commit                                 |

---

## Merge Strategies Summary (EN)

| Strategy     | Description                                      |
|--------------|--------------------------------------------------|
| recursive    | Default strategy for two-branch merges           |
| ours         | Keep current branch changes, ignore the other    |
| theirs       | Keep other branch changes (rarely used manually) |
| octopus      | Merge 3+ branches at once                        |

----

## Octopus Merge Summary (EN)

| Action / Behavior           | Description                                      |
|-----------------------------|--------------------------------------------------|
| Purpose                     | Merge multiple branches simultaneously           |
| Command                     | `git merge branch1 branch2 branch3`              |
| Use case                    | Large automated merges                           |
| Common?                     | No, very rare                                    |


# 🚫 Git Abort Guide (English Version)

## 1) Merge Abort
Explanation:

If a merge results in conflicts and you decide not to continue, this command cancels the merge and restores the repository to the state before the merge began.

**Command**
```bash
git merge --abort
```

---

## 2) Rebase Abort
Explanation:

If a rebase becomes complicated or produces conflicts you don’t want to resolve, this command cancels the entire rebase process and returns the repository to its pre-rebase state.

**Command**
```bash
git rebase --abort
```
---

## 3) Cherry-pick Abort
Explanation:

If a cherry-pick operation encounters conflicts and you want to stop, this command cancels the cherry-pick and resets the working directory.

**Command**
```bash
git cherry-pick --abort
```

---

## 🚫 Git Abort Commands (English)

| Operation | Abort Command | Description |
|-----------|----------------|-------------|
| Merge | `git merge --abort` | Cancels the ongoing merge and restores the repository to its pre-merge state. |
| Rebase | `git rebase --abort` | Cancels the entire rebase process and returns to the state before the rebase began. |
| Cherry-pick | `git cherry-pick --abort` | Cancels the cherry-pick operation and resets the working directory. |



---



# 🇹🇷 |  Merge ve Rebase Farkları. Conflict ile Başa Çıkmak

İki farklı branch üzerinde çalışırken, bu branch’leri birleştirmek için iki yöntem vardır: **merge** ve **rebase.**

Her ikisi de değişiklikleri bir araya getirir, ancak çalışma şekilleri tamamen farklıdır.

Bu bölümde ayrıca conflict çözümü konusunu da ele alıyoruz.

## 1. Merge Nedir?
git merge, iki branch’i yeni bir merge commit’i oluşturarak birleştirir.

**Örnek**
```bash
git switch main
git merge feature-login
```

✔️ Merge ne yapar?
- Tüm commit geçmişini korur
- Branch ayrılma noktalarını gösterir
- Merge commit oluşturur
- Ekip çalışması için güvenlidir

---

## 2. Rebase Nedir?
git rebase, commit geçmişini yeniden yazar ve commit’lerinizi başka bir branch’in en üstüne taşır.

**Örnek**
```bash
git switch feature-login
git rebase main
```

✔️ Rebase ne yapar?
- Daha temiz, çizgisel bir geçmiş oluşturur
- Merge commit’lerini kaldırır
- Commit ID’lerini değiştirir (dikkat!)
- Paylaşılan branch’lerde önerilmez

---

## 3. Merge vs Rebase Özet Tablosu (TR)

| Özellik / Davranış        | Merge                         | Rebase                        |
|---------------------------|-------------------------------|-------------------------------|
| Geçmiş yapısı             | Dallanmış (non-linear)        | Çizgisel (linear)             |
| Merge commit oluşturur    | Evet                          | Hayır                         |
| Geçmişi yeniden yazar     | Hayır                         | Evet                          |
| Ekip için güvenli         | Evet                          | Sadece lokal branch’lerde     |
| Önerilen kullanım         | Ekip çalışması                | Kişisel feature branch’leri   |

---

## 4. Conflict Nedir?

Conflict, iki branch aynı satırı değiştirdiğinde ve Git hangi versiyonun doğru olduğuna karar veremediğinde oluşur.

Örnek conflict işaretleri:
```bash
<<<<<<< HEAD
Sizin değişikliğiniz
=======
Diğer branch’in değişikliği
>>>>>>> feature-login
```

---


## Conflict Çözümü Özet Tablosu (TR)

| Adım                     | Açıklama                                         |
|--------------------------|--------------------------------------------------|
| 1. Conflict tespiti      | Git dosyada conflict işaretleri gösterir        |
| 2. Dosyayı aç            | `<<<<<<<`, `=======`, `>>>>>>>` satırlarını bul |
| 3. Versiyon seç          | Sizin, onların veya birleşik versiyon           |
| 4. İşaretleri temizle    | Conflict işaretlerini silip kaydedin            |
| 5. Çözümü işaretle       | `git add .`                                     |
| 6. İşlemi tamamla        | Merge: `git commit` / Rebase: `git rebase --continue` |

---

## 5. Conflict Nasıl Çözülür?

✔️ Adım 1 — Dosyayı aç

- Conflict işaretlerini bul:
```bash
<<<<<<<
=======
>>>>>>>
```

✔️ Adım 2 — Doğru versiyonu seç
- Sizin versiyonunuz
- Onların versiyonu
- İkisini birleştirme


✔️  Adım 3 — İşaretleri temizle
Dosyayı kaydedin.

✔️ Adım 4 — Çözümü işaretle
```bash
git add .
```

✔️ Adım 5 — İşlemi tamamla
Merge için:
```bash
git commit
```

✔️ Rebase için:
```bash
git rebase --continue
```

---

## 🇹🇷 Gelişmiş Git Konuları — Özet Tabloları (Türkçe)

## Cherry-pick Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Tek bir commit’i başka branch’e taşımak           |
| Komut                      | `git cherry-pick <commit-id>`                     |
| Kullanım alanı             | Hotfix, seçili commit aktarma                     |
| Geçmişi yeniden yazar      | Evet (yeni commit ID oluşturur)                   |
| Ekip için güvenli          | Evet, dikkatli kullanılırsa                       |


---

## Fast-forward Merge Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Merge commit oluşturmadan branch’i ileri almak    |
| Komut                      | `git merge feature` (ayrılma yoksa)               |
| Merge commit               | Hayır                                             |
| Geçmiş yapısı              | Çizgisel (linear)                                 |
| Önerilen kullanım          | Basit feature birleştirmeleri                     |

---

## No-FF Merge Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Merge commit’i zorunlu oluşturmak                 |
| Komut                      | `git merge --no-ff feature`                       |
| Merge commit               | Evet                                              |
| Geçmiş yapısı              | Dallanmış (non-linear)                            |
| Önerilen kullanım          | Ekip çalışması, PR geçmişinin korunması           |

---

## Interactive Rebase Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Commit’leri düzenlemek, sıralamak, birleştirmek   |
| Komut                      | `git rebase -i <commit-id>`                       |
| Geçmişi yeniden yazar      | Evet                                              |
| Önerilen kullanım          | Merge öncesi commit geçmişini temizlemek          |

---

## Squash Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Birden fazla commit’i tek commit’e indirmek       |
| Komut (rebase)             | `git rebase -i HEAD~3` → `squash`                 |
| Komut (merge)              | `git merge --squash feature`                      |
| Sonuç                      | Temiz, tek commit                                 |

---


## Merge Strategies Özeti (TR)

| Strateji     | Açıklama                                          |
|--------------|---------------------------------------------------|
| recursive    | İki branch merge’lerinde varsayılan strateji      |
| ours         | Mevcut branch’i korur, diğerini yok sayar         |
| theirs       | Diğer branch’i korur (manuel kullanım nadir)      |
| octopus      | 3+ branch’i aynı anda birleştirir                 |


---

## Octopus Merge Özeti (TR)

| İşlem / Davranış           | Açıklama                                          |
|----------------------------|---------------------------------------------------|
| Amacı                      | Birden fazla branch’i aynı anda merge etmek       |
| Komut                      | `git merge branch1 branch2 branch3`               |
| Kullanım alanı             | Büyük otomatik birleştirmeler                     |
| Yaygın mı?                 | Hayır, çok nadir                                  |


---

# 🚫 Git Abort Rehberi (TR–EN Bilingual)

### 1) Merge Abort
Açıklama:

Bir merge sırasında conflict çıktı ve devam etmek istemiyorsan, merge’i tamamen iptal eder ve repo’yu merge başlamadan önceki hâline döndürür.

🔧 Komut / Command
```bash
git merge --abort
```

---

### 2) Rebase Abort
Açıklama:

Rebase sırasında işler karıştıysa, tüm rebase sürecini iptal eder ve rebase başlamadan önceki commit’e geri döner.

🔧 Komut / Command
```bash
git rebase --abort
```

--- 

### 4) Cherry-pick Abort
Açıklama:

Cherry-pick sırasında conflict olursa ve devam etmek istemiyorsan, işlemi iptal eder.

🔧 Komut / Command
```bash
git cherry-pick --abort
```
---

### 🚫 Git Abort Komutları (Türkçe)

| İşlem | Abort Komutu | Açıklama |
|-------|--------------|----------|
| Merge | `git merge --abort` | Devam eden merge işlemini iptal eder ve repo’yu merge başlamadan önceki hâline döndürür. |
| Rebase | `git rebase --abort` | Rebase sürecini tamamen iptal eder ve rebase öncesi commit’e geri döner. |
| Cherry-pick | `git cherry-pick --abort` | Cherry-pick sırasında oluşan çatışmaları iptal eder ve işlemi geri alır. |


