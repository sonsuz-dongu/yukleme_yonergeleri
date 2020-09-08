# Ubuntu 20.04'de Python Geliştirme Ortamı


## Python Kurulumu
Ubuntu 20.04'de python kurmaya gerek yok çünkü python ön tanımlı olarak gelmekte.

**Terminali Açmak İçin:**  
<kbd>ctrl + alt + t</kbd>

**Python Shell İçin:**  
```sh 
$ python3
```
>Python 3.8.2 (default, Apr 27 2020, 15:53:34) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.


**Sürüm öğrenmek için:**  

```sh 
$ python3 -V
```
> Python 3.8.2



## Pip3 Kurulumu

**Kurulum İçin:**   

```sh 
sudo apt install python3-pip
```

**Sürüm  Kontrolü İçin:**   

```sh 
pip3 -V
```
> pip 20.0.2 from /usr/lib/python3/dist-packages/pip (python 3.8)  


**Sürümünü yükseltmek için:**   

```
sudo -H pip3 install --upgrade pip
```

## Virtualenv Kurulumu
**Kurulum İçin:**    
```sh 
sudo pip3 install virtualenv
```

**Versiyon Kontorolü için:**    

```sh 
virtualenv --version
```
>virtualenv 20.0.31 from /usr/local/lib/python3.8/dist-packages/virtualenv/__init__.py

### Git Kurulumu

**Kurulum İçin:**   
```sh 
sudo apt install git-all
```
**Versiyon Kontrolü için:**   
```sh 
git --version
```
>git version 2.25.1

**Global Ayarları yapalım**   

```sh 
git config --global user.email "sonsuz_dongu_youtube@hotmail.com"
git config --global user.name "Sonsuz Döngü"
```



**Global Ayarlarımıza Bakalım**   
```sh 
git config --list --global
```


### Visual Studio Code Kurulumu

[Visual Studio Code](https://code.visualstudio.com/) sitesine giderek **deb** paketini indirelim.   

Paketin indirildiği dizine gidelim.

```sh 
cd İndirilenler
```

Paketi kuralım, code_ çizgisinden sonra <kbd>tab</kbd> tuşu ile otomatik doldurma yaparak versiyonunu rahatça yazabiliriz.

```sh 
sudo dpkg -i code_1.44.2-1587059832_amd64.deb
```

**Python Extension'a Yükleme:**    
Search kısmına Python diyerek extension yükleyelim.

## Proje Oluşturma - Git Ekleme - Github'a Proje Ekleme
**Masaüstüne Gidelim:**
```sh 
cd ~/Desktop
```
**Linux Proje adında Dizin Oluşturalım:**
```sh 
mkdir linux_proje
```

**Dizine Girelim:**   
```sh 
cd linux_proje
```

**Sanal Ortam Oluşturma:**    
```sh 
virtualenv venv
```

**Sanal Ortamı Aktif Etme:**    
```sh 
source venv/bin/activate
```
**Deaktif Etmek İçin:**    
```sh 
deactivate
```

**Hangi paketlerin yüklü olduğunu anlamak için:**    

```sh 
pip freeze 
```

**Paketler yükleyelim:**   
```sh 
pip install requests # web istemcileri sağlama paketi
pip install pillow # resim işleme paketi
```

**Requirements.txt oluşturalım:**   
```sh 
pip freeze > requirements.txt
```

**Requirements.txt ile paket oluşturalım:**   
```sh 
pip install -r requirements.txt
```

**Git Ekleme:**   
```sh 
git init
```

**Gitignore Dosyası Ekleme:**    
[Python için gitignore dosyası](https://github.com/github/gitignore/blob/master/Python.gitignore)

**Dosya Oluşturma**  
first.py adında bir dosya oluşturalım.
```python
print('Hello World!')
```

**Dosyamızı Stage'e Ekleyelim:**   
```sh 
git add .
```
**Dosyamızı commit edelim:**   
```sh 
git commit -m "first commit"
```

**Çalışmamızı Github'a yükleyelim:**   
Github sayfasında new diyerek yeni bir repo oluşturalım.

```sh 
git remote add origin https://github.com/sonsuz-dongu/git.git
git branch -M master
git push -u origin master
```

