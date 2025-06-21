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

**touch** - tworzy nowy plik (można utworzyć plik z datą modyfikacji zaległą - **touch last_week -d "1 week ago"**)

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

**sort** - sortuje alfabetycznie (albo -r odwrotnie) / liczby sortuje po pierwszej cyfrze (chyba że -n , wtedy posortuje liczby rosnąco), fajną opcją sortowania, jak jest kilka kolumn danych, jest opcja -k (np -nk2 - posortuje numerycznie po kolumnie 2) 

**tr** - tłumaczy albo usuwa znaki. Komenda potrzebuje standard input i wyrzuca do standard output. np. cat msg | tr a-z A-Z (zamieni zawartość pliku msg na duże litery) albo np **cat data.txt | tr -d a** usunie litery a

**wc** - liczy ilość słów - word count

**locate** - lokalizuje plik na komputerze np locate monday.txt

**find** - pokazuje pełne ścieżki (ls pokazuje dane pliki i foldery, a find całą ich zawartość) (-type f -ograniczy szukanie do plików) (-type -d - ograniczy szukanie do folderów) **(find ~/Desktop -iname "*.txt")** - wyszuka od pulpitu pliki .txt ale -iname jest niezależny od wielkości liter
**find -size +5G** wyszuka plików > 5GB **find -user santi** - wyszuka plików po userze
Wyszukiwanie przez **timestamp** - mtime (data modyfikacji - kiedy była zmiana w pliku) ctime (change time - kiedy była jakakolwiek zmiana - lokalizacji, nazwy itp) atime (access time - kiedy w jakikolwiek sposób plik był odczytany przez program lub komendą)
<find -amin +10> wyszuka po minutach, <find -atime +10> wyszuka access time wiecej niż 10h
można używać też -or ; -not (to samo co !) ; -and
**find -name "*chick*" -or -name "*kitty*";  
**-empty** wyszuka puste pliki

**exec** - w połączeniu z find - wykonuje komende dla wszystkich znalezionych plikóW: **find -type -f -name "*.html" -exec cp '{}' '{}_COPY' ';'** {} - to aktualna nazwa, musi być w '{}' bo inaczej ma inne znaczenie. Ten zestaw używamy do przenoszenia albo usuwania wszystkich pustych plików, albo nieużywanych itp

**grep** - wyszukuje w pliku danego słowa **grep "chicken" animals.txt** -i (wielkość liter nieistotna) -w (wyszuka konkretnie słowa np "cat" a nie "catheter") **-r wyszka w plikach danej lokalizacji! bardzo użyteczne** -c (count - liczy ile jest podanych słow / liter / znaków)

**Regex Grep** . - single character
^ - start of a line (np zaczyna się "Ja,") 
$ - end of a line (np kończy sie "?")
[abc] - any character in the set
[^abc] - any char NOT in set
[A-Z] - characters in range
* - repeat previous expression 0 or more times
\- escape meta-characters

**Piping to Grep** - używa się żeby np zobaczyć konkretne procesy (jest ich bardzo dużo, a chcemy znaleźć konkretne) np. ps -aux | grep "sound" -i ; albo do wyszukiwania w manualu np. man grep | grep "count" -i

**chmod** - zmienia uprawnienia userów do plików [dział 7]

**chown** - zmienia do kogo należy plik [dział 7]

**printenv** - pokazuje środowisko dla aktualnego użytkownika

## 📁 4 –  przydatne skróty klawiszowe

**ctrl-L** - clear - czyści terminal

**ctrl-a i ctrl-e** - przeskakuje kursor na początek / koniec

**alt-f i alt-b** - przeskakuje kursor 1 słowo w przód / tył

**ctrl-k ctrl-u** usuwa wszystko co za / przed kursorem

## 📁 5 –  REDIRECTION

**>** - jeśli chcemy przekierować output danej komendy gdzieś indziej - np echo 'moo' > krowa.txt (wtedy w krowa.txt nadpisze się cały plik z wynikiem tej komendy) **>>** za to dopisze do pliku, a nie nadpisze całość.

**<** - przekierowuje plik 'zróbto.txt' do komendy np. cat < kurczaki.txt ; komenda słucha polecenia w pliku np .txt

**coś < coś innego > jeszce coś** - COMBO - input i output są przekierowane w tym samym czasie np cat < original.txt > output.txt (original.txt wyśle dane do komendy cat, a wynik będzie zapisany w output.txt)

**2>** - error redirection - przekierowuje potencjalny błąd gdzieś - np cat idontexist 2> errorlog.txt - będzie zapisywał błędy w errorlog.txt

**cat bees.txt ants.txt > insects.txt 2> error.txt** , a fancy opis jeśli chcemy error i output w tym samym miejscu **ls docs > output.txt 2>&1** a nowsze wersje basha obsługują komende **ls docs &> output.txt**, co też wyrzuci i błąd i wynik do output.txt

