---
title: "Statystyka - a komu to potrzebne? A dlaczego?"
date: 2020-07-09
permalink: /posts/2020/07/Statystyka-a-co-to-takiego
excerpt: 'W tym poście chciałbym przybliżyć temat statystyki dla tych osób które nie miały z nią do czynienia, ale także tym którzy posługują się pewnymi narzędziami ale niewiedzą jaka intuicja za nimi stoi. Ten post będzie być może początkiem dłuższej serii o tym jak ja rozumiem tę dziedzinę matematyki.'
tags:

  - Statystyka
---

# Wstęp

W tym poście chciałbym przybliżyć temat statystyki dla tych osób które nie miały z nią do czynienia, ale także tym którzy posługują się pewnymi narzędziami ale niewiedzą jaka intuicja za nimi stoi. Ten post będzie być może początkiem dłuższej serii o tym jak ja rozumiem tę dziedzinę matematyki. 

# Statystyka - a komu to potrzebne? A dlaczego?

Będąc w szkole każdy z nasz na pewno nie raz zastanawiał się na lekcji matematyki czy cała ta wiedza będzie nam potrzebna w późniejszym życiu. Dla wielu teoretycznych gałęzi matematyki odpowiedzią jest tzw. *"gimnastyka mózgu"*. W przypadku statystyki jest jednak inaczej. Statystyka jest bardzo praktyczną dziedziną matematyki, a z niektórych jej narzędzi korzystamy na co dzień nawet nie zdając sobie z tego sprawy.

Dlaczego zdecydowałem się opowiedzieć właśnie o statystyce? Niedługo po rozpoczęciu studiów informatycznych zacząłem interesować się tematami związanymi z data science. Umiejętność zaimplementowania algorytmów wydaję się byś potężnym narzędziem w rękach Data Scientista, lecz bez znajomości teorii dzięki której dany algorytm powstał nie mamy pełnego obrazu. 

![VennDataScience](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/VennDataScience.png?raw=true)

Data Science to bardzo szeroka dziedzina nauki czerpiąca zarówno z osiągnięć informatyki, jak i matematyki. Obejmuje takie zagadnienia jak Machine Learning, czy Sieci Neuronowe, a zawód data scientista określany jest mianem najseksowniejszego zawodu świata. Skoro wiemy już że statystyka jest ważna to odpowiedzmy sobie na kolejne pytanie.

# W jaki sposób wykorzystać statystykę?

Jak powiedział C. R. Rao *"Statystyka jest sposobem myślenia i wnioskowania"* i właśnie to wnioskowanie przybliża nas do odpowiedzi. Zanim przejdziemy do wnioskowania statystycznego przypomnijmy sobie czym jest rachunek prawdopodobieństwa leżący u podstaw statystyki. Na pytanie 

> *"Jaka jest szansa wyrzucenia 2 orłów w 4 rzutach, jeżeli szansa na  wyrzucenie orła to 50%?"* 

odpowie nam właśnie rachunek prawdopodobieństwa. Wiedząc że rozkład prawdopodobieństwo <p align="center"><img src="/_posts/tex/28b0b71e05b371ee11b28542314966d1.svg?invert_in_darkmode&sanitize=true" align=middle width=9.07536795pt height=11.4155283pt/></p> sukcesów w <p align="center"><img src="/_posts/tex/b49da7325822089835b531a5fce8b94e.svg?invert_in_darkmode&sanitize=true" align=middle width=9.866876249999999pt height=7.0776222pt/></p> próbach określone jest wzorem <p align="center"><img src="/_posts/tex/bd53dac8ee0ace6e5a0dd907c85d5669.svg?invert_in_darkmode&sanitize=true" align=middle width=144.63690119999998pt height=39.452455349999994pt/></p>, gdzie <p align="center"><img src="/_posts/tex/3ceb13107024b0fcb56c22464beee0a1.svg?invert_in_darkmode&sanitize=true" align=middle width=8.27056725pt height=10.2739725pt/></p> to prawdopodobieństwo sukcesu.

![rachunekPrawdopodobienstwa](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/rachunekPrawdopodobienstwa.gif?raw=true)

