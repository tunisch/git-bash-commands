# Diff and History

This document explains how to inspect changes and view the commit history in Git.

---

## git log

Displays the commit history of the repository.

```gitbash
git log
```
---


## Each commit includes:

- Commit ID
- Author
- Date
- Commit message

This helps you understand how the project evolved over time.

---

## git diff

Shows differences between files.

**Working directory vs last commit (HEAD)**

```gitbash
git diff

```
**Staged changes vs last commit**
```gitbash
git diff --staged

```
---

## Comparing Commits

View differences between two commits:

```gitbash
git diff commit_id_1..commit_id_2

```
This is useful when:

- Investigating bugs
- Reviewing changes
- Understanding what was modified between versions

---

## HEAD Reference
`HEAD` represents the current commit.
Diff commands often compare changes against `HEAD` by default.

Understanding this reference makes diff outputs much clearer.

---

# 🇹🇷
# Diff ve Geçmiş (History)

Bu doküman, Git'te yapılan değişikliklerin nasıl inceleneceğini ve commit geçmişinin nasıl görüntüleneceğini açıklar.

---

## git log

Depodaki (repository) commit geçmişini gösterir.

```gitbash
git log
```

---

## Her commit şunları içerir:

* Commit ID
* Yazar (Author)
* Tarih (Date)
* Commit mesajı

Bu bilgiler, projenin zaman içinde nasıl geliştiğini anlamanıza yardımcı olur.

---

## git diff

Dosyalar arasındaki farkları gösterir.

**Çalışma dizini (working directory) ile son commit (HEAD) arasındaki farklar**

```gitbash
git diff
```

**Stage edilmiş (staged) değişiklikler ile son commit arasındaki farklar**

```gitbash
git diff --staged
```

---

## Commit'leri Karşılaştırma

İki commit arasındaki farkları görüntülemek için:

```gitbash
git diff commit_id_1..commit_id_2
```

Bu özellikle şu durumlarda faydalıdır:

* Hataları (bug) araştırırken
* Değişiklikleri gözden geçirirken
* Sürümler arasında neyin değiştiğini anlamak için

---

## HEAD Referansı

`HEAD`, mevcut (current) commit'i temsil eder.

Diff komutları varsayılan olarak çoğu zaman `HEAD` ile karşılaştırma yapar.

Bu referansı anlamak, diff çıktılarının çok daha net olmasını sağlar.

