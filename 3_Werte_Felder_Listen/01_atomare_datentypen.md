Für uns sind in R drei atomare Datentypen zentral: 

* Zahlen
* Wahrheitswerte 
* Zeichenketten

#### Zahlen

R unterscheidet verschiedene Zahlentypen. Für uns am wichtigsten sind die *numerischen* Zahlen. In R werden dieser Datentyp als `numeric` bezeichnet. Diese Zahlen umfassen alle Zahlen die wir als Fliesskommazahlen darstellen können. Wenn wir eine Zahl eingeben oder aus einer Datei einlesen, dann geht R von diesem Datentyp aus. 

Neben den Fliesskommazahlen versteht R auch den Zahlenraum der ganzen Zahlen und die komplexen Zahlen. Diese beiden Zahlen werden als eigene Datentypen geführt: `integer` und `complex`. Beachten Sie, dass R ganze Zahlen falls nötig automatisch in Fliesskommazahlen umwandelt, aber trotzdem von diesen unterscheidet. 

Mit den `as.*`-Funktionen können wir den jeweiligen Datentyp überführen. 

Mit den `is.*`-Funktionen können wir den jeweiligen Datentyp überprüfen. 


***Beispiel***

```
is.numeric(1)   # TRUE
is.integer(1)   # FALSE
is.complex(1)   # FALSE

is.numeric(as.integer(1))   # TRUE
is.integer(as.integer(1))   # TRUE
is.complex(as.integer(1))   # FALSE

is.numeric(as.complex(1))   # FALSE
is.integer(as.complex(1))   # FALSE
is.complex(as.complex(1))   # TRUE
```

R erlaubt Zahlen in wissenschaftlicher Notation einzugeben. Diese Zahlen sind standardmässig ebenso Flieskommazahlen, wie andere Zahlen auch. Die wissenschaftliche Zahlennotation zeigt eine Zahl und ihre Grössenordnung zur Basis 10 an. 

Die Zahl `3000` lässt sich auch als $$3 * 10^3$$ ausdrücken. In R schreiben wir diese Zahl als `3e3`. 

Kleine Werte lassen sich durch ein negatives Vorzeichen des Exponenten darstellen. So können wir die Zahl `0.003` wissenschaftlich als $$3 * 10^{-3}$$ schreiben. Analog zum obigen Beispiel schreiben wir in R `3e-3`

####  Besondere Zahlen

R kennt einige spezielle Zahlen: 

* `pi` entspricht der Kreiszahl π
* `Inf` und `-Inf` entsprechen dem mathematischen unendlich bzw. negativ unendlich. Diese Werte stehen für Werte die sich nicht mehr als numerische Werte darstellen lassen. `Inf` wird nach der grössten bzw. kleinsten möglichen Fliesskommazahl erreicht. 
* `NaN` steht für `Not a Number`, damit werden normalerweise ungültige Zahlenwerte gekennzeichnet. Z.B. das Ergebnis der Division durch 0 ist `NaN`. 

#### Wahrheitswerte

Wahrheitswerte sind ein besonderer Datentyp in R. Dieser Datentyp hat nur zwei mögliche Werte `TRUE` (Wahr) und `FALSE` (Falsch). Wahrheitswerte sind normalerweise das Ergebnis von Vergleichsoperationen und logischen Ausdrücken.

#### Zeichenketten 

Zeichenketten sind Folgen von Symbolen. R bezeichnet diesen Datentypen als `character`.

Normalerweise denken wir bei Zeichenketten an Wörter. Aber ein Symbol kann ein beliebiges Zeichen sein. Z.B. eine Ziffer, ein Satzzeichen, ein Leerschlag oder Zeilenumbruch.

Zeichenketten werden in R entweder mit einem einfachen (`'`) oder doppelten Anführungszeichen (`"`) eingeschlossen. So können wir beliebige Werte in R eingeben. 

Sobald eine Folge von Symbolen zwischen Anführungszeichen steht, wird diese als Zeichenkette behandelt. R versucht nicht eine Zeichenkette automatisch zu konvertieren, wenn sie in mathematischen Operationen auftaucht. Das gilt auch dann, wenn eine Zeichenkette wie eine Zahl aussieht.

***Beispiel:*** Zeichenketten

``` 
"Hallo"
'Welt' 

"1"
is.character("1")  # TRUE
is.numeric("1")    # FALSE
```

***Beispiel:*** Zeichenketten und Operationen

```
"1" + 1 # Fehler "nicht-numerisches Argument für binären Operator"
```

Wir erkennen Zeichenketten in der Ausgabe von R immer an den einfachen Anführungszeichen.