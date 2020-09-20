R-Bibliotheken sind besondere Dateien. Sie beinhalten R-Funktionen, die wir für unsere Arbeit nutzen können. Nur weil wir eine R-Bibliothek in unserer Arbeitsumgebung installiert haben, können wir sie aber noch nicht in unserer R-Programmen verwenden. Damit  wir eine Bibliothek verwenden können müssen wir sie in unsere Programme *importieren*. Das erreichen wir mit der `library()`-Funktion. Mit  dieser Funktion steht R ein sehr flexibles System zur Erweiterung und Verbesserung der Funktionalität zur Verfügung. 

Mit der `library()`-Funktion importieren wir eine Bibliothek in ein Programm. Der Aufruf `library(bibliotheksname)` läd eine installierte R-Bibliothek in unser Programm. Dabei müssen wir natürlich einen gültigen Bibliotheksnamen verwenden. Diesen können wir entweder direkt oder als Zeichenkette der  Funktion übergeben.

Normalerweise würden wir erwarten, dass wir wissen müssen, in welchem Verzeichnis eine Bibliothek installiert ist. Das ist bei R nicht der Fall. R organisiert die Installation selbst, so dass R "weiss", wo die gewünschte Bibliothek zu finden ist. 

Nachdem eine Bibliothek in unser Programm importiert wurde, können wir die bereitgestellten Funktionen verwenden.

<p class="alert alert-warning">Ein häufiger Fehler ist der Aufruf einer Funktion, bevor die entsprechende Bibliothek importiert wurde. Wenn Sie den Fehler erhalten, dass R eine Funktion nicht finden konnte, dann bedeutet das, dass Sie die jeweilige Bibliothek (noch) nicht importiert haben.</p>

Das Importieren funktioniert natürlich nur solange gut, wenn die Bibliothek auch installiert ist. Falls eine Bibliothek nicht installiert ist, erhalten wir von der `library()`-Funktion eine Fehlermeldung. 

![Fehlermeldung für eine nicht installierte Bibliothek]()

Es gibt zwei Ursachen für diese Fehlermeldung.

1. Die gewünschte Bibliothek ist nicht installiert.
2. Sie haben die Bibliothek falsch geschrieben. 

#### Modernes R

Die Syntax und die Funktionen für das moderne R wird als Bibliothek eingebunden. Dabei sind die verschiedenen Funktionen in verschiedene Bibliotheken gegliedert. Zum Glück müssen wir uns nicht merken, welche Bibliotheken wir einbinden müssen, um alle modernen Funktionen und Operatoren zu erhalten. Stattdessen importieren wir die `tidyverse`-Bibliothek. 

Die `tidyverse`-Bibliothek importiert alle wichtigen Teile für die Programmierung nach den aktuellen R-Prinzipien. Entsprechend wollen wir am Anfang unserer Programme immer diese Bibliothek mit der Operation `library(tidyverse)` importieren. 

![Import und Ausgabe der tidyverse Bibliothek in Jupyter Notebooks]()

#### R-Bibliotheken installieren

Falls eine Bibliothek in unserer Arbeitsumgebung nicht installiert ist, können wir sie installieren. Dazu verwenden wir die `install.packages()`-Funktion. 

<p class="alert alert-info">Die bereitgestellte Jupyter Notebook Umgebung hat bereits alle notwendigen Bibliotheken für die Lehrveranstaltungen installiert. </p>

<p class="alert alert-warning">Falls Sie eine besondere Bibliothek verwenden möchten, dann müssen Sie sie für *jede Sitzung* neu installieren, weil die installierten  Bibliotheken zwischen den Sitzungen nicht erhalten bleiben.</p>