## 📁 6 - Piping

Przepuszczanie jednej komendy przez drugą np, **date | rev** - wyświetli odwróconą datę, są to 2 komendy. Przydatne do np: **ls /usr/bin -l | less** wyświetli pliki w bin, ale nie wszystkie na raz tylko po 1 stronie

**> vs |** - różnica polega na pliku - w **>** wynik zapisywany jest w pliku, a w **|** wynik jednej komendy jest przekazywany do następnej, nie ma żadnego pliku, za to możemy je połączyć

**tee** - są komendy, które potrzebują standard input, a chcemy użyć ich po danej komendzie albo chcemy zachować oba wyniki - wtedy używamy tee  np. **command1 | tee file.txt | command2** - command1 zapisze do pliku file.txt, a command2 wyrzuci w terminalu.
(du -ha /usr/bin | sort -h |tee sorted.txt| tail -3 ) wykona po kolei sortowanie (po drodze stworzy plik sorted.txt z tymi danymi ale przejdzie dalej i wyświetli w terminalu dopiero po tail -3 (czyli 3 ostatnie). Ta komenda tworzy plik z danymi "po drodze" do finalnego wyniku w terminalu

## 📁 6 –  EXPANSION

'*' - oznacza cokolwiek np *.css albo w ogóle *

'?' - oznacza nieznany 1 znak np cats.??? albo cat?.css albo *.???

'[]' - oznacza zakresy - np [a-z] ; [0-9] ; 

'[^]' - not match np [^1-9] poza liczbami 1-9 albo [^a-z] - poza małymi literami ; [^CcPpDd] 

'{}' - przy tworzeniu plików pozwala na wielokrotne pliki z różnymi nazwami - np touch {mon, tue, wed, thu, fri}_planner.txt - utworzy 5 plików z końcówką _planner. Tworzy stringi w komendach i również kombinacje np touch {mon, tue, wed, thu, fri}_{am, pm}_planner.txt - utworzy 10 plików (każdą możliwą kombinację). Możliwość również {1..365} - utworzy 365 plików ; {a..e} - utworzy od a do e.
Ciekawy przykład: chcemy utworzyć ścieżkę folderów więc: **mkdir -p {mon,tue,wed,thu,fri}/{breakfast,lunch,dinner}** - utworzy skomplikowaną strukturę folderów jednym wierszem

'$' - wykonuje matematyke np. echo $((10+7)) -> wyrzuci 17, ale wynik jest zawsze w liczbach całkowitych - np 10/3 = 3

'' i "" - różnica jest w wykonywaniu poleceń np. echo 'today is $(date)' nie wykona polecenia i wyświetli wszystko a echo "today is $(date)" wyświetli napis i datę dzisiejszą

**Komendy do dużej sieci folderów i plików: mkdir -p Year/{winter,spring,summer,fall}/{yard,house}**

**touch {winter,spring,summer,fall}/{yard,house}/{todos.txt,done.txt}**

## 📁 7 –  Typy plików i uprawnienia

po ls -l wyskakuje log z plikami, przed nimi jest konfig uprawnień 10 znaków (1 typ pliku i 9 uprawnień) d[rwx][---][---] d[Owner][Group][World]
pierwsze 3 (po typie pliku) - oznaczają co właściciel może z nimi zrobić ; kolejne 3 co może grupa z nim zrobić; a ostatnie - co wszyscy pozostali mogą zrobić
1. typy plików
'-' - regular file

d - directory

c - character special file 

l - symbol ink

b - blocked

2. uprawnienia

r - read permission

w - write (can be modified)

x - can be treated as a program (executed)

'-' - cannot be read, executed, modified

**chmod** - zmienia uprawnienia [chmod mode file]

  u - user (owner) ; g - group ; o - (others = world) ; a - (all of the above)
  
  '-' - removes permission ; + - grants permission ; = - sets a permission and removes others
  
  '-' r - read ; w - write ; x - execute

- przykłady : chmod a-w file.txt - usunie write permissions od wszystkich użytkowników [rw-][rw-][r--] -> [r--][r--][r--]

**substitute user - zmiana usera** - su - santi - przełączy usera na santi 

**chown** - zmiana właściciela albo grupy właścicieli pliku np. [chown bojak file.txt] , żeby zmienić grupe dodajemy ':' np [chown :grupaSanti file.txt] a grupe i właściciela tak [chown bojak:horses file.txt] - właścicielem bedzie bojak, a grupa horses - często przy tych komendach trzeba użyć SUDO

**groups** - pokazuje w jakich grupach jest dany user **addgroup [groupname]** tworzy nową grupę; **adduser [user] [group]** dodaje usera do danej grupy
