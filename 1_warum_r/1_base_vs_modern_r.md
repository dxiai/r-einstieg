# Motivation

R ist eine sogenannte *Statistiksprache*. Dabei handelt es sich um eine *Programmiersprache*, die speziell für die Bearbeitung statistischer und stochastischer Problemstellungen optimiert wurde. 

R ähnelt in vielen Belangen EXCEL, mit dem entscheidenden Unterschied, dass wesentlich grössere Datenmengen effizient bearbeitet werden können. Der zweite Unterschied zu Excel ist, dass bei R die operativen Arbeitsschritte im Vordergrund stehen. Während uns Excel als Erstes Daten und Ergebnisse präsentiert, wird bei R die *Vorgehensweise* hervorgehoben. Damit werden die *Algorithmen* als *Code* sichtbar. Im Gegensatz zu Excel kann R erweitert werden, so dass wir nicht nur auf die bestehenden Funktionen angewiesen sind. Der Vorteil dieser Erweiterbarkeit ist eine bessere *Nachvollziehbarkeit* und *Lesbarkeit* des Codes unserer Programme. Dadurch werden Konzepte einfach zugänglich, die mit Tabellenkalkulationen wie Excel nicht oder nur sehr umständlich umzusetzen sind.

R ist eine *Open Source* Implementierung und Weiterentwicklung der Programmiersprache S, die vor über vierzig Jahren an den Bell Labs entwickelt wurde. R wird seid 1997 aktiv entwickelt und ist heute laut dem TIOBE Index eine der 10 populärsten Programmiersprachen, die in der Software-Industrie eingesetzt werden ([TIOBE, 2020](https://www.tiobe.com/tiobe-index/)). R ist vor Allem für Anwendungen zur wissenschaftlichen Berechnung (dem *scientific Computing*) besonders geeignet. Das scientific Computing bildet die Grundlage für die sogenannten *Data Sciences*.  

Den Kern von R bildet ein *Sprachinterpreter*. Dabei handelt es sich um ein Programm, dass unseren Programmcode in Maschinencode *übersetzt* und direkt auf unserem Computer *ausführt*, bis unser Programmcode zu Ende ist oder ein Fehler auftritt. Der Sprachinterpreter gibt vor, welche Symbole (Werte, Operatoren, Funktionen) in welcher Reihenfolge gültige (d.h. interpretierbare) Aussagen für ein R Programm sind. Diese Vorgaben sind als Regeln festgelegt, die als *Programmsyntax* bezeichnet werden. Von der gültigen Programmsyntax darf nicht abgewichen werden, sonst gibt es einen Programmfehler. In diesem Fall sprechen wir von einem *Bug*. Obwohl wir von der Programmsyntax von R nicht abweichen dürfen, gibt es oft mehr als einen Weg, um das gleiche Ziel als Programmcode *auszudrücken*. Die Grundlage für die verschiedenen Ausdrucksformen werden als *Grammatik* einer Programmiersprache bezeichnet. 

#### Base R

R verfügt über eine umfangreiche Syntax, die im Laufe der Zeit schrittweise erweitert wurde. Bei Programmiersprachen ist es üblich, dass alte Programme auch von neuen Versionen des Sprachinterpreters verstanden werden. So können mit der aktuellen Version von R auch vierzig Jahre alte S-Programme noch ausgeführt werden. Die dafür notwendige Syntax und Grammatik sind direkt im Sprachinterpreter festgelegt und sind für alle R-Programme verfügbar. Im R-Umfeld werden diese Konzepte als `Base R` bezeichnet.

Ein Grossteil der Fachliteratur zu R bezieht sich auf diese Basis-Funktionalität. Weil R jedoch eine lange Geschichte hat, haben sich einige Ausdrucksformen eingeschlichen, die aus heutiger Sicht nicht immer konsistent oder nachvollziehbar sind. Viele dieser gewachsenen Konzepte lösen zwar die jeweiligen Probleme gut, sind aber zum Teil schwer zu merken oder klingen altmodisch und geschwollen. Das zeigt sich vor Allem an den Base-R-Funktionen zur Datenvisualisierung. 

#### Modern R

Etwa 2005 wurde ausgehend von den Grafikfunktionen ein neuer strukturierter Zugang zur R-Programmierung entwickelt. Im Zentrum dieser Entwicklung steht die Nachvollziehbarkeit der Strukturen von R Programmen. Den Beginn hat die Grafikbibliothek ggplot2 gemacht. Diese Programmbibliothek ermöglicht es, Datenvisualisierungen strukturiert und konsistent beschrieben werden. Diese Prinzipien wurden nach und nach auf andere Bereiche der R Syntax ausgeweitet. Diese neuen Zugänge zur R Programmierung erlauben nicht nur eine saubere und leichter verständliche Struktur von R-Programmen, sondern können grössere Datenmengen besser und schneller verarbeiten. Im Zentrum dieser Entwicklung steht das Konzept der sauberen Datenstruktur (tidy data), die eine Grundlage für komplexere Anwendungen der Data Sciences ist ([Wickham, 2013](https://www.jstatsoft.org/index.php/jss/article/view/v059i10/v59i10.pdf)). Zu diesen Anwendungen gehört insbesondere das maschinelle Lernen. 

Aus diesen Entwicklungen hat sich in den letzten 8 Jahren eine modernere R-Syntax entwickelt, die sich an den Prinzipien der funktionalen Programmierung orientiert. Dadurch werden R Programme transparenter und konsistenter, wodurch sie leichter zu verstehen sind. Den Kern dieser modernen R Syntax bilden verschiedene R-Bibliotheken, die unter dem Namen `tidyverse` zusammengefasst werden.

#### Base R oder Modern R

Im Gegensatz zu Base R benötigt die moderne Arbeit zusätzliche Bibliotheken. Diese zusätzlichen Bibliotheken werden als *Abhängigkeiten* bezeichnet. Gelegentlich ist es notwendig, dass ein Programm keine Abhängigkeiten haben darf. In solchen Fällen dürfen nur Funktionen des R Interpreters verwendet werden. Solche Anforderungen sind aber in der Praxis sehr selten, so dass es keine Gründe gibt, nicht mit den modernen R-Konzepten zu arbeiten. 

<p class="alert alert-success">Es ist eine gute Übung, Base R-Strategien in moderne R Syntax zu übersetzen. </p>

