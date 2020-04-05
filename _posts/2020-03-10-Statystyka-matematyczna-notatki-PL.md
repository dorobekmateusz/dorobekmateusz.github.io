---
title: "Statystyka Matematyczna - Notatki"
permalink: /posts/2020/03/Statystyka-matematyczna-notatki-PL
excerpt: 'Notatki Statystyka Matematyczna'
date: 2020-03-10
mathjax: true
tags:

  - Statistics
  - Mathematics
  - Notes
---

# Rozkłady

## Tabela

| Nazwa                    | Oznaczenie                  | Rozkład                                                      | Miary                                                        | Funkcja tworząca momenty                                     | Właściwości                                                  |
| ------------------------ | --------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Dwupunktowy              | $Bin(p)$                    | $f(k)=\left\{\begin{array}{ll}p & \text { dla } x=a \\1-p & \text { dla } x=b\end{array}\right.$ | $$EX=p a+(1-p) b \\VX=p(1-p)(a-b)^{2}$$                      | $M_{X}(t)=p e^{t}+(1-p)$                                     |                                                              |
| Bernoullego (Dwumianowy) | $Bern(n,p)$                 | $$\begin{matrix}f(k)=\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k} \\ n - \text{liczba prób}\\ p -  \text{pstwo. sukcesu}\end{matrix}$$ | $$EX=np \\ VX=np(1-p)$$                                      | $M_{X}(t)=q+p e^t$                                           | n - duże p-małe to $Bin(n,p) \sim Poiss(np)$                 |
| Geometryczny             | $G_1(p)$                    | $f(k)=(1-p)^{k-1} p, \text { gdzie } k=1,2, \ldots$          | $E X=\frac{1}{p} \quad \\ VX=\frac{1-p}{p^{2}}$              | $M_{X}(t)=\frac{p e^{t}}{1-(1-p) e^{t}}, \quad t<-\ln (1-p)$ |                                                              |
| Jednostajny              | $U(a,b)$                    | $$\begin{matrix}f(x) = \frac{1}{b-a}\mathbb{1}_{(a,b)}(x) \\ a, b - \text{krance przedziału}\end{matrix}$$ | $$EX = \frac{1}{b-a} \\ VX = \frac{(b-a)^2}{12}$$            | $M_{X}(t)=\frac{e^{ t b}-e^{ t a}}{ t(b-a)}$                 |                                                              |
| Normalny (Gaussa)        | $N(\mu,\sigma)$             | $f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $$EX = \mu \\ VX=\sigma^2$$                                  | $M_{X}(t)=\exp \left(t \mu+\frac{1}{2} t^{2} \sigma^{2}\right)$ | $\bar{X} \sim N(\mu,\frac{\sigma}{\sqrt{n}})\\ \sum{X^2}\sim \mathcal{X}^2_n$ |
| Logarytmiczno-Normalny   | $LN(\mu,\sigma)$            | $f(x)=\frac{1}{\sigma x \sqrt{2 \pi}} e^{-\frac{(\log x-\mu)^{2}}{2 \sigma^{2}}},$ gdzie $x \in \mathbb{R}$ | $$E X=e^{\mu+\frac{z^{2}}{2}}, \\ VX=e^{2 \mu}\left(e^{2 \sigma^{2}}-e^{\sigma^{2}}\right)$$ | nie istnieje                                                 |                                                              |
| Poissona                 | $Poiss(\lambda)$            | $$\begin{matrix}f(k,\lambda) = \frac{\lambda^ke^{-\lambda}}{k!} \\ \lambda - \text{oczekiwana liczba zdarzeń} \\ k - \text{faktyczna liczba zdarzeń}\end{matrix}$$ | $$EX = \lambda \\ VX=\lambda$$                               | $M_{X}(t)=e^{\lambda\left(e^{ t}-1\right)}$                  |                                                              |
| Wykładniczy              | $Exp(\lambda)$              | $$\begin{matrix}f(x) = \lambda e^{-\lambda x}\\ F(x) = 1-e^{-\lambda x}\end{matrix}$$ | $$EX=\frac{1}{\lambda} \\ VX = \frac{1}{\lambda^2}$$         | $M_{X}(t)=\frac{\lambda}{\lambda-t}$                         | $Exp(\lambda)=\Gamma(1,\lambda)$                             |
| Gamma                    | $\Gamma(\alpha,\beta)$      | $$f(x)=\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}\mathbb{1}_{(0,\infty)}(x)\\ \Gamma(\alpha)=\int_{0}^{\infty}x^{\alpha-1}e^{-x}dx$$ | $$EX=\frac{\alpha}{\beta} \\ VX=\frac{\alpha}{\beta^2}$$     | $M_{X}(t)=\frac{1}{(1-t \lambda)^{p}}$                       | $\Gamma(1)=1\\\Gamma(n+1)=n! \; n\in N\\\Gamma(\frac{1}{2})=\sqrt{\pi}$ |
| Chi-kwadrat              | $\mathcal{X}^2_n$           | $$f(x)=\left\{\begin{matrix}\frac{1}{2^{n/2}\Gamma(\frac{n}{2})}x^{\frac{n}{2}-1}e^{\frac{-x}{2}}\text{dla }x>0\\ 0\text{ w.p.p.}\end{matrix}\right.$$ | $$EX = n \\ VX=2n$$                                          | $$M_{X}(t)=(1-2 t)^{-n / 2} \\ \text{ dla } 2 t<1$$          | $$X=\sum Z_i^2\;Z_i\sim N(0,1) \\ (Z_1,\dots,Z_n) \:iid \\ X\sim \mathcal{X}^2_n  \\ n\bar Z^2 = (\sqrt{n} \bar{Z})^2\sim \mathcal{X}^2_1\ \\ \mathcal{X}^2_n \sim \Gamma(\frac{n}{2}, \frac{1}{2})$$ |
| T-studenta               | $t(n)$                      | $f(x)=\frac{\Gamma(\frac{n+1}{2})}{\sqrt{n\pi}\:\Gamma(\frac{n}{2})}(1+\frac{x^2}{n})^{-\frac{n+1}{2}}$ | $$EX=0\;n>1 \\ VX=\frac{n}{n-2}\;n>2$$                       | nie istnieje                                                 | $$T=\frac{Z}{\sqrt{\frac{X}{n}}} \\ Z\sim N(0,1) \\ X\sim \mathcal{X}^2_n$$ |
| F-Snedecora              | $F^{[n,m]}$                 | $f(x)=\frac{\sqrt{\frac{\left(d_{1} x\right)^{d_{1}} d_{2}^{d_{2}}}{\left(d_{1} x+d_{2}\right)^{d_{1}+d_{2}}}}}{x \mathrm{B}\left(\frac{d_{1}}{2}, \frac{d_{2}}{2}\right)}$ | $$EX=\frac{m}{m-2} \;m>2 \\ VX=\frac{2 m^{2}\left(n+m-2\right)}{n\left(m-2\right)^{2}\left(m-4\right)} \; m>4$$ |                                                              | $$F = \frac{\frac{X}{n}}{\frac{Y}{m}} \\ X\sim \mathcal{X}^2_n \\ Y\sim \mathcal{X}^2_m$$ |
| Cauchy'ego               | $C(m,\lambda)$              | $f(x)=\frac{1}{\pi}\frac{\lambda^2}{\lambda^2+(x-m)^2}$      | $EX$ i $VX$ nie istnieją.                                    | $M_{X}(t)=e^{t m-\lambda}$                                   | $$C = \frac{X_1}{X_2} \\ X_1,X_x\sim N(0,1) \\ C\sim C(m,\lambda) $$ |
| Beta                     | $\mathcal{B}(\alpha,\beta)$ | $$f(x)=\frac{1}{\mathcal{B}(\alpha,\beta)}x^{\alpha-1}(1-x)^{\beta-1}\mathbb{1}_{(0,1)}(x) \\ \mathcal{B}(\alpha,\beta)=\frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+\beta)} \\ \mathcal{B}(\alpha,\beta)=\int_0^1t^{\alpha-1}(1-t)^{\beta-1}dt$$ | $$EX = \frac{\alpha}{\alpha+\beta} \\ VX=\frac{\alpha \beta}{(\alpha+\beta)^{2}(\alpha+\beta+1)}$$ |                                                              |                                                              |
| Rayleigha                | $Ra(\sigma)$                | $f(x)=\frac{x}{\sigma^2}e^{-\frac{x^2}{2\sigma^2}}\mathbb{1}_{(0,\infty)}(x)$ | $$EX=\sigma\sqrt{\frac{\pi}{2}} \\ VX=\frac{4-\pi}{2}\sigma^2$$ |                                                              |                                                              |
| Pareto                   | $Pa(k,\alpha)$              | $f(x)=\frac{\alpha k^{\alpha}}{x^{\alpha+1}} \mathbb{1}_{(k, \infty)}(x)$ | $E X=\frac{\alpha k}{\alpha-1}, \alpha>1 \\ VX=\frac{\alpha k^{2}}{(\alpha-2)(\alpha-1)^{2}}$ | nie istnieje                                                 |                                                              |

