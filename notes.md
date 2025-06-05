 # 📓 Linux DevOps Notes

Notatki z kursu: *The Linux Command Line Bootcamp* by Colt Steele  

## 📁 1 – Podstawy terminala

Podstawowe narzędzia:
https://ubuntu.com/download/desktop
https://www.virtualbox.org/wiki/Downloads

## 📁 2 – Podstawy komend
**man** ncal - wyświetli co robi komenda, opis oraz listę opcji (spacja przewija pełną stronę w terminalu)
nie wszystkie komendy mają man! - dla wbudowanych w shell należy użyć komendy *help*


opcje  [ ] - są to opcje niekonieczne (nie trzeba ich podać)
opcje bez [ ] - są to opcje konieczne - trzeba je podać
opcje z ... - można podać ich wiele

**man man** wyświetli opcje dla manuala 

## 📁 3 –  komendy

typy komend: 
**type** pokazuje typ komendy
* executable program /bin, /usr/bin, /usr/local/bin - binary files
* built-in shell command - part of the shell
* shell function
* an alias

  
**which** - lokalizuje komende 

**xdg-open** - otwiera graficznego eksplorera plików dla np root (xdg-open /) /root ~home 

**pwd** - wyświetla aktualną lokalizację np (/home/santi) 

**ls** - wyświetla zawartość lokalizacji 

**touch** - tworzy nowy plik 

**nano 'plik'** - otwiera plik w celu edycji albo go tworzy - ta sama komenda z nowym plikiem np. nano list.txt

**rm** - usuwa pliki bezpowrotnie, (-d usuwa puste foldery, -r usuwa wszystko razem z folderem) 
**rmdir** - usuwa puste foldery 

