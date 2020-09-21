Wir haben schon einige R-Funktionen kennengelernt. Tatsächlich sind Funktionen unser Hauptzugang, wenn wir mit R arbeiten. 

R-Funktionen haben einen Namen. Dieser Name beschreibt in der Regel, was die Funktion macht und ist eindeutig. Es kann also nicht zwei Funktionen mit dem gleichen Namen geben. 

Die meisten Funktionen haben *Parameter*. Ein Parameter ist eine besondere [Variable](variablen.md), die Werte an die Funktion zur Bearbeitung übergibt. R-Funktionen unterscheiden zwischen Positionsparametern und benannten Parametern. Bei Positionsparametern kommt es auf die Reihenfolge der Parameter beim Funktionsaufruf an. 

Bei benannten Parametern weisen wir dem Parameternamen einen Wert zu. Damit müssen wir uns nicht an die Reihenfolge der Parameter halten. Stattdessen können wir die Logik unseres Funktionsaufrufs deutlich festhalten.

<p class="alert alert-info">Viele R-Funktionen haben obligatorische und optionale Parameter. Es ist üblich, die <i>obligatorischen</i> Parameter als Positionsparameter und die <i>optionalen</i> Parameter als benannte Parameter an eine Funktion zu übergeben. </p>

Die meisten Funktionen haben ein Ergebnis. Dieses Ergebnis speichern wir am Besten in einer Variablen.

***Beispiel***

```
positionsParameter = "meineDatei.csv"
benannterParameter = FALSE

meinErgebnis = read_csv(positionsParameter, col_names = benannterParameter)
```

#### Funktionen umbenennen 

Wir können Funktionen umbenennen, indem wir eine Funktion einer [Variablen](variablen.md) zuweisen. Dabei dürfen wir nur den Funktionsnamen ohne Klammern verwenden. Daran erkennen wir, dass Funktionsnamen nichts anderes als Variablen sind. 

Diese Eigenschaft wird übrigens von der `help()`-Funktion genutzt, um die Dokumentation einer Funktion zu ermitteln. [Siehe auch Selbsthilfe](1_warum_r/5_selbsthilfe.md)