> *"Jakie jest prawdopodobieństwo wyrzucenia orła, jeżeli w 4 rzutach wyrzuciliśmy 2 orły?"* 

Na to pytanie rachunek prawdopodobieństwa już nam nie odpowie. Podstawowa różnica? Rachunek prawdopodobieństwa zakłada że znamy rozkład zmiennej. Jest to często możliwe jedynie w teoretycznych rozważaniach, lecz mając do czynienia z prawdziwymi danymi często nie wiemy jaki jest rozkład i tu z pomocą przychodzi statystyka. Dla przypomnienia rozkład mówi nam o tym jakie jest prawdopodobieństwo wystąpienia danej wartości. Poniżej dwa przykłady dyskretny rozkład Bernoullego (Dwumianowy) i ciągły rozkład Gaussa (Normalny).

![BernoulliDistribution](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/Distributions.png?raw=true)

# Co zrobić gdy nie znamy rozkładu?

Wyobraźmy sobie że jako analityk w firmie ubezpieczeniowej chcemy przewidzieć ile ubezpieczeń będzie musiała wypłacić twoja firma przy zadanej liczbie ubezpieczonych. Nie znamy rozkładu tej zmiennej losowej. Pierwsze co przyszło by nam na myśl to spojrzeć w zeszłoroczne *"statystyki"* (nie przypadkowo tak się właśnie nazywają). Na podstawie danych z poprzednich lat jesteśmy w stanie stworzyć pewien model badanego zjawiska. Dzięki czemu możemy stwierdzić z pewnym prawdopodobieństwem że liczba odszkodowań w tym roku wyniesie x. Całkowitej pewności nie mamy, ale możemy posłużyć się pewnym przybliżeniem.

![CarrAccident](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/CarrAccident.jpg?raw=true)

<center>Zdjęcie: Aubrey Rose Odom - unsplash.com</center>


Statystyka pozwala nam na podstawie realizacji zmiennej losowej wywnioskować cos o rozkładzie, rachunek prawdopodobieństwa natomiast pozwala na wnioskowanie w drugą stronę.

# Czas na twierdzenie

Skąd możemy mieć pewność że dane które zebraliśmy pozwalają w jakikolwiek sposób powiedzieć coś o rozkładzie, przecież są losowe. Tutaj z pomocą przychodzi jedno z najważniejszych twierdzeń statystyki - Lemat Glivienki - Cantellego.

Niech <p align="center"><img src="/_posts/tex/e74116a7a668e7504e141d3601d6a374.svg?invert_in_darkmode&sanitize=true" align=middle width=63.742540950000006pt height=14.42921205pt/></p> będzie próbką prostą z rozkładu o dystrybuancie <p align="center"><img src="/_posts/tex/efaaaf7e462e6a462aa9912b88cea10c.svg?invert_in_darkmode&sanitize=true" align=middle width=12.8539257pt height=11.232861749999998pt/></p>

Wówczas:

![lematGlivienkiCantellego](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/lematGlivienkiCantellego.gif?raw=true)

To twierdzenie mówi nam, że dystrybuanta empiryczna zbiega do teoretycznej, co oznacza, że przy odpowiednio dużej próbce możemy dowolnie blisko przybliżyć prawdziwy rozkład danej zmiennej rozkładem empirycznym (tym który uzyskaliśmy w badaniu próbki). Poniżej możemy zobaczyć przykład potwierdzający lemat Glivienki-Cantellego. Rozkład empiryczny (jeśli rozkład to i dystrybuanta) dla coraz to większych próbek zbiega do rozkładu teoretycznego. 

![ExponentionalDistributionComparison](https://raw.githubusercontent.com/mateuszdorobek/mateuszdorobek.github.io/master/files/StatystykaSources/ExponentionalDistributionComparison.gif)

# Podsumowanie

W tym krótkim tekście przybliżyłem czym jest statystyka oraz wskazałem różnicę między rachunkiem podobieństwa. Nie chciałem wyprowadzać tu złożonych wzorów i udowadniać twierdzeń a raczej zwrócić uwagę na praktyczny aspekt tej dziedziny matematyki. 

---

9 Jul 2020 - [Mateusz Dorobek](https://mateuszdorobek.pl/)
