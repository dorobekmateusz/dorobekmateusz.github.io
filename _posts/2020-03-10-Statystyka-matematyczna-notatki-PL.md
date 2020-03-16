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

| Nazwa                     | Oznaczenie                                                   | Rozkład                                                      | Miary                                                | Funkcja tworząca momenty | Właściwości                                                  |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------------------------------------------- | ---------------------------------- | ------------------------------------------------------------ |
| Jednopunktowy | $\delta(x_0)$ |  | $$EX = x_0, \\ VX = 0$$ |  |  |
| Bernoullego (Dwumianowy) | $$\begin{matrix}Bin(n,p)\\ n - \text{liczba prób}\\ p -  \text{pstwo. sukcesu}\end{matrix}$$ | $f(k)=\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k}$ | $$EX=np \\ VX=np(1-p)$$                             | $\varphi_{X}(t)=q+p e^t$ | n - duże p-małe to $Bin(n,p) \sim Poiss(np)$                 |
| Jednostajny               | $$\begin{matrix}U(a,b) \\\ a, b - \text{krance przedziału}\end{matrix}$$ | $f(x) = \frac{1}{b-a}\mathbb{1}_{(a,b)}(x)$ | $$EX = \frac{1}{b-a} \\ VX = \frac{(b-a)^2}{12}$$     | $\varphi_{X}(t)=\frac{e^{ t b}-e^{ t a}}{ t(b-a)}$ |                                                              |
| Normalny (Gaussa)         | $N(\mu,\sigma)$                                              | $f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $$EX = \mu \\ VX=\sigma^2$$                          |                                    | $\bar{X} \sim N(\mu,\frac{\sigma}{\sqrt{n}})\\ \sum{X^2}\sim \mathcal{X}^2_n$ |
| Poissona                  | $Poiss(\lambda)$                                             | $$\begin{matrix}f(k,\lambda) = \frac{\lambda^ke^{-\lambda}}{k!} \\ \lambda - \text{oczekiwana liczba zdarzeń} \\ k - \text{faktyczna liczba zdarzeń}\end{matrix}$$ | $$EX = \lambda \\ VX=\lambda$$                       | $\varphi_{X}(t)=e^{\lambda\left(e^{ t}-1\right)}$ |                                                              |
| Wykładniczy               | $Exp(\lambda)$                                               | $$\begin{matrix}f(x) = \lambda e^{-\lambda x}\\ F(x) = 1-e^{-\lambda x}\end{matrix}$$ | $$EX=\frac{1}{\lambda} \\ VX = \frac{1}{\lambda^2}$$ | $\varphi_{X}(t)=\frac{\lambda}{\lambda-t}$ | $Exp(\lambda)=\Gamma(1,\lambda)$                             |
| Gamma                     | $\Gamma(\alpha,\beta)$                                       | $$f(x)=\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}\mathbb{1}_{(0,\infty)}(x)\\ \Gamma(\alpha)=\int_{0}^{\infty}x^{\alpha-1}e^{-x}dx$$ | $$EX=\frac{\alpha}{\beta} \\ VX=\frac{\alpha}{\beta^2}$$ | $\varphi_{X}(t)=\frac{1}{(1-t \lambda)^{p}}$ | $\Gamma(1)=1\\\Gamma(n+1)=n! \; n\in N\\\Gamma(\frac{1}{2})=\sqrt{\pi}$ |
| Chi-kwadrat               | $\mathcal{X}^2_n$                      | $$f(x)=\left\{\begin{matrix}\frac{1}{2^{n/2}\Gamma(\frac{n}{2})}x^{\frac{n}{2}-1}e^{\frac{-x}{2}}\text{dla }x>0\\ 0\text{ w.p.p.}\end{matrix}\right.$$ | $$EX = n \\ VX=2n$$                                  | $\varphi_{X}(t)=(1-2 t)^{-n / 2} \text{ dla } 2 t<1$ | $$X=\sum Z_i^2\;Z_i\sim N(0,1) \\ (Z_1,\dots,Z_n) \:iid \\ X\sim \mathcal{X}^2_n  \\ n\bar Z^2 = (\sqrt{n} \bar{Z})^2\sim \mathcal{X}^2_1\ \\ \mathcal{X}^2_n \sim \Gamma(\frac{n}{2}, \frac{1}{2})$$ |
| T-studenta                | $t(n)$                                                       | $f(x)=\frac{\Gamma(\frac{n+1}{2})}{\sqrt{n\pi}\:\Gamma(\frac{n}{2})}(1+\frac{x^2}{n})^{-\frac{n+1}{2}}$ | $$EX=0\;n>1 \\ VX=\frac{n}{n-2}\;n>2$$              | (nieokreślona) | $$T=\frac{Z}{\sqrt{\frac{X}{n}}} \\ Z\sim N(0,1) \\ X\sim \mathcal{X}^2_n$$ |
| F-Snedecora               | $F^{[n,m]}$                                                  | $f(x)=\frac{\sqrt{\frac{\left(d_{1} x\right)^{d_{1}} d_{2}^{d_{2}}}{\left(d_{1} x+d_{2}\right)^{d_{1}+d_{2}}}}}{x \mathrm{B}\left(\frac{d_{1}}{2}, \frac{d_{2}}{2}\right)}$ | $$EX=\frac{m}{m-2} \;m>2 \\ VX=\frac{2 m^{2}\left(n+m-2\right)}{n\left(m-2\right)^{2}\left(m-4\right)} \; m>4$$ |                                    | $$F = \frac{\frac{X}{n}}{\frac{Y}{m}} \\ X\sim \mathcal{X}^2_n \\ Y\sim \mathcal{X}^2_m$$ |
| Cauchy'ego                | $C(m,\lambda)$                                               | $f(x)=\frac{1}{\pi}\frac{\lambda^2}{\lambda^2+(x-m)^2}$      | $EX$ i $VX$ nie istnieją. | $\varphi_{X}(t)=e^{t m-\lambda}$ | $$C = \frac{X_1}{X_2} \\ X_1,X_x\sim N(0,1) \\ C\sim C(m,\lambda) $$ |
| Beta                      | $\mathcal{B}(\alpha,\beta)$                                        | $$f(x)=\frac{1}{\mathcal{B}(\alpha,\beta)}x^{\alpha-1}(1-x)^{\beta-1}\mathbb{1}_{(0,1)}(x) \\ \mathcal{B}(\alpha,\beta)=\frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+\beta)} \\ \mathcal{B}(\alpha,\beta)=\int_0^1t^{\alpha-1}(1-t)^{\beta-1}dt$$ | $$EX = \frac{\alpha}{\alpha+\beta} \\ VX=\frac{\alpha \beta}{(\alpha+\beta)^{2}(\alpha+\beta+1)}$$ |                                    |                                                              |
| Rayleigha                 | $Ra(\sigma)$                                                 | $f_\sigma(x)=\frac{x}{\sigma^2}e^{-\frac{x^2}{2\sigma^2}}\mathbb{1}_{(0,\infty)}(x)$ | $$EX=\sigma\sqrt{\frac{\pi}{2}} \\ VX=\frac{4-\pi}{2}\sigma^2$$ |                                    |                                                              |



