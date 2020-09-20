# Hilfe bekommen

R-Funktionen sind in der Regel gut dokumentiert. Neben der eigentlichen Funktionsbeschreibung finden sich viele ausführliche Problemlösungsstrategien in Form sog. *Vignettes*. Zusätzlich finden sich für die `tidyverse`-Module sog. *Cheat Sheets*. Die einen schnellen Überblick über die Kernfunktionen erlauben. 

<p class="alert alert-success"><i class="fa fa-lg fa-lightbulb-o"></i> Nutzen Sie die Dokumentation regelmässig, um die richtigen Funktionen für Ihre Problemstellungen auszusuchen. Die verschiedenen Teile der R-Dokumentation helfen Ihnen die Konzepte und Techniken für die Arbeit mit R zu vertiefen.</p>

#### help(funktionsname)

Die `help()`-Funktion ist der erste Anlaufpunkt, um mehr über eine Funktion zu erfahren. 

R-Funktionen sind in der Regel sehr ausführlich dokumentiert. Falls Sie Details über die Arbeitsweise einer Funktion erfahren möchten, können Sie die Dokumentation einer Funktion mit der `help()`-Funktion abrufen. Dazu rufen Sie diese Funktion wie jede andere R-Funktion auf. 

Die `help()`-Funktion ist Teil von `Base R` und ist in jeder Umgebung verfügbar. 

Die Funktion erwartet den gewünschten Funktionsnamen. `help()` kann der Funktionsname direkt oder als Zeichenkette als Parameter übergeben werden. D.h. die beiden folgenden Operationen haben den geleichen Effekt und zeigen die Dokumentation der Funktion `read.csv` an.

```r
> help(read.csv)
> help("read.csv")
```

Jedes Funktionsdokumentation besteht aus den folgenden Teilen:

1. Beispielen für den Aufruf der Funktion
2. Besschreibung aller Funktionsparameter
3. Einer Detaillierten Funktionsbeschreibung
4. Beispielen

Die Beispiele zeigen typische Aufrufe der jeweiligen Funktion und finden sich **immer** *am Ende* der Dokumentation. Es lohnt sich häufig zu erst die Beispiele anzusehen und danach die Funktionsdetails zu lesen. 

In Jupyter Notebooks wird die Hilfe direkt unter dem Aufruf der help() Funktion angezeigt. Das ist nicht immer praktisch. Deshalb wird empfohlen, die *Jupyter Notebook Inline Hilfe* zu verwenden. 

![Jupyter Notebook Hilfe](jupter_help.png)

<p class="alert alert-warning"><i class="fa fa-lg fa-exclamation-triangle"></i> In R-Studio wird die Dokumentation immer separat angezeigt! Beim Aufruf der `help()`-Funktion wird automatisch der Reiter `Help` aktiviert.</p>

![R-Studio Hilfe Funktion](rstudio_hilfe.png)

#### Jupyter Inline Hilfe

Jupyter Notebooks verfügen über die Option einer sogenannten *inline Hilfe*. Diese Funktion ruft die Dokumentation für die Funktion auf, die Sie gerade mit dem Cursor ausgewählt haben. 

![Jupyter Notebooks Inline Hilfe](jupyter_inline_hilfe.png)


#### Vignettes

Viele R-Bibliotheken haben komplexe Anwendungen. Diese Anwendungen werden in sogenannten *Vignettes* beschrieben. 

Sie können sich die verfügbaren Vignettes für eine Bibliothek mit der Operation `vignette(package = bibliotheksname)` anzeigen lassen. Wenn Sie z.B. alle Vignettes für die dplyr Bibliothek anzeigen lassen möchten, dann geben Sie `vignette(package = "dplyr")` ein. Das Ergebnis ist Liste der verfügbaren Vignettes für diese Bibliothek. 

![Vignettes für die DPlyr Bibliothek](vignette_list_dplyr.png)

Wenn Sie das gesuchte Thema gefunden haben, dann können Sie sich die Vignette mit dem folgenden Befehl anzeigen lassen: `vignette(thema, package = bibliotheksname)`
 
<p class="alert alert-warning"><i class="fa fa-lg fa-exclamation-triangle"></i> In <b>Jupyter Notebooks</b> können <code>vignettes</code> nicht direkt angezeigt werden. Hier hilft Ihnen Google weiter: Geben Sie als Suche <code>vignette bibliotheksname thema</code> ein und der erste Treffer verweist normaler Weise auf die entsprechende Vignette. Dabei ist <code>thema</code> eine Thema, das in der Spalte <code>Item</code> der Ausgabe der <code>vignette()</code>-Funktion angezeigt wird. z.B. <code>vignette dplyr programming</code></p>

#### Cheat Sheets

Die *tidyverse*-Bibliotheken bieten zusätzlich *Schummelzettel* für die wichtigsten Funktionen und Techniken für eine Bibliothek auf zwei Seiten. Diese Schummelzettel werden auch als *Cheat Sheets* bezeichnet. Sie können diese Cheat Sheets doppelseitig ausdrucken und als Schnellreferenz verwenden.

#### Hilfreiche Webseiten und Literatur

Weiterführende Literatur zu verschiedenen Arbeitstechniken mit R finden Sie auf verschiedenen Web-Seiten und Büchern.

Gute allg. Referenzwerke sind: 

* G. Grolemund and H. Wickham (2017). R for Data Science. O'Reilly ([Online Version](https://r4ds.had.co.nz/)). 
* J. Albert and M. Rizzo (2012). R by Example, Use R! Springer.
* J. Long and P. Teetor (2019). R Cookbook. O'Reilly ([Online Version](https://rc2e.com/)