## Opisy

### Rozkład Dwupunktowy

Rozkład ten pojawia się przy opisie doświadczeń losowych o dwu możliwych wynikach, z którymi
możemy skojarzyć wartości liczbowe.

### Rozkład Dwumianowy (Bernoullego)

Jest to rozkład łącznej liczby sukcesów w $n$ doświadczeniach Bernoullego, gdy szansa pojedynczego sukcesu wynosi $p$. Lub inaczej: jest to rozkład sumy $X_{1}+\ldots+X_{n},$ gdzie zmienne losowe $X_{i}$ są niezależne i maja ten sam rozkład dwupunktowy.

### Rozkład Poissona

Jest to rozkład graniczny dla ciągu rozkładów Bernoullego $Bern(n, p_{n}),$ gdy $n \rightarrow \infty, p_{n} \rightarrow 0$ i $n p_{n} \rightarrow \lambda .$ W związku z tym pojawia się jako rozkład zdarzeń "*rzadkich*" (liczba wypadków drogowych, liczba pożarów, liczba wygranych w "Lotto", itp).

### Rozkład Geometryczny

Jest to rozkład czasu oczekiwania na pierwszy sukces w ciągu doświadczeń Bernoullego, rozumianego jako liczba doświadczeń, które należy wykonać, żeby doczekać się sukcesu.

