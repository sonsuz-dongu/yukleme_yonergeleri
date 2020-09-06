# Windows Ortamına Git Kurulumu

Git kurulumu için https://git-scm.com/download/win adresine gidiyoruz.  
**64-bit Git for Windows Setup** kurulum dosyasını indiriyoruz.     
   
   
Kurulum dosyamızı çalıştırıyoruz. Gerekli ayarları istediğimiz şekilde ise **next** veya ayar değişikliği yapmak istediğimizde ayarımızı yapıp **next** diyoruz.

**Adjusting your Path environment**    
Bu bölümde komut satırlarında unix komutlarının çalışması için aşağıdaki seçeneği seçiyoruz.   
[ x ] Use Git and optional Unix tools from the Command Prompt

Diğer ayarları da kendimize göre ayarladıktan sonra kurulumumuzu tamamlıyoruz.

**Git Ayarlarını Yapalım**   
Komut Satırına aşağıdaki ayarları yaparak kullanıcı ayarlarını yapalım.
```sh
git config --global user.name "Sonsuz Dongu"
```

```sh
git config --global user.email "sonsuz_dongu_youtube@hotmail.com"
```
Global ayarlara göz atalım
```sh
git config --list --global
```

**Bir proje oluşturarak Github'a yükleyelim**    
Diznimize git'i ekleyelim.

```sh
git init
```

Dosyamızı stage'e ekleyelim
```sh
git add first.py
```

Dosyamızı commit edelim
```sh
git commit -m "first commit"
```
  
**Çalışmamızı Github'a yükleyelim**   
Github sayfasında new diyerek yeni bir **repo** oluşturmaya başlayalım.  
Repomuzun adını, görünürlük ayarlarını, ve diğer ayarlarını yaptıktan sonra oluşturalım.
```sh
git remote add origin https://github.com/sonsuz-dongu/git.git
```
```sh
git branch -M master
```
```sh
git push -u origin master
```

Kullanıcı işlemlerini hallettikten sonra projemiz githuba yüklenmesi gerekir.
