# GIT Temel Komutları
<img width="550" height="218" alt="image" src="https://github.com/user-attachments/assets/c5dbbc47-2eff-48b2-8a1b-91e52bd9cec5" />

# Başlıca bilmemiz gereken bazı terimler;

- untracked (izlenmeyen): GIT tarafından henüz takip edilmeyen, yani yeni oluşturulmuş dosyaları ifade eder.
- unstaged (hazırlanmamış): Güncellenmiş ancak commit’lenmek için hazırlanmamış dosyaları ifade eder.
- staged (hazırlanmış): Commit’lenmeye hazır olan dosyaları ifade eder.
- deleted (silinmiş): Projeden silinmiş ama GIT üzerinden kaldırılmamış dosyaları ifade eder.

## git init
- Henüz versiyon kontrolü altında olmayan bir projenin dizininde, boş bir git deposu oluşturmak için kullanılır.

## git add
- Yeni eklenen veya üzerinde değişiklik yapılan dosyaları staged ortamına göndermek için kullanılır.
- Tek seferde bütün dosyaları eklemek için ise:
```gitbash
$ git add .  veya  $ git add *  veya   $ git add -A .
```
## git rm
- Staged ortamına eklenmiş bir dosyanın takibinin bırakılması yani untracked (izlenmeyen) hale getirilmesi sağlayan komuttur.
```gitbash
$ git rm  --cached <dosya veya klasor_name>
```
- Dosyayı klasörden silmek istiyorsak eğer, aşağıdaki komutu kullanılırız.
```gitbash
$ git rm <dosya veya klasor_name>
```
## git status
- Üzerinde çalışılan projenin o anki durumu hakkında bilgi verir. Yapılan değişiklikler, eklenen ve silinen dosyalar gibi bilgiler listelenir.
```gitbash
$ git status
git-status-1

On branch main -> Main branch'ınde olduğumuzu,
Changes to be commited -> Commit'lenmeye hazır değişiklikler olduğunu,
Modified: index.html -> Index.html dosyasında değişiklik yaptığımızı,
Deleted: styles.css -> styles.css dosyasını sildiğimizi,
```
```gitbash
git-status-2

Changes not staged for commit -> Üzerinde değişiklik yapılan ama staged ortamına gönderilmemiş dosyaları ifade eder.
Untracked files -> takibi yapılmayan dosyaları ifade eder.
```
## git commit
- Commit, staged ortamına alınan dosyaların Local Repository’e gönderilmesidir. En iyi uygulama yöntemi her kayıt sırasında yapılan değişiklikleri açıklayıcı bir mesaj eklemektir. Ayrıca her commit benzersiz bir kimliğe (unique ID) sahip olur. Bu sayede eski bir commit'e geri dönebilirsiniz ve herhangi bir kayıp yaşama ihtimaliniz kalmaz.
```gitbash
$ git commit -m "ilk commit mesajı"
Buradaki -m (message) mesaj anlamındadır.
```
## git log
- Projedeki commit geçmişini görüntülememizi sağlar. Bütün commit'ler, id'si, yazarı, tarihi ve mesajı ile beraber listelenir.

## git branch
Local veya remote repository üzerinde yeni bir branch (dal) eklemek, silmek veya listelemek için kullanılır.

- Projenize yeni bir branch eklemek için;
```gitbash
$ git branch <branch_name>
```
- *Tüm uzak ve yerel branch'lari listelemek için;
```gitbash
$ git branch -a
```
- Bir branch'ı silmek için;
```gitbash
$ git branch -d <branch_name>
```
## git checkout
- Branch’ler arası veya commit'ler arası geçiş yapmak istediğimizde kullanılır.

- Mevcutta var olan branch'a geçiş yapmak için;
```gitbash
$ git checkout <branch_name>
```
- Yeni bir branch oluşturup, bu branch'a geçiş yapmak için;
```gitbash
$ git checkout -b <branch_name>
```
- Commitler arası geçiş yapmak için: (Eski bir versiyona dönmek istediğimiz zaman)
```gitbash
$ git checkout <commit_ID>
```
## git merge
- Başka bir branch'da olan değişiklikleri, bulunduğumuz branch ile birleştirmek istediğimizde kullanılır.
```gitbash
$ git merge <branch_name>
```
## git clone
- Mevcut bir Remote Repository'de bulunan dosyaların bilgisayarımızda bir kopyasının oluşturulmasını sağlar.
```gitbash
$ git clone <remote_URL>
```
## git push
- Projemizde aldığımız commit'leri, remote repository'e gönderir.
```gitbash
$ git push origin master
```
- Burada bahsi geçen origin remote repository’nin kök dizinini belirtir ve sabit bir isimdir. master ise sizin çalıştığınız branch (dal)’ı belirtir.

- Henüz remote repository’niz yoksa aşağıdaki komut ile local deponuzu uzak sunucudaki depoya bağlayabilirsiniz.
```gitbash
$ git remote add origin http://uzak_deponun_adresi.git
```
## git diff
- Repository üzerinde yapılan değişikliklerden sonra dosyalar arasında oluşan farklılıkları göterir.

