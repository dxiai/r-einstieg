#### Vektoren

Vektoren sind der einfachste komplexe Datentyp in R. Ein Vektor ist als eine Folge von Werten vom gleichen Datentyp definiert. 

Wir können einen Vektor aus Werten zusammenstellen indem wir mit der `c()`-Funktion Werte zu einem Vektor *kombinieren*. 

***Beispiel***

``` 
c(1, 2, 4, 8) 
c(1, "2", 4, 8) # wird zu c("1", "2", "4", "8")
```

Wenn wir bei der `c()`-Funktion Datentypen mischen, dann wir der allgemeinste Datentyp verwendet, der für alle Werte gültig ist.

#### Listen 

Listen sind weniger streng definiert als ein Vektor. Mit Listen können wir verschiedene Werte mit beliebigen Datentypen zusammenfassen. 

***Beispiel***

```
list(1, "a", as.integer(1))  # Gültige Liste
```

Listen können darüberhinaus benannte Elemente haben. 

***Beispiel***

```
list(a = 1, b = "a", as.integer(1))
```

Wir erhalten die Namen der Listenelemente mit der `names()-Funktion.

***Beispiel***
```
names(list(a = 1, b = 2))  # Ergibt c('a', 'b')
```

Gelegentlich wollen wir Listenwerte nachträglich benennen. Dazu müssen wir die Reihenfolge der Elemente kennen. Hierfür weisen wir den Listennamen eine entsprechende Liste zu.

***Beispiel***

```
names(list(1,2,3)) <- c("a", "b", "c")
```

<p class="alert alert-danger">Den Werten in Vektoren können keine Werte zugewiesen werden.</p>

#### Auf Vektoren und Listenelemente zugreifen.

Um ein einzelnes Element aus einem Vektor zu extrahieren verwenden wir den `[]`-Operator. 

Der `[]`-Operator erlaubt es uns Elemente aus einem Vektor mit Hilfe eines zweiten Vektors zu extrahieren. Interessant ist dieser Operator, wenn wir einen Vektor mit Wahrheitswerten übergeben. In diesem Fall greifen wir nur auf die Elemente zu die im Auswahlvektor den Wert `TRUE` haben. 

***Beispiel***

```
( c(1, 2, 4, 8) )[c(2,4)]  # ergibt c(2, 8)

( c(1, 2, 4, 8) )[c(FALSE, TRUE, FALSE, TRUE)]  # ergibt c(2, 8)
```

Dieser Trick funktioniert auch mit Listen. 

#### Auf benannte Elemente von Listen zugreifen 

Wir können auf einzelne benannte Elemente in Listen mit Hilfe des `$` oder des `[[]]`-Operators zugreifen. Wir verwenden den `$`-Operator immer dann, wenn wir auf ein bestimmtes benanntes Object in einer Liste zugreifen wollen. Der `[[]]`-Operator ist grundsätzlich flexibler, weil wir den Namen oder den Index berechnen dürfen. 

***Beispiel***

```
meineListe = list(a = 1, b = 2, c = 4, d = 8, e = 16)

meineListe[["b"]]  # ergibt 2
meineListe$b       # ergibt 2
meineListe["b"]    # ergibt list(b = 2)

meineListe[[letters[2]]]  # ergibt 2
meineListe[[c("a", "b")]] # Verboten! Ergibt einen Fehler!
meineListe[c("a", "c")]   # ergibt list(a = 1, c = 4)
```

#### Besonderheiten von Vektoren

Mit R-Vektoren können wir rechnen wie wir es aus der Mathematik gewohnt sind. 

Wir können zwei Vektoren miteinander addieren und multiplizeren. Bei diesen Operationen beachten wir, dass die Werte jeweils paarweise zugeordnet sind. 

```
a = c(1,2,3,4)
b = c(1,2,3,4)

a + b # ergibt c(2, 4, 6, 8)
```

Auch die Skalar-Operationen funktionieren problemlos. 

```
3 * a # ergibt c(3, 6, 9, 12)
```

Falls bei Vektor-Operationen ein Vektor kürzer als der andere ist, dann wird der kürzere durch wiederholung soweit verlängert, dass beide Vektoren gleich lang sind. 

<p class="alert alert-warning">Wenn Sie Vektoren mit unterschiedlicher Länge addieren oder multiplizieren, dann erscheint eine Warnung, dass die Längen angepasst werden.</p>