Niekiedy rozumie się czas oczekiwania dosłownie, jako liczbę doświadczeń wykonanych przed otrzymaniem pierwszego sukcesu. Wtedy otrzymujemy zmienna losowa $Y=X-1$ przejmującą wartości $k=0,1,2 \ldots ;$ wtedy $P(Y=k)=(1-p)^{k} p .$ Rozkład zmiennej losowej $Y$ takie nazywamy geometrycznym i oznaczamy $G_{0}(p) .$ Wtedy $E Y=EX-1, VY=VX.$

### Rozkład jednostajny

Wiąże się z intuicją ”*losowego*” wyboru punktu ze zbioru.

### Rozkład Gamma

Rozkład gamma jest dobry do opisu zmiennych, które mogą mieć rozkład skośny

### Rozkład Wykładniczy

Szczególnym, ale bardzo istotnym przypadkiem rozkładu gamma jest rozkład $\Gamma(1, \beta),$ czyli rozkład wykładniczy z parametrem $\beta(\beta>0),$ oznaczany $\operatorname{Exp}(\beta)$. Rozkład wykładniczy jest ciągłym odpowiednikiem rozkładu geometrycznego.

### Rozkład Pareto

Nazwa pochodzi od nazwiska włoskiego ekonomisty Vilfredo Pareto. Jest to ciągły rozkład prawdopodobieństwa, występujący m.in. w naukach społecznych, geofizyce, i aktuariacie. W ubezpieczeniach wyraża rozmiar finansowej odpowiedzialności ubezpieczyciela w związku z wypadkami losowymi jego klientów przy ubezpieczeniu OC, AC oraz od wypadków przy pracy.

