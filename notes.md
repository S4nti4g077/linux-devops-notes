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

**mv plik [source] [destination]** - przenosi folderyq ; a w plikach zmienia nazwe - przenosi plik z dobby.txt do tools.txt

**cp <source><destination>** - kopiuje 

**history** - pokazuje historie komend z numerami **!numer** - wykonuje komende z historii

**cat** - czyta zawartość pliku lub kilku plików (pokazuje zawartość) CAŁĄ OD RAZU

**less** - pokazuje zawartość pliku ale tylko po 1 stronie (jak plik jest duży to lepsza opcja)

**tac** - pokazuje zawartość pliku ale od ostatniej do pierwszej linijki (odwraca kolejność)

**rev** - Pokazuje zawartość pliku ale każde słowo jest odwrócone np (black -> kcalb)

**head / tail** - pokazuje zawartość pierwszych / ostatnich 10 (domyślnie 10 albo więcej jak wpiszemy N) linijek w pliku [ **-f** jest opcją która "słucha" zmian pliku i pokazuje cały czas ostatnie 10, jest to użyteczne do czytania logów] 

**wc** - pokazuje liczbę: linii, słów, byte'ów

## 📁 4 –  przydatne skróty klawiszowe

**ctrl-L** - clear - czyści terminal

**ctrl-a i ctrl-e** - przeskakuje kursor na początek / koniec

**alt-f i alt-b** - przeskakuje kursor 1 słowo w przód / tył

**ctrl-k ctrl-u** usuwa wszystko co za / przed kursorem
