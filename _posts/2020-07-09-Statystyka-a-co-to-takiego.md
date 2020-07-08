---
title: "Statystyka - a komu to potrzebne? A dlaczego?"
date: 2020-07-09
permalink: /posts/2020/07/Statystyka-a-co-to-takiego
excerpt: "W tym poście chciałbym przybliżyć temat statystyki dla tych osób które nie miały z nią do czynienia, ale także tym którzy posługują się pewnymi narzędziami ale niewiedzą jaka intuicja za nimi stoi. Ten post będzie być może początkiem dłuższej serii o tym jak ja rozumiem tę dziedzinę matematyki."
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

> *"Jaka jest szansa wyrzucenia 2 orłów w 4 rzutach, jeżeli prawdopodobieństwo wyrzucenia orła to 50%?"* 

odpowie nam właśnie rachunek prawdopodobieństwa. Wiedząc że rozkład prawdopodobieństwo $k$ sukcesów w $n$ próbach określone jest wzorem $\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k}$, gdzie $p$ to prawdopodobieństwo sukcesu.

![rachunekPrawdopodobienstwa](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/rachunekPrawdopodobienstwa.gif?raw=true)

> *"Jakie jest prawdopodobieństwo wyrzucenia orła, jeżeli w 4 rzutach wyrzuciliśmy 2 orły?"* 

Na to pytanie rachunek prawdopodobieństwa już nam nie odpowie. Podstawowa różnica? Rachunek prawdopodobieństwa zakłada że znamy rozkład zmiennej. Jest to często możliwe jedynie w teoretycznych rozważaniach, lecz mając do czynienia z prawdziwymi danymi często nie wiemy jaki jest rozkład i tu z pomocą przychodzi statystyka. Dla przypomnienia rozkład mówi nam o tym jakie jest prawdopodobieństwo wystąpienia danej wartości. Poniżej dwa przykłady dyskretny rozkład Bernoullego (Dwumianowy) i ciągły rozkład Gaussa (Normalny).

![BernoulliDistribution](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/Distributions.png?raw=true)

# Co zrobić gdy nie znamy rozkładu?

Wyobraźmy sobie że jako analityk w firmie ubezpieczeniowej chcemy przewidzieć ile ubezpieczeń będzie musiała wypłacić twoja firma przy zadanej liczbie ubezpieczonych. Nie znamy rozkładu tej zmiennej losowej. Pierwsze co przyszło by nam na myśl to spojrzeć w zeszłoroczne *"statystyki"* (nie przypadkowo tak się właśnie nazywają). Na podstawie danych z poprzednich lat jesteśmy w stanie stworzyć pewien model badanego zjawiska. Dzięki czemu możemy stwierdzić z pewnym prawdopodobieństwem że liczba odszkodowań w tym roku wyniesie x. Całkowitej pewności nie mamy, ale możemy posłużyć się pewnym przybliżeniem.

![CarrAccident](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/CarrAccident.jpg?raw=true)

Zdjęcie: Aubrey Rose Odom - unsplash.com

Statystyka pozwala nam na podstawie realizacji zmiennej losowej wywnioskować cos o rozkładzie, rachunek prawdopodobieństwa natomiast pozwala na wnioskowanie w drugą stronę.

# Czas na twierdzenie

Skąd możemy mieć pewność że dane które zebraliśmy pozwalają w jakikolwiek sposób powiedzieć coś o rozkładzie, przecież są losowe. Tutaj z pomocą przychodzi jedno z najważniejszych twierdzeń statystyki - Lemat Glivienki - Cantellego.

Niech $$X_1, ... X_n$$ będzie próbką prostą z rozkładu o dystrybuancie $F$ 

Wówczas:

![lematGlivienkiCantellego](https://github.com/mateuszdorobek/mateuszdorobek.github.io/blob/master/files/StatystykaSources/lematGlivienkiCantellego.gif?raw=true)

To twierdzenie mówi nam, że dystrybuanta empiryczna zbiega do teoretycznej, co oznacza, że przy odpowiednio dużej próbce możemy dowolnie blisko przybliżyć prawdziwy rozkład danej zmiennej rozkładem empirycznym (tym który uzyskaliśmy w badaniu próbki). Poniżej możemy zobaczyć przykład potwierdzający lemat Glivienki-Cantellego. Rozkład empiryczny (jeśli rozkład to i dystrybuanta) dla coraz to większych próbek zbiega do rozkładu teoretycznego. 

![ExponentionalDistributionComparison](https://raw.githubusercontent.com/mateuszdorobek/mateuszdorobek.github.io/master/files/StatystykaSources/ExponentionalDistributionComparison.gif)

# Podsumowanie

W tym krótkim tekście przybliżyłem czym jest statystyka oraz wskazałem różnicę między rachunkiem podobieństwa. Nie chciałem wyprowadzać tu złożonych wzorów i udowadniać twierdzeń a raczej zwrócić uwagę na praktyczny aspekt tej dziedziny matematyki. 

---

9 Jul 2020 - [Mateusz Dorobek](https://mateuszdorobek.pl/)