### Rozkład Normalny (Gaussa)

Jest to jeden z najważniejszych rozkładów prawdopodobieństwa. Odgrywa ważną rolę w statystycznym opisie zagadnień przyrodniczych, przemysłowych, medycznych, socjalnych, ekonomicznych itp.

### Rozkład Logarytmiczno-Normalny

Rozkład Logarytmiczno-Normalny jest często lepszym od rozkładu normalnego przybliżeniem rozkładów zmiennych losowych, w których istotne są stosunki pomiędzy wartościami, a nie różnice pomiędzy nimi. Na przykład przybliżony rozkład logarytmiczno-normalny mają kursy akcji giełdowych, gdzie ważniejsze jest o ile procent zmniejszyła się lub zwiększyła wartość akcji, a nie o ile złotych.

# Statystyka vs Rachunek Prawdopodobieństwa

Przykład: Rzucamy 10 razy monetą.

|                 Rachunek Prawdopodobieństwa                  |                          Statystyka                          |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|            Jakie jest pstwo. wyrzucenia 5 orłów?             | Załóżmy że otrzymaliśmy 5 orłów jakie jest prawdopodobieństwo wyrzucenia jednego orła? |
| $X_1, \dots, X_{10} \quad X \sim Bin(\frac{1}{2}) = \left\{\begin{matrix} x_i = 1 \quad orzeł \\ x_i = 0 \quad reszka\\ \end{matrix}\right. \\ \sum_{i=1}^{10} \sim Bin(10,\frac{1}{2}) \quad P(\sum_{i=1}^{10}{x_i}=5) = \binom{10}{5} \frac{1}{2^{10}}$ | $X_1, \dots, X_{10} \quad X \sim Bin(p)   \quad p \in <0,1> \\ \sum_{i=1}^{10}{x_i} = 5 \Rightarrow p =?$ |
|                      określony rozkład                       |                     nieokreślony rozkład                     |

# Cytaty

> "Statystyki mają założenia"
>

> "Konsultacja ze statystykiem po badaniu to tak jak wołanie lekarza do umarłego, on może tylko stwierdzić zgon"
>

> "Wszystkie modele są złe, ale część z nich jest użyteczna" - George Box
>

> "Dlaczego sułtan nosi zielone szelki? ... żeby mu spodnie nie spadały." - o istotności danych
>

> "Czasami do wnioskowania statystycznego wystarczy jedynie statystyka z próbki a nie cała próbka"
>

> "Próbka też jest statystyką - dostateczną"
>
> "Statystyka jest sposobem myślenia i wnioskowania" - Calyampudi Radhakrishna Rao

# Twierdzenia

## Podstawowe twierdzenie statystyki matematycznej (lemat Glivienki-Cantellego)

Niech $$X_1, ... X_n$$ będzie próbką prostą z rozkładu o dystrybuancie $F$ 

Wówczas:

$$
P\left(\lim _{t \rightarrow \infty} \sup _{t \in R}|\hat{F_{n}}(t)-F(t)|=0\right)=1
$$

Dystrybuanta empiryczna zbiega do teoretycznej.

## Kryterium faktoryzacji (Twierdzenie Fishera - Neymana)

Statystyka $T$ jest dostateczna dla rodziny rozkładów $\mathcal{P}=\left\{p_{0}: \theta \in \Theta\right\}$ wtedy i tylko wtedy, gdy łączny rozkład próbki $\mathbb{X}=\left(X_{1}, \ldots, X_{n}\right)$ można przedstawić w postaci
$$
p_{\theta}(\mathrm{x})=g_{\theta}(T(\mathrm{x})) \cdot h(\mathrm{x})
$$
gdzie $h$ jest funkcją, która nic zależy od $\theta$, natomiast funkcja $g$, zależna od $\theta$, zależy również od próbki, ale tylko poprzez wartość statystyki $T$

## Twierdzenie (min. stat. dost.)

Załóżmy że istnieje taka statystyka $T$ że $\forall{x,y}\in X $ zachodzi: $\frac{p_\theta(x)}{p_\theta(y)}$ nie zależy od $\theta,\forall_{\theta \in \Theta} \Leftrightarrow T(X) = T(y)$ wówczas $T$ jest **minimalną statystyką dostateczną**. 

**Przykład**
$$
p_\theta(x) = \theta^{\sum{x_i}}(1-\theta)^{n-\sum{x_i}} ,\quad
\frac{p_\theta(x)}{p_\theta(y)} = \left(\frac{\theta}{1-\theta}\right)^{\sum{x_i}-\sum{y_i}}\\
$$

nie zależy od $\theta$ tylko gdy $\sum{x_i}=\sum{y_i}$ stąd $T(x) = \sum{x_i}$ jest minimalną statystyką dostateczną.

## Centralne twierdzenie graniczne

Jeżeli $X_i$ są niezależnymi zmiennymi losowymi o jednakowym rozkładzie, takiej samej wartości oczekiwanej $\mu$ oraz dodatniej i skończonej wariancji $ \sigma ^{2}$ to zmienna losowa o postaci:
$$
\frac{\frac{1}{n} \sum_{i=1}^{n} X_{i}-\mu}{\frac{\sigma}{\sqrt{n}}}
$$
zbiega według rozkładu do standardowego rozkładu normalnego, gdy $n$ rośnie do nieskończoności.

## Twierdzenie

$X$ - próbka prosta z rozkładu należy do **k-parametrowej rodziny wykładniczej** wtedy istnieje nietrywialna statystyka dostateczna w postaci:

$$
S(X) = (S_1(x), \dots, S_n(x)) \text{, gdzie }S_j(X) = \sum_{i=1}^{n}T_j(X_i)
$$

# Definicje

## Zmienne Losowe IID

Niezależne i identycznie rozmieszczone zmienne losowe (z tego samego rozkładu) - (ang. *Independent and identically distributed random variables)*

## Funkcja tworząca momenty

$$
\begin{aligned}
M_X(t) & = E(e^{tX}) \\ \\
EX & = M'_X(0) \\ 
\text{Dowód: }  M'_X(0) & = E(Xe^{0X}) = E(X)\\
E(X^2) & = M''_X(0) \\
VX & = E(X^2) - E(X)^2 \\ 
& = M''_X(0) - M'_X(0)^2 \\
\end{aligned}
$$

**Przykład**

Dla rozkładu gamma o funkcji gęstości:
$$
f(x)=\frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta \tau} \text { dla } x>0
$$
Wyznaczamy funkcję generującą momenty:
$$
\begin{aligned}
M_{X}(t) & =\int_{0}^{\infty} e^{\pi t} \frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta t} d x \\
& =\left(\frac{\beta}{\beta-t}\right)^{\alpha} \int_{0}^{\infty} \frac{(\beta-t)^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1} e^{-(\beta-t) x} d x \\
& =\left(\frac{\beta}{\beta-t}\right)^{\alpha} \text { dla } \mathrm{t}<\beta \\
m_{1}& =\frac{\alpha}{\beta} \\
m_{2}& =\frac{\alpha(\alpha+1)}{\beta^{2}} \\
m_{k}& =\frac{\alpha(\alpha+1)(\alpha+2) \cdots(\alpha+k)}{\beta^{k}} \\

