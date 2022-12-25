Wir können in R zwar Werte direkt erfassen. In vielen Fällen möchten wir aber Daten aus anderen Systemen übernehmen und mit Hilfe von R bearbeiten und analysieren. Diese Daten erhalten wir in den meisten Fällen als Dateien. In der Regel werden solche Dateien Tabellen mit Stichprobendaten enthalten.

#### Daten aus Dateien mit `readr` einbinden

Das Einlesen von Datendateien ist ein zentraler Bestandteil von R, weil es die Voraussetzung für die statistische Programmierung bildet. Diese Funktionen gehen jedoch nicht sehr sparsam mit dem Arbeitsspeicher unseres Computers um, so dass sehr grosse Datenmengen immer wieder zu Problemen führen. 

Die `readr`-Bibliothek ersetzt die Base R-Funktionen zum Einlesen von Dateien durch flexiblere und effizientere Funktionen. Diese Funktionen können mit grösseren Datenmengen umgehen und schonen den verfügbaren Arbeitsspeicher. Deshalb sind die `readr`-Funktionen den jeweiligen Gegenstücken von Base R vorzuziehen.


#### Dateitypen

Für den Austausch von Stichproben stehen verschiedene Dateiformate zur Verfügung. Diese Dateiformate unterscheiden sich im wesentlichen in der Strategie, wie die Werte in den einzelnen Tabellenzellen unterschieden werden. 

Die wichtigsten Formate sind: 

* Tabulator getrennte Werte (TSV, tabulator-separated values)
* Komma getrennte Werte (CSV, comma-separated values)
* Excel Tabellen (via `readxl`-Bibliothek)
* Fixformat Tabellen (FWF, fixed-width format)
* R-Datendateien (RDS, R-data structure)

Diese Dateien können wir mit den folgenden Funktionen einlesen.

| Format | Modern R | Base R |
| --- | --- | --- |
| csv (mit `,` als Trennzeichen) | `read_delim()` | `read.csv()` |
| csv (mit `;` als Trennzeichen) | `read_delim()` | `read.csv2()` |
| tsv | `read_delim()` | `read.delim()` |
| xls (Excel Arbeitsmappen mit `readxl`) | `read_excel()` | - |
| FWF | `read_fwf()` | - |
| RDS | `read_rds()` | `readRDS()` |

Bei der modernen Variante können wir uns leicht an der Dateiendung orientieren, um die richtige `read_`-Funktion auszuwählen. 

Wenn wir eine Datei einlesen, dann gibt uns die jeweilige `read_`-Funktion zurück, wie die Datei eingelesen wurde. Sofern die Datei Spaltenüberschriften enthält können wir daran erkennen, dass wir das richtige Dateiformat eingelesen haben. 

<p class="alert alert-warning" markdown="1">
Falls wir nur einen *Datenvektor* importiert haben, müssen wir die Datei ggf. mit der ``read_csv``-Funktion einlesen, weil R das (fehlende) Trennzeichen nicht erkennen kann.
</p>

***Beispiel***

Mit dem Aufruf `read_delim("beispieldaten.csv")` werden Daten mit einem Komma als Trennzeichen eingelesen. 

#### Rohdaten direkt einlesen

Alle `readr`-Funktionen erwarten entweder einen Dateinamen oder Rohdaten als ersten Parameter. Rohdaten entsprechen normalerweise dem Dateiinhalt. Gelegentlich haben wir jedoch keine Datei, sondern haben die Rohdaten aus einer anderen Quelle erhalten. Die `readr`-Funktionen erkennen, ob sie mit einem Dateinamen oder Rohdaten aufgerufen wurden und lesen die Daten automatisch in eine R-Datenstruktur. 

Im nächsten Abschnitt haben wir ein Beispiel, wie Rohdaten eingelesen werden. 

#### Daten aus Excel via Kopieren und Einfügen einbinden. 

Wir können schnell Daten aus einer Excel Tabelle in R einlesen. Dabei nutzen wir aus, dass Excel beim Kopieren die Werte im `TSV`-Format übergibt. Entsprechend können wir diese Daten mit der `read_tsv()`-Funktion in R einbinden. Wir gehen dabei wie folgt vor: 

