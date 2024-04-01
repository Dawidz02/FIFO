# FIFO
Program realizujący poniższe zadanie:
Napisz program, który:

    (a) utworzy potok (funkcją pipe),
    (b) uruchomi podproces, z którym proces nadrzędny będzie komunikował się przez ten potok (funkcja fork),
    (c) proces nadrzędny otworzy plik tekstowy podany w argumencie wywołania programu, a następnie wyśle procesowi potomnemu zawartość tego pliku przez potok,
    (d) proces potomny odczyta dane z potoku, a następnie wyświetli je na standardowym wyjściu dodając znacznik @@@@ na początku i #### na końcu każdej odebranej paczki danych. Wielkość paczek jest dowolna.

Zmodyfikuj program z punktu w taki sposób, by wykorzystując potok nazwany (FIFO) był w stanie wysyłać do tego potoku zawartość wielu kolejnych plików, których nazwy poda użytkownik w formie kolejnych argumentów wywołania. Pomiędzy przesyłaniem zawartości poszczególnych plików program ma odczekać 5 sekund.

Ponieważ potoki FIFO istnieją jako pliki na dysku, i każdy program może je dowolnie otwierać, nie ma tu już potrzeby uruchamiania procesu czytającego przez klonowanie. Program czytający może być uruchomiony całkowicie niezależnie.

Do wyświetlania plików FIFO najlepiej wykorzystać program tail z argumentami -c +NUM oraz -f (flaga -f powoduje, że po osiągnięciu końca pliku, program tail nie kończy pracy tylko czeka na dalsze dane).