EX & = m_1 = \frac{\alpha}{\beta}\\
VX & = m_2 - m_1^2  = \frac{\alpha}{\beta^2}\\
\end{aligned}
$$


## Statystyka dostateczna

Statystykę $T = T(X_1, ..., X_n)$ nazywamy **dostateczną** dla rodziny rozkładów $P = \{p_{\theta}, \theta \in \Theta\}$ (dla parametru $\theta$) jeżeli dla każdej wartości $t$ tej statystyki rozkład warunkowy próbki $(X_1, \dots, X_n)$ pod warunkiem $T = t$ nie zależy od $\theta$.

Próba sama w sobie też jest statystyką dostateczną (trywialną)

**Przykłady**

Czy  $T=\sum x_{i}$ jest statystyką dostateczną dla rozkładu dwupunktowego?


$$
\begin{aligned}
P_{\theta}\left(X_{1}=x_1, \dots, X_{n}=x_{n} | T=t \right) &= \frac{P_{\theta}\left(X_{1}=x_1, \dots, X_{n}=x_{n}, T=t \right)}{P_{\theta}\left(T=t\right)} = (*) \\
P_{\theta}\left(X_{1}=x_1, \dots, X_{n}=x_{n}, T=t \right) &= \left\{\begin{matrix}
P_{\theta}\left(X_{1}=x_1, \dots, X_{n}=x_{n} \right) & \text{gdy} \quad x_1+\dots+x_n = t \\
0 & \text{ wpp}
\end{matrix}\right. \\
P_{\theta}\left(X_{1}=x_1, \dots, X_{n}=x_{n} \right) &= P_{\theta}\left(X_{1}=x_1\right)* \dots * P_{\theta}\left(X_{n}=x_{n}\right) = \\
 &= \theta^{x_1}(1-\theta)^{1-x_1} * \dots * \theta^{x_n}(1-\theta)^{1-x_n} = \\
 &= \theta^{\sum{x_i}}(1-\theta)^{n-\sum{x_i}}\\

T &= \sum{x_i} \sim Bern(n, \theta) \Rightarrow P_\theta(T=t) = \binom{n}{t}\theta^{t}(1-\theta)^{n-t}\\

(*) &= \left\{\begin{matrix}
\frac{\theta^{\sum{x_i}}(1-\theta)^{n-\sum{x_i}}}{\binom{n}{t} \theta^{t}(n-\theta)^{n-t}} = \frac{1}{\binom{n}{t}} & \text{gdy} \quad x_1+\dots+x_n = t \\
0 & \text{ wpp}
\end{matrix}\right.\\
\frac{1}{\binom{n}{t}} &\text{ nie zależy od }\theta \text{ więc statystyka } T \text{ jest dostateczna}
\end{aligned}
$$

## Minimalna Statystyka Dostateczna

Statystykę dostateczną S nazywamy **minimalną statystyką dostateczną**, jeżeli dla każdej statystyki dostatecznej $T$ istnieje funkcja $h$ taka, że $S = h(T)$.

## K-parametrowa rodzina wykładnicza

Rodzina rozkładów prawdopodobieństwa $\left\{P_{\theta}: \theta \in \Theta\right\}$ nazywa się k-parametrową rodziną wykładniczą jeżeli  $ p_\theta$ (gęstość) można przedstawić w następującej postaci:
$$
p_{\theta}(x)=\exp \left\{\sum_{j=1}^{k} C_{j}(\theta) T_{j}(x)-B(\theta)\right\} \cdot h(x)
$$
gdzie

- $T_{1}, \ldots, T_{k}$ są funkcjami liniowo niezależnymi
- $C_1, \dots, C_k, B$ - funkcje parametru $ \theta $
- $h, T_1, \dots, T_k$ - funkcje $x$

jest pewnym $k$ -wymiarowym zbiorem w $\mathbf{R}^{k}$.

# Wzory

## Wartość oczekiwana

$$
\begin{aligned}
EX &= \int_{-\infty}^{+\infty}xf(x)dx \\
E(h(X)) &= \int_{-\infty}^{+\infty}h(x)f(x)dx\\
\end{aligned}
$$

## Wariancja próbkowa
$$
\begin{aligned} 
\sigma &= \sqrt{\int_{-\infty}^{\infty}(x-\mu)^{2} f(x) d x}\\
s^{2} &= \frac{1}{n-1} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}=\\ 
&= \frac{1}{n-1}\left(\sum x_{i}^{2}-2 \sum x_{i} \bar{x}+\sum \bar{x}^{2}\right)=\\ 
&= \frac{1}{n-1}\left(\sum x_{i}^{2}-2 \bar{x} \sum x_{i}+n \bar{x}^{2}\right)=\\ 
&= \frac{1}{n-1}\left(\sum x_{i}^{2}-2 \bar{x}{n} \bar{x}+n \bar{x}^{2}\right)=\\ 
&= \frac{1}{n-1}\left(\sum x_{i}^{2}-n \bar{x}^{2}\right) \end{aligned}
$$

# Analiza Matematyczna

Małe przypomnienie całek z analizy matematycznej.

## Twierdzenie (o całkowaniu przez części)

Jeżeli funkcje $u$ i $v$ maja na pewnym przedziale $P$ ciągłe pochodne $u$' i $v'$ to na tym przedziale.
$$
\int u(x) v^{\prime}(x) d x=u(x) v(x)-\int v(x) \mu^{\prime}(x) d x
$$
**Przykład 1** 

$\int x \cos x \, d x=\left|\begin{array}{ll}
u=x & v^{\prime}=\cos x\\
u^{\prime}=1 & v=\sin x
\end{array}\right|=x \sin x-\int \sin x \, d x=x \sin x+\cos x+C$

**Przykład 2**

$\int \ln x \, d x=\int 1 \cdot \ln x \, d x=\left|\begin{array}{ll}
u=\ln x &v^{\prime}=1   \\
u^{\prime}=\frac{1}{x}& v=x
\end{array}\right|=x \ln x-\int \frac{1}{x} x \, d x=x \ln x-x+C$

**Przykład 3**

$\int x e^{x} d x=\left|\begin{array}{cc}u=x & v^{\prime}=e^{x}  \\ u^{\prime}=1& v=e^{x}\end{array}\right|=x e^{x}-\int e^{x} d x=e^{x}(x-1)+C$

## Twierdzenie (o całkowaniu przez podstawienie)

Jeżeli funkcja $f$ jest całkowalna na przedziale $P$, zaś funkcja $g$ ma ciągłą pochodna na przedziale $T$ i przekształca go na przedział $P$ oraz znana jest całka
$$
\int f(x) d t=f(t)+c \\
\int f(g(x)) g^{\prime}(x) d x=F(g(x))+c
$$

**Przykład 1**
$\int\left(e^{x}+5\right) e^{x} d x=\left|\begin{array}{l}t=e^{x} \\ dt=e^{x} d x\end{array}\right|=\int(t+5) d t=\frac{t^{2}}{2}+5 t+C=\frac{e^{2 x}}{2}+5 e^{x}+C$

**Przykład 2**

$\int \frac{x d x}{1+x^{2}}=\left|\begin{array}{l}
t=1+x^{2} \\
a t=2 x d x \\
x d x=\frac{1}{2} d t
\end{array}\right|=\frac{1}{2} \int \frac{d t}{t}=\frac{1}{2} \ln |t|+C=\frac{1}{2} \ln \left(x^{2}+1\right)+C$

# TODO

- [ ] Rozkłady łączne
- [ ] Rozkłady warunkowe - prawdopodobieństwo rozkładu łącznego jest równe iloczynowi prawdopodobieństw pojedynczych jeżeli zmienne losowe są iid.
- [ ] Centralne twierdzenie  graniczne
- [ ] Zmienna Losowa
- [ ] Próbka - realizacja zmiennej losowej

----

2020 [Mateusz Dorobek](https://mateuszdorobek.pl/)

10 Marzec 2020 - Tabela Rozkładów, Cytaty, Statystyka vs Rachunek

26 Marzec 2020 - Statystyka Dostateczna + twierdzenia (Kryterium Faktoryzacji)

01 Kwiecień 2020 - Update: Wzory EX VX, K-parametrowa rodzina wykładnicza

05 Kwiecień 2020 - Opisy rozkładów, Funkcja tworząca momenty, Całkowanie

# Źródła:

- Większość wzorów i twierdzeń: PW - Wykłady Statystyka Matematyczna
- Opisy rozkładów: KUL - Przegląd ważniejszych rozkładów - [link](https://pracownik.kul.pl/files/103633/public/Aktuarialna_teoria_ryzyka/rozklzmlosakt.pdf)
- Całkowanie: PWJSTK - Wykłady Analiza Matematyczna - [link](http://edu.pjwstk.edu.pl/wyklady/am/scb/index59.html)