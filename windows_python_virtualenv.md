# Windows Ortamına Python ve Virtualenv Kurma
##  Windows Ortamına Python Kurma
### İndirme
İlk önce https://www.python.org/downloads/windows/ adresine gidiyoruz. 
Son sürüm olan **Python 3.8.5** başlığının altındaki:
- **Download Windows x86-64 executable installer** 

Bağlantısını tıklayarak **64-bitlik** sürümünü indiriyoruz.

### Kurma
İndirmiş olduğumuz kurulum dosyasını çalıştıralım.
- Kurulumuzun ilk aşamasında 
**-------Önemli--------** 
[x] Add Python 3.8 to Path
kısmını işaretlemeliyiz. Yoksa Path ayarlarını elimizle yapmak zorunda kalırız. 

- **Install now** diyerek kuruluma devam edebiliriz.
- **Close** diyerek kurulumu tamamlayabiliriz.

### Çalıştırma
Arama kutusuna **cmd** yazarak **Komut İstemini** çalıştıralım

**Sürüm öğrenmek için:**
```sh
python -V
```
- Python 3.8.5

**Python Shelle ulaşmak için:** 
```sh
python
```

- Python 3.8.5 (tags/v3.8.5:580fbb0, Jul 20 2020, 15:57:54) [MSC v.1924 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.

**Shellden çıkmak için ise:**
```python
exit()
```

### Paket Yöneticisi

```sh
pip -V
```
- pip 20.1.1 from c:\users\user\appdata\local\programs\python\python38\lib\site-packages\pip (python 3.8)
- 
**Örnek Paket Kurulumu:**
```sh
pip install requests
```

**Pip Sürümünü Yükseltme**
```sh
python -m pip install --upgrade pip
```

**Versiyon Öğrenme**
```sh
pip -V
```

## Windows Ortamına Virtualenv Kurma
**Kurulum**
```sh
pip install virtualenv
```

**Versiyon Kontrol**
```sh
virtualenv --version
```
- virtualenv 20.0.31 from c:\users\user\appdata\local\programs\python\python38\lib\site-packages\virtualenv\__init__.py


**Dizine Virtualenv Kurulumu**
```sh
virtualenv venv
```

**Virtualenv'i Aktif Etme**
```sh
venv\Scripts\activate
```

**Virtualenv'i Deaktif Etme**
```sh
deactivate
```

**Sanal Ortama Kütüphaneler Yükleme**
```sh
pip install requests
```
```sh
pip install Pillow
```
```sh
pip install BeautifulSoup4
```
**Sanal Ortamdaki Kütüphaneleri Listeleme**
```sh
pip freeze
```

**Gereksinim Dosyası Oluşturma**
```sh
pip freeze > requirements.txt
```

**Gereksinim Dosyasından Kütüphane Yükleme**
```sh
pip install -r requirements.txt
```
