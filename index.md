---
title       : Outils de visualisation sur R
subtitle    : Laboratoire de Biostatiques (Chapitre 2)
author      : Steve Vissault
job         : Laboratoire d'écologie théorique
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [quiz, bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Chargement des données ##

On charge un exemple de données


```r
dat  <- iris
```

- **Iris** est un jeu de données intégré dans R (parfait pour des exemples)

**Aprés avoir chargé un jeu de données, on fait quoi ?**

---
## Chargement des données ##

Vérification de sa structure


```r
str(dat)
```

```
## 'data.frame':	150 obs. of  5 variables:
##  $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
##  $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
##  $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
##  $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
##  $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
```

---
## Chargement des données ##

À quoi ces données ressemblent?


```r
head(dat)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```

---  Visualiser les données

## Visualiser les données ##

On peut mettre en relation deux variables quantitatives en créant un nuage de points 


```r
plot(dat$Sepal.Length,dat$Sepal.Width)
```

<img src="assets/fig/unnamed-chunk-4.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />

---  Visualiser les données

## Visualiser les données ##

La fonction `plot()` peut créer un nuage de points pour chaque paire de variables


```r
plot(dat)
```

<img src="assets/fig/unnamed-chunk-5.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />

**ATTENTION:** Il y a des bonnes et des mauvaises facons de représenter des données... 

---  Visualiser les données

## Visualiser les données ##

Pour illustrer la distribution d'une variable quantitative avec une variable nominale, on utilise généralement des boites à moustache
    

```r
boxplot(Sepal.Length ~ Species, data=dat)
```

<img src="assets/fig/unnamed-chunk-6.png" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" style="display: block; margin: auto;" />

---  Visualiser les données

## Visualiser les données ##

Si je m'intéresse à la distribution de fréquence d'une variable quantitative, j'utilise plutôt **un histogramme**:
    

```r
hist(log(dat$Sepal.Length))
```

<img src="assets/fig/unnamed-chunk-7.png" title="plot of chunk unnamed-chunk-7" alt="plot of chunk unnamed-chunk-7" style="display: block; margin: auto;" />

Il éxiste une infinité de possibilités de graphiques sur R...

--- Visualiser les données

## Visualiser les données ##

**Qu'est ce qui n'est pas conforme dans ce graphique?**

> - Le titre et le nom des axes doivent être changer, pour mieux décrire le contenu du graphique
    

```r
hist(log(dat$Sepal.Length))
```

<img src="assets/fig/unnamed-chunk-8.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" style="display: block; margin: auto;" />

--- Visualiser les données

## Visualiser les données ##
    

```r
hist(log(dat$Sepal.Length),main = "Histogramme de fréquence ")
```

<img src="assets/fig/unnamed-chunk-9.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" style="display: block; margin: auto;" />

---  Personnaliser les figures

## Bien illustrer ##

**Trois choses primordiales:**

1. Utiliser un type de figure approprié à ce que l'on veut montrer (boxplot, plot, hist..)
2. Bien décrire les variables d'interêts (Axes, légende, titre descriptif) - **Voir guide de rédaction**
3. Ne pas hésitez à adapter (personnaliser) votre figure pour mettre en valeur votre résultat

