## KURS DOCKERA

### Część 1
#### Uruchomienie nowego kontenera na podstawie obrazu ubuntu
`docker run ubuntu ls -l`
![opis](images/utworzenieKon.png)

#### Wyświetlenie wersji jądra systemu operacyjnego
`docker run ubuntu uname -a`
![opis](images/uname.png)

#### Zmiana obrazu na inną dystrybucję Linuxa 
`docker run debian uname -a`
![opis](images/debian.png)

#### Uruchomienie kontenera bash 
`docker run --interactive --tty ubuntu bash`
![opis](images/bash.png)

Możemy robić różne operacje wewnątrz pliku
`ls -l`
![opis](images/ls-l.png)

#### Utworzenie pliku tekstowego, wypisanie zawartości pliku
` echo "skni" > skni.txt`
`cat skni.txt`
![opis](images/pliktxt.png)

#### Wyjście z basha za pomocą CTRL D

#### Sprawdzenie jakie mamy kontenery
`docker container ls -a`
![opis](images/kontenery.png)
`docker container ls`- te kontenery które cały czas działaja
#### Uruchomienie wyłączonego kontenera
`docker start affectionate_sinoussi`
![opis](images/uruchomienie.png)

#### Wykonanie polecenia wewnątrz działającego kontenera- odczytanie pliku poprzednio zapisanego
`docker exec 8756 cat skni.txt`
![opis](images/875.png)

### Część 2- obrazy
#### Tworzenie obrazu
`docker commit 8756 skni_img`
![opis](images/obraz.png)

### Wyświetlenie warstw w obrazie
`docker history skni_img`
`docker history ubuntu `
![opis](images/warstwy.png)

#### Na podstawie własnego obrazu stworzenie nowego kontenera
`docker run -it skni_img bash`
![opis](images/kontObr.png)

#### Zainstalowanie nowego programu w kontenerze
`apt update && apt install vim`
![opis](images/program.png)

#### Stworzenie nowego obrazu w którym mamy vim
`docker commit 5151 vim_img`
![opis](images/vim.png)
![opis](images/vimHistory.png)

### Docker Hub
#### Ściąganie obrazu alpine z docker hub i postgres
`docker run alpine ls -l`
`docker pull postgres`
![opis](images/alpinePostgres.png)

#### Wgrywanie obrazów na docker hub
`docker push skni_img`
oraz zmiana nazwy obrazu `docker tag skni_img juliakleinszmidt/obraz`
![opis](images/zmianaNazwa.png)

`docker push juliakleinszmidt/obraz`
![opis](images/wgranie.png)
![opis](images/dockerHub.png)

### Docker file
#### Kopiowanie plików z kontenera na komputer hosta
`docker cp elegant_ptolemy:/skni.txt .`
![opis](images/kopiowanie.png)

