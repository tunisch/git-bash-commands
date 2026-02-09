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

**📌 What Should Go Into .gitignore**

(From Elementary to Professional — Full Guide)

The `.gitignore` file defines which files and directories Git should ignore. Below is a complete, structured guide showing what you should typically include — starting from the basics and progressing to professional‑level setups.

**🟦 1. Elementary Level — The Absolute Minimu**

```gitignore
# System files
.DS_Store
Thumbs.db

# Logs
*.log
logs/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Environment / secrets
.env
.env.local
.env.*.local

# Dependency directories
node_modules/
```

**Why these?**

They are generated automatically, contain secrets, or can be recreated at any time.


**🟩 2. Intermediate Level — Language & Tool Specifi**
Node.js / Frontend

```gitignore
# Dependencies
node_modules/

# Build outputs
dist/
build/
out/

# Package managers
package-lock.json
yarn.lock
pnpm-lock.yaml

# Testing
coverage/
.nyc_output/

# Tools
.eslintcache
.stylelintcache
```

Java / Maven / Gradle

```gitignore
# Build outputs
target/
build/
out/

# IDE files
*.iml
.idea/
.project
.classpath
.settings/

# Logs
*.log

# JVM crash logs
hs_err_pid*
replay_pid*
```

🟧 3. Advanced Level — Editor, IDE & OS Nois

```gitignore
# VS Code
.vscode/
.history/
*.code-workspace

# JetBrains / IntelliJ
.idea/
*.iml
*.iws
out/

# Eclipse
.project
.classpath
.settings/

# macOS
.DS_Store
.AppleDouble
.LSOverride

# Windows
Thumbs.db
Desktop.ini
$RECYCLE.BIN/
```

🟥 4. Professional Level — Environment, Security & Frameworks
```gitignore

# Environment-specific configs
.env
.env.local
.env.development
.env.production
.env.test

# Local override configs
config.local.*
*.local.json
*.local.yml

# Cache directories
.cache/
.tmp/
temp/
tmp/

# Framework-specific
.next/
.nuxt/
.svelte-kit/
.angular/
.storybook-static/

# Docker
*.pid
*.seed
docker-compose.override.yml

# Security / certificates
*.pem
*.key
*.crt
*.pfx
*.p12
```

Professional practice:

Track example configs (config.example.json) but ignore real ones (config.local.json)


**🔍 Finding `.gitignore` Templates for Any Language**

If you need a `.gitignore` file for a specific language or framework, you can easily find official templates online by searching for: “<language> .gitignore template” (e.g., “Java .gitignore template”, “Node.js .gitignore template”).



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
--- 

**📌 .gitignore Dosyasına Neler Eklenmeli**

(Temelden Profesyonele — Tam Rehber)

`.gitignore`, Git’in hangi dosya ve klasörleri yok sayacağını belirler. Aşağıda seviyeli bir şekilde hazırlanmış, doğrudan kullanabileceğin kapsamlı bir rehber bulunuyor.

🟦 1. Başlangıç Seviyesi — Olmazsa Olmazlar

```gitignore

# Sistem dosyaları
.DS_Store
Thumbs.db

# Log dosyaları
*.log
logs/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Ortam / gizli dosyalar
.env
.env.local
.env.*.local

# Bağımlılık klasörleri
node_modules/
```

**Neden?**

Otomatik üretilirler, gizli bilgi içerirler veya kolayca yeniden oluşturulabilirler.

🟩 2. Orta Seviye — Dile ve Araca Özel Kurallar

Node.js / Frontend

```gitignore
# Bağımlılıklar
node_modules/

# Build çıktıları
dist/
build/
out/

# Paket yöneticileri
package-lock.json
yarn.lock
pnpm-lock.yaml

# Test çıktıları
coverage/
.nyc_output/

# Araçlar
.eslintcache
.stylelintcache
```

Java / Maven / Gradle

```gitignore

# Build çıktıları
target/
build/
out/

# IDE dosyaları
*.iml
.idea/
.project
.classpath
.settings/

# Loglar
*.log

# JVM crash logları
hs_err_pid*
replay_pid*
```
🟧 3. İleri Seviye — Editör, IDE ve İşletim Sistemi Gürültüsü

```gitignore
# VS Code
.vscode/
.history/
*.code-workspace

# JetBrains / IntelliJ
.idea/
*.iml
*.iws
out/

# Eclipse
.project
.classpath
.settings/

# macOS
.DS_Store
.AppleDouble
.LSOverride

# Windows
Thumbs.db
Desktop.ini
$RECYCLE.BIN/
```
**Kural:**

Editör/OS tarafından otomatik üretiliyorsa `.gitignore’a` girmelidir.

🟥 4. Profesyonel Seviye — Ortam, Güvenlik ve Framework Dosyaları

```gitignore
# Ortama özel config dosyaları
.env
.env.local
.env.development
.env.production
.env.test

# Lokal override config’ler
config.local.*
*.local.json
*.local.yml

# Cache klasörleri
.cache/
.tmp/
temp/
tmp/

# Framework’e özel
.next/
.nuxt/
.svelte-kit/
.angular/
.storybook-static/

# Docker
*.pid
*.seed
docker-compose.override.yml

# Güvenlik / sertifika dosyaları
*.pem
*.key
*.crt
*.pfx
*.p12
```

**Profesyonel yaklaşım:**

config.example.json takip edilir, config.local.json yok sayılır.

🟪 5. Uzman İpuçları — Takım Standartları ve En İyi Pratikler

- .gitignore içinde açıklama satırları kullan.
- Public vs private config ayrımını koru.
- Hazır .gitignore şablonlarını temel al.
- Gizli hiçbir şeyi commit etme (API key, token, SSH key, sertifika).

**🔍 Her Dil İçin `.gitignore` Şablonu Bulma**

- Belirli bir dil veya framework için `.gitignore` oluşturmak istersen, internette “<dil> .gitignore template” şeklinde arama yaparak resmi ve güncel şablonlara kolayca ulaşabilirsin (örneğin: “Java .gitignore template”, “Node.js .gitignore template”).