- Çalışma dizini ile repository (HEAD) arasındaki farklılıkları görmek için:
```gitbash
$ git diff HEAD
```
-- **İki commit arasındaki farklılıkları görmek için:
```gitbash
$ git diff <commit_id_1>..<commit_id_2>
```
- Çalışma dizini ve staged ortamı arasındaki farkları görmek için:
```gitbash
$ git diff --staged
```
# SETUP
- Configuring user information used across all local repositories
  
  ```gitbash
  git config --global user.name “[firstname lastname]”
  ```
  - set a name that is identifiable for credit when review version history
  ```gitbash
  git config --global user.email “[valid-email]”
  ```
  - set an email address that will be associated with each history marker
  ``` gitbash
  git config --global color.ui auto
  ```
  - set automatic command line coloring for Git for easy reviewing

# SETUP & INIT
- Configuring user information, initializing and cloning repositories
```gitbash
git init
```
- initialize an existing directory as a Git repository
```gitbash
git clone [url]
```
- retrieve an entire repository from a hosted location via URL

# STAGE & SNAPSHOT
- Working with snapshots and the Git staging area
```gitbash
git status
```
- show modified files in working directory, staged for your next commit
```gitbash
git add [file]
```
- add a file as it looks now to your next commit (stage)
```gitbash
git reset [file]
```
- unstage a file while retaining the changes in working directory
```gitbash
git diff
```
- diff of what is changed but not staged
```gitbash
git diff --staged
```
- diff of what is staged but not yet committed
```gitbash
git commit -m “[descriptive message]”
```
- commit your staged content as a new commit snapshot

# .gitignore Dosyası Ne İşe Yarar? Nasıl Kullanırız?

- .gitignore dosyası projemizin kök dizinine oluşturulan düz bir metin dosyasıdır. Adından anlaşıldığı gibi diyor ki beni göz ardı et. Daha doğrusu göz ardı etmek istediğin, local çalışma alanındaki takip edilmesini istemediğin, takım arkadaşların için gerekmeyen dosyaların varsa veya bu dosyaların boyutu reponuza atmanıza gerek olmayacak kadar büyük ölçekli ise buyur beni kullan diyor.

- Gel bu dosyaları .gitignore dosyasına koy ki GIT de senin bu dosyalarını artık takip etmesin. Üstelik bu işlemler yapılırken senin halihazırdaki dosyalarını da hiç bir şekilde etkilemesin. 

## Peki nedir bu tür dosyalar ?
- Paket yöneticisinden indirilen bağımlılıklar,
- image ve video dosyalarınız(dosya boyutları çok fazla olabilir)
- IDE eklentileri( örneğin .vscode)
- Sadece kendi çalışma alanınızda olması gereken başkaları tarafından görülmemesi gereken dosyalarınız (veritabanınıza ilişkin konfigürasyonlar)
- API anahtarları, kimlik bilgileri veya hassas bilgiler içeren dosyalar(.env)
- Çalışma dizinizdeki geçici dosyalar
- Log dosyaları
- Yararsız sistem dosyaları (örneğin MacOS işletim sisteminin .DS_Store dosyası )
- dist gibi oluşturulan dosyalar
- Veya herhangi bir dosyanız da olabilir.

## Nasıl oluşturulur?
- Reponuzu oluştururken verilen seçeneklerde add gitignore file dosyasına tıklayarak reponuzla beraber oluşturabilirsiniz. Aynı şekilde editörünüzde .gitignore şeklinde de oluşturabilirsiniz.

- Terminal kullanarak boyle yapariz:
```gitbash
$ touch .gitignore 
```
## Nasıl çalışır, nasıl kullanılmalı?
- .gitignore dosyasının her satırına takip edilmesini istemediğimiz dosyaları veya dizinleri yazarak göz ardı edebiliriz.

- Tabii bu dosyaları yazarken bize kolaylık sağlayan bazı formatlar var. İşte onlar:

**.env**
- Dizinleri ise klasörün sonuna `/` işareti ekleyerek  belirtiriz.  (node-modules/ dist/ logs/)
- `*` yıldız karakteriyle ise belirtilen ilk örnekte `.log` uzantısına sahip dosyaların tümünü, ikinci örnekte ise `files` klasör içerisindeki bütün dosyaları izlemeyi bırakacaktır. (.log files/)
- Eğer ki bir klasörümüzü içerisindeki bir dosya haricinde izlenmesini istemiyorsak `!` işareti ile bunu sağlayabiliriz. Bu örnekte `files` klasörü içerisindeki `example.txt` haricindeki dosyalar izlenmeyecektir. Files klasörü içerisindeki sadece **example.txt** git akışında görülecektir.(!files/example.txt)
- - Yukarıdaki örnekte dikkat edilmesi gereken önemli bir ayrıntıyı açıklayacak olursak eğer ki daha öncesinde `files` klasörü `.gitignore` dosyasına eklenmişse sonrasında ise `!`  içerisindeki dosya ile işlem yapmak işe **yaramayacaktır.**(files/ !files/example.txt)
- `.gitignore` dosyasında yorum satırı oluşturmak için ise `#` karakteri kullanılır.
 
Kullanımından da bahsettiğimize göre gelelim dikkat edilmesi gereken hususlara...

## Neye dikkat etmeliyim?

- Eğer projenizi `git add .` veya `git commit ` etmişseniz sonrasında  `.gitignore`  dosyasına eklemek istediğiniz dosyayı ekleseniz de bu işlem gerçekleşmeyecektir ve o dosyanız reponuzda hala GIT ile takip edilecektir. Tabi her şeyin bir çözümü olduğu gibi bu sorunu da çözmenin bir yolu var. İşte o çözüm .

```bash
$ git rm --cached FILENAME
```

https://education.github.com/git-cheat-sheet-education.pdf
