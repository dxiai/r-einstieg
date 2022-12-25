Damit wir mit unseren Daten arbeiten können müssen wir diese erreichen können. Dabei helfen uns R-Variablen.

<p class="alert alert-primary">Definition: **Variablen** sind benannte Platzhalter, in denen wir beliebige Werte ablegen und über die wir diese Werte für unsere Arbeitsschritte wieder abrufen können.</p>

Ein Variablennname muss in R mit einem Buchstaben oder einem Punkt (`.`) beginnen und kann beliebig lang sein. Beginnt eine Variable mit einem Punkt, dann darf diesem Punkt nur ein weiterer Punkt oder ein Buchstabe folgen. Variablennamen dürfen nur aus Buchstaben, Unterstrichen (`_`), Punkten (`.`) und Ziffern bestehen.

<p class="alert alert-success">Sie sollten Variablennamen so wählen, dass sie den Inhalt der Variable beschreiben. Längere Variablennamen sind deshalb kürzeren vorzuziehen.</p>

Wir können jederzeit und fast überall in unseren Programmen Variablen erstellen und verwenden. 

#### Werte zuweisen

Wir können Werte einer Variable zuweisen. Mit einer Zuweisung erstellen wir entweder eine neue Variable oder überschreiben den Wert, der bisher in dieser Variable stand. Sobald Sie einen Wert in einer Variable zugewiesen haben, können Sie alle alten Werte nicht mehr über diese Variable abfragen. 

Uns stehen drei Operatoren zur Verfügung, um Werte einer Variable zuzuweisen. 

* `=` (Ist Gleich, "wird definiert als")
* `<-` (Linkszuweisung)
* `->` (Rechtszuweisung)

Bei der Links- und Rechtszuweisung kommt der Wert vom Anfang des Pfeils und die Variable ist das Ziel des Pfeils. Wir können und das so vorstellen, dass der Wert in Richtung des Pfeils in unsere Variable fliesst. 

***Beispiel***

```
meineVariable <- "Guten Tag"
"Hallo" -> meineAndereVariable
```

Das Gleichheitszeichen entspricht der Linkszuweisung. Wenn Sie also das Gleichheitszeichen für Zuweisungen verwenden, dann **muss** der Variablenname auf der linken Seite des Gleichheitszeichens stehen.

Selbstverständlich dürfen wir den Wert einer Variablen einer anderen Variablen zuweisen.

***Beispiel***

```
meineVariable <- "Guten Tag"
meineBegrüssung <- meineVariable
```

Damit enthalten die beiden Variablen den gleichen Wert `Guten Tag`. Jetzt können wir `meineVariable` einen neuen Wert zuweisen und können auf den alten Wert über die Variable `meineBegrüssung` immernoch zugreifen. 

##### Variablen und komplexe Datentypen

Wenn wir mehreren Variablen die gleiche Liste oder den  gleichen Vektor zuweisen, dann können wie Daten in allen Variablen gleichzeitig  verändern,  weil alle  Variablen auf die gleiche komplexe *Datenstruktur* verweisen. 

***Beispiel***

```
meineVariable = list(a = 1, b = 2, c = 4)
meineAndereVariable  = meineVariable

meineVariable$a = 8
print(meineAndereVariable$a)                 # ergibt  8
```

<p class="alert alert-primary">Diese fast "magische" Datenübertragung wird in der Programmierung  als *Seiteneffekt* oder als *Nebeneffekt* bezeichnet. Obwohl es gelegentlich gewünschte und sinnvolle Seiteneffekte gibt, sind solche Seiteneffekte eine häufiger Quelle für *logische* Fehler.</p>

#### Zuweisung von Funktionsparametern

Spezielle Variablennamen sind [Funktionsparameter](6_funktionen.md). In R sind Funktionsparameter benannt und erstellen Variablen, die nur in der jeweiligen Funktion gültig sind. Wenn Sie eine Funktion aufrufen, dann ergibt sich der Name des Parameters entweder aus der *Position* oder aus dem *Parameternamen*. Wir haben eine besondere  Form von benannten Funktionsparametern beim Erstellen von Listen mit  benannten Elementen kennengelernt.

Weil viele Parameter von R-Funktionen *optional* sind, ist es üblich Werte an diese optionalen Parameter über den Parameternamen zuzuweisen. Für diese Zuweisung *müssen* Sie das Gleichheitszeichen für die Zuweisung verwenden. Dabei steht der Parametername *immer* links vom Gleichheitszeichen.

#### Gleichheitszeichen oder Linkszuweisung?

Welche Zuweisungsoperatoren verwendet werden sollen, hat fast  religiöse Züge. Anfängern rate ich, nur das Gleichheitszeichen und die Rechtszuweisung zu verwenden, weil die Linkszuweisung nicht für Parameterzuweisungen funktioniert. 

Falls Sie nämlich die Linkszuweisung anstatt des Gleichheitszeichens in einem Funktionsaufruf verwenden, dann erstellen Sie eine Variable mit dem gleichen Namen wie der Funktionsparameter und übergeben nach der Zuweisung den Wert dieser Variable als `Postionsparameter` der Funktion. Diese Verwechslung der Zuweisung ist eine häufige Ursache für Fehlermeldungen.

Dieses Problem entsteht bei der Rechtszuweisung normalerweise nicht, weil die Werte in die umgekehrte Richtung fliessen. Dadurch lässt sich die Rechtszuweisung mit benannten Parametern schwerer verwechseln.

<p class="alert alert-success">Wenn Sie nur das Gleichheitszeichen als Zuweisungsoperator verwenden, können Ihnen Zuweisungsfehler von benannten Parametern nicht passieren.</p>

***Beispiel***

```
meineDaten = read_csv("meineDatei.csv", trim_ws = FALSE, col_names = FALSE)    # OK
meineDaten = read_csv("meineDatei.csv", trim_ws <- FALSE, col_names <- FALSE)  # Fehler, weil falsche Positionen

meineDaten = read_csv("meineDatei.csv", trim_ws = FALSE, col_names = FALSE -> spaltenNamenAus) # OK, aber schlechter Stil wegen geschachtelter Zuweisung. 
```

<p class="alert alert-success">Gewöhnen Sie sich an, Variablenzuweisungen *ausschliesslich* am Anfang oder am Ende einer Operation vorzunehmen.</p>
