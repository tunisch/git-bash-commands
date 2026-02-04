# .gitignore

The `.gitignore` file tells Git which files or directories should be ignored
and not tracked in the repository.

---

## Why Use .gitignore?

Some files should not be included in version control because they are:
- Generated automatically
- Environment-specific
- Too large
- Sensitive

Common examples:
- Dependencies (node_modules)
- Build outputs (dist, build)
- Environment files (.env)
- IDE settings (.vscode)
- Log files
- System files (e.g. .DS_Store)

---

## Creating a .gitignore File

You can create a `.gitignore` file in the root directory of your project.

```gitbash
touch .gitignore
```
--- 
## Basic Usage

Each line in `.gitignore` represents a file or directory to ignore.

Ignore a directory:

```gitbash
node_modules/
dist/

```

Ignore files by extension:
```gitbash
*.log
```
Ignore a specific file:
```gitbash
.env

```
---

## Exception Rules

Use `!` to make an exception for a file.

```gitbash
!files/example.txt

```
⚠️ Important:

If a directory is already ignored, exceptions inside it will not work.

---

## Comments

Use `#` to add comments inside `.gitignore`.

```gitbash
# Ignore log files
*.log

```
---

## Already Tracked Files

If a file is already tracked by Git, adding it to .gitignore will not stop tracking it.

Solution:

```gitbash
git rm --cached file_name

```

---

# 🇹🇷 
---

# .gitignore

`.gitignore` dosyası, Git'e hangi dosya veya klasörlerin yok sayılacağını (takip edilmeyeceğini) söyler.

---

## .gitignore Neden Kullanılır?

Bazı dosyalar sürüm kontrolüne dahil edilmemelidir çünkü:

* Otomatik olarak üretilirler
* Ortama (environment) özeldirler
* Çok büyük olabilirler
* Hassas (gizli) bilgiler içerebilirler

Yaygın örnekler:

* Bağımlılıklar (node_modules)
* Build çıktıları (dist, build)
* Ortam dosyaları (.env)
* IDE ayarları (.vscode)
* Log dosyaları
* Sistem dosyaları (ör. .DS_Store)

---

## .gitignore Dosyası Oluşturma

Projenizin kök dizininde bir `.gitignore` dosyası oluşturabilirsiniz.

```gitbash
touch .gitignore
```

---

## Temel Kullanım

`.gitignore` içindeki her satır, yok sayılacak bir dosya veya klasörü temsil eder.

Bir klasörü yok saymak:

```gitbash
node_modules/
dist/
```

Dosya uzantısına göre yok saymak:

```gitbash
*.log
```

Belirli bir dosyayı yok saymak:

```gitbash
.env
```

---

## İstisna Kuralları

Bir dosya için istisna tanımlamak için `!` kullanılır.

```gitbash
!files/example.txt
```

⚠️ Önemli:

Bir klasör zaten yok sayılıyorsa, içindeki dosyalar için tanımlanan istisnalar çalışmaz.

---

## Yorum Satırları

`.gitignore` içinde yorum eklemek için `#` kullanılır.

```gitbash
# Log dosyalarını yok say
*.log
```

---

## Zaten Takip Edilen Dosyalar

Bir dosya Git tarafından zaten takip ediliyorsa, onu `.gitignore` içine eklemek takibi durdurmaz.

Çözüm:

```gitbash
git rm --cached dosya_adi
```