# Cytaty

"Statytsyki mają założenia"

"Konsultacja ze statystykiem po badaniu to tak jak wołanie lekarza do umarłego, on może tylko stwierdzić zgon"

"All models are wrong, but some are useful" - George Box

"Dlaczego sułtan nosi zielone szelki? ... żeby mu spodnie nie spadały." - o istotności danych

"Czasami do wnioskowania statystycznego wystarczy jedynie statystyka z próbki a nie cała próbka"

"Próbka też jest statystyką - dostateczną"

# Twierdzenia

## Podstawowe twierdzenie statystyki matematycznej

Niech $$X_1, ... X_n$$ będzie próbką prostą z rozkładu o dystybuancie $F$ 

Wówczas:

$$
P\left(\lim _{t \rightarrow \infty} \sup _{t \in R}|\hat{F_{n}}(t)-F(t)|=0\right)=1
$$

Dystrybuanta empiryczna zbiega do teoretycznej.

# Definicje

## Statystyka dostateczna

Statystykę dostateczną $T = T(X_1, ..., X_n)$ nazywamy **dostateczną** dla rodziny rozkładów $P = \{p_{\theta}, \theta \in \Theta\}$ (dla parametru $\theta$) jeżeli dla każdej wartości $t$ tej statystyki rozkład warunkowy próbki $(X_1, \dots, X_n)$ jpod warunkiem $T = t$ nie zależy od $\theta$.



# Wzory

# TODO

- [ ] Rozkłady łączne
- [ ] Rozkłady warunkwe
- [ ] Centralne twierdzenie  graniczne
- [ ] Zmienna Losowa
- [ ] Próbka - realizacja zmiennej losowej
- [ ] 



10 Mar 2020 [Mateusz Dorobek](https://mateuszdorobek.pl/)