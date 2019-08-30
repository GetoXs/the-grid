# The Grid
Projekt na studia 2011 r. Gra oparta na własnych modułach silnika 3d

## Cel zadania

Celem naszego zadania będzie stworzenie niżej wymienionych elementarnych mechanizmów niezbędnych do stworzenia gry komputerowej. Zdecydowaliśmy się na taką interpretację:
*	uproszczony parser plików XML bądź SQLLite do szybkiego i prostego dostępu do danych,
*	własny silnik graficzny (oparty o bibliotekę OpenGL) lub Ogre3D – jeszcze nie zdecydowaliśmy się na wybór,
*	moduł zarządzania zasobami (obiektami i elementami) w grze,
*	moduł obsługi wejścia (klawiatura, mysz),
*	moduł obsługi dźwięku.

Przy implementacji zamierzamy stosować środowisko deweloperskie Microsoft Visual Studio 2010, a jako język zamierzamy używać C++ z uwagi na szerokie zastosowanie w produkcji gier.

## Specyfikacja zewnętrzna

*	Gra polega na likwidowaniu pojawiających się losowo przeciwników i zdobyciu jak największej ilości punktów.
*	Grę rozpoczynamy starując na środku kwadratowej planszy, na której krańcach w losowych miejscach (daleko od przeciwnika) pojawiają się przeciwnicy. Na starcie posiada się 5 żyć.
*	Postacią sterujemy za pomocą strzałek, praco, lewo, jest skręcanie, przód, tył, odpowiednio przesuwamy postać do przodu oraz do tyłu.
*	Strzał oddajemy naciskając klawisz spacji, możemy oddać maksymalnie 10 strzałów na sekundę.
*	W górnym lewym roku ekranu mam informacje o posiadanej ilości życia oraz ilości zebranych punktów. Za każdego zabitego przeciwnika dostajemy 1 punkt.
*	Jeśli przeciwnik podejście zbyt blisko do nas, wybucha i zabiera nam jedno życie. Jeśli poziom życia zejdzie do zera gra się zakończy.
*	Podczas gry możemy uruchomić wyświetlanie informacji o ilości fpsów klawiszem ‘F’.

## Specyfikacja wewnętrza

Gra została zaimplementowania z wykorzystaniem pętli silnika gry, z czego, jako że mamy 2 odrębne systemy zarządzania, logiką oraz grafiką (logika całkowicie niezależna od grafiki), ustawiliśmy odświeżanie pętli grafiki na 50fpsów (zmiany niewidoczne dla oka), natomiast pętla logiki działa z częstotliwością 10Hz. 
