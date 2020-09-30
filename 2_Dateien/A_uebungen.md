# Übungen

#### Aufgage 1. Importieren Sie die Bibliothek `tidyverse` in ein neues Notebook.

* Erstellen Sie einen neuen Ordner für ein neues Notebook 
* Wechseln in diesen Ordner
* Erstellen Sie ein neues Jupyter Notebook .
* Verwenden Sie die `library()`-Funktion. 
* Führen Sie die Codezelle aus. 
* Prüfen Sie in einer neuen Codezelle mit der folgenden Operation, ob Ihr das Einbinden funktioniert hat: 

```
tibble(1) %>% pull() 
```

Das Ergebnis sollte `1` sein. 

War das Importieren erfolgreich sollten Sie als Ergebnis der ersten Codezelle auch die importierten `tidyverse`-Bibliotheken sehen. 

Hat das Importieren nicht funktioniert erhalten Sie eine Fehlermeldung als Ergebnis für *beide* Codezellen. 

#### Aufgabe 2. Öffnen Sie die `Inline Hilfe` (bzw. `Contextual Help`), so dass Sie das Hilfefenster *rechts neben* Ihren Notebook sehen. 

Klicken Sie im Notebook auf die `pull()`-Funktion und lesen die Funktionsbeschreibung. 

#### Aufgabe 3. Geben Sie Ihren Namen als Zeichenkette und Ihr Alter als Zahl in einer neuen Codezelle ein und führen Sie die Codezelle aus.

Schreiben Sie die beiden Werte in eine eigene Zeile. 

#### Aufgabe 4. Passen Sie die Codezelle aus Aufgabe 2 so an, dass Ihr Name und Ihr Alter in jeweils einer Variable gespeichert wird. 

* Verwenden Sie die Variablennamen `meinName` und `meinAlter`. 

Überprüfen Sie mit dem folgenden Code in einer neuen Codezelle, ob Ihre Zuweisung funktioniert hat. 

```
tibble(meinName, meinAlter)
```

Das Ergebnis sollte Ihren Namen und Ihr Alter als Tabelle darstellen. 

#### Aufgabe 5. Lesen Sie die angefügte CSV-Datei mit der `read_csv()` bzw. der `read_csv2()`-Funktion ein. 

* Laden Sie die Datei in den Ordner, in dem sich auch Ihr Notebook befindet. 
* Wählen Sie die richtige `read`-Funktion für die Daten. 
* Speichern Sie das Ergebnis der `read`-Funktion in die Variable `meineDaten`.

<a href=""><p class="button button-primary"><i class="fa fa-lg fa-download"></i> CSV Daten</p></a>

Überprüfen Sie mit dem folgenden Code, ob Ihre Funktion richtig funktioniert hat.

```
table(meineDaten)
```

Das Ergebnis sollte wie folgt aussehen: 

```
              Gerät
Geschlecht     2 : iPhone 3 : Android Smartphone
  1 : Andere            1                      0
  2 : Männlich         25                     19
  3 : Weiblich         18                     20
```

#### Aufgabe 6. Finden Sie heraus, was die `table()`-Funktion genau macht. 

* Lesen Sie die Dokumentation für diese Funktion.