1. Markieren Sie in Excel den Bereich mit den zu übertragenden Daten. Ideal ist es, wenn dieser Bereich auch Überschriften enthält. 
1. Kopieren Sie den ausgewählten Bereich mit `C-c` (Win) oder `Cmd-c` (Mac).
1. Wechseln Sie in Ihre R Arbeitsumgebung. 
1. Erstellen Sie den Funktionsaufruf `read_tsv("")`.
1. Bewegen Sie den Textcursor zwischen die beiden Anführungszeichen.
1. Fügen Sie die kopierten Daten mit `C-v` (Win) bzw. `Cmd-v` (Mac) ein.
1. Führen Sie die `read_tsv()`-Operation aus.

Das folgende Beispiel illustriert den `read_tsv()`-Aufruf.

```
> read_tsv("Foo	bar	baz
6	31	8
23	42	19
33	42	16
29	17	29
18	13	43
26	12	16
19	31	9
21	21	21
19	29	14
35	29	25")
```

Dieser Aufruf hat das folgende Ergebnis: 

```
A tibble: 10 × 3

Foo	bar	baz
<dbl>	<dbl>	<dbl>
6	31	8
23	42	19
33	42	16
29	17	29
18	13	43
26	12	16
19	31	9
21	21	21
19	29	14
35	29	25

```

<p class="alert alert-warning">Wenn Sie einen Bereich ohne Überschriften kopieren, dann müssen Sie zusätzlich den Parameter ``col_names`` auf ``FALSE`` setzen.</p>

***Beispiel***

```
> read_tsv("6	31	8
23	42	19
33	42	16
29	17	29
18	13	43
26	12	16
19	31	9
21	21	21
19	29	14
35	29	25", col_names = FALSE)
```

#### Daten aus Excel-Arbeitsmappen einlesen

Die `readr`-Bibliothek kann **keine** Excel Arbeitsmappen einlesen. Stattdessen müssen wir die `readxl`-Bibliothek verwenden. Wenn wir also Excel-Arbeitsmappen einlesen möchten, müssen wir zusätzlich die `readxl`-Bibliothek mit `library(readxl)` importieren.

Die `readxl`-Bibliothek ist eine logische Fortsetzung der `readr`-Bibliothek. Entsprechend haben die Funktionen die gleichen Parameter wie die Funktionen der `readr`-Bibliothek.  Die `readxl`-Bibliothek hat drei Funktionen: 

* `read_excel()`
* `read_xls()`
* `read_xlsx()`

Wenn wir es mit Dateien aus Office 365 zu tun haben können wir problemlos die Funktion `read_xlsx()` verwenden. Wenn wir Arbeitsmappen aus älteren Excel-Versionen erhalten, dann ist es sicherer die `read_excel()`-Funktion zu verwenden. Diese Funktion prüft, welches Excel-Datenformat vorliegt und ruft die richtige Funktion für uns auf. 

Weil alle drei Funktionen die gleichen Parameter akzeptieren, wird im Folgenden nur auf die allgemeine Funktion `read_excel()` verwiesen. 

Wenn wir `read_excel()` nur mit dem Dateinamen aufrufen, dann liesst `read_excel()` immer das erste Arbeitsblatt ein. Das ist das Arbeitsblatt, das in Excel zu äusserst links in den Arbeitsblattreitern steht. Das muss nicht unbedingt das aktive Arbeitsblatt der Arbeitsmappe sein.

Um ein beliebiges Arbeitsblatt einzulesen, müssen wir den `sheet`-Parameter verwenden. Mit diesem Parameter können wir das gewünschte Arbeitsblatt explizit über dessen Namen einlesen. Alternativ können wir die Position des gewünschten Arbeitsplatts als Zahl angeben. Dabei zählt `read_excel()` die Positionen von links nach rechts. 

***Beispiel***

Nehmen wir an, wir hätten eine Arbeitsmappe in der Datei `BeispielR.xlsx`. Diese Arbeitsmappe soll drei Arbeitsblätter mit den folgenden Namen haben: 

* `Teil A`
* `Teil B`
* `Teil C` 

Die Operation `read_excel("BeispielR.xlsx")` liesst den Inhalt des Arbeitsblatts `Teil A` ein. 

Die Operation `read_excel("BeispielR.xlsx", "Teil B")` liesst den Inhalt des Arbeitsblatts `Teil B` ein. 

Die Operation `read_excel("BeispielR.xlsx", 3)` liesst den Inhalt des Arbeitsblatts `Teil C` ein. 

Falls die Daten auf Ihren Arbeitsblättern keine Überschriften haben, setzen Sie ausserdem den Parameter `col_names = FALSE`. 
