Ein besonderer Datentyp von R sind sogenannte *Data-Frames*. Data-Frames fassen Vektoren zusammen, so dass wir die Vektoren als Einheit behandeln können. Damit entsprechen Data-Frames Tabellen in Excel, in denen die Spalten die Vektorennamen sind und die Werte in jeder Zeile zusammen gehören. 

Wir können Data-Frames mit zwei Funktionen erstellen: 

* `data.frame` (Base R)
* `tibble` (Modern R)

Die beiden Funktionen und die entstehenden Data-Frames sind für uns in der Anwendung identisch. Unter der Oberfläche sind die Data-Frames der `tibble`-Funktion flexibler und effizienter im Umgang mit Daten. Ich empfehle daher, **immer** die `tibble`-Funktion zur Erstellung von Data-Frames zu verwenden.

Wir können einen Data-Frame mit der `tibble`-Funktion aus existierenden Vektoren oder Listen erstellen. Falls Sie Listen an die `tibble`-Funktion übergeben, dann wird diese Liste in einen Vektor mit gleichen Datentypen umgewandelt. Dabei versucht `tibble` immer den "besten" Datentypen für die Werte auszuwählen. Das macht sich bemerkbar, wenn wir Listen mit Zahlen und Zeichenketten mit Ziffern übergeben. Dann konvertiert die `tibble`-Funktion die Ziffernfolgen automatisch.

Der Vektorenname ergibt sich entweder aus dem Variablennamen des Vektors oder wir können den Namen selbst setzen.

***Beispiel***

```
> meineDaten = tibble(meineListe, Sequenz = a)
> meineDaten

# A tibble: 5 x 2
  meineListe   Sequenz
  <named list>   <int>
1         1          1
2         2          2
3         4          3
4         8          4
5        16          5
```

Wir können auf die Vektoren in einem Data-Frame wie auf benannte  Listenelemente zugreifen. Selbstverständlich können wir Data-Frames Variablen zuweisen. 

<p class="alert alert-info">Data-Frames sind *keine* speziellen Listen: Während bei Listen keine Beziehungzwischen den einzelnen Elementen besteht, haben die Vektoren eines Data-Frames alle die gleiche Länge und die Werte an der gleichen Position sind miteinander verknüpft.</p>

Wir können auf die einzelnen Vektoren wie bei Listen mit dem `[[]]`-Operator oder dem `$`-Operator zugreifen. 

***Beispiel***

```
meineDaten$Sequenz  # ergibt c(1, 2,  3, 4, 5)
meineDaten[["Sequenz"]] # ergibt auch c(1, 2,  3, 4, 5)
``` 

<p class="alert alert-info">In der Praxis werden wir selten mit diesen Operatoren arbeiten, weil wir in Modern R mit speziellen Funktionen arbeiten</p>

#### Daten aus Dateien

Wenn wir Daten aus Dateien mit einer der [`readr`-Funktionen](../2_Dateien/1_dateien.md) einlesen, dann erhalten wir automatisch `tibble` Data-Frames als Ergebnis.
