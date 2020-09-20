Nachdem Sie R installiert haben, können Sie nur `Base R` verwenden. Damit wir `Modern R` oder komplexere Funktionen verwenden können, müssen wir Bibliotheken installieren. 

Die `Base R`-Funktion zum installieren von Bibliotheken ist `install.packages()`

#### Bibliotheken für modernes R 

Die wichtigsten Bibliotheken für `Modern R` verwenden können benötigen wir die folgenden Bibliotheken: 

* ggplot2
* tidyr
* dplyr
* stringr
* readr
* purrr
* forcats
* tibble

Diese Bibliotheken werden gemeinsam als *Tidyverse* bezeichnet und wir können alle zugehörigen Bibliotheken auf einmal installieren. Dazu geben wir in der R-Console den  Befehl `install.packages("tidyverse")` ein. R zeigt uns im Anschluss an, welche Bibliotheken installiert werden. Abschliessend müssen wir die Installation mit `yes` bestätigen. Dazu geben wir auf der Tastatur die Buchstaben `yes` ein und tippen danach die `Eingabe`-Taste. Alternativ können wir die Installation an dieser Stelle mit der Eingabe von `no` oder `cancel` abbrechen. 

Danach werden alle notwendigen Komponenten auf Ihrem Rechner installiert. 

<p class="alert alert-warning">Es kann eine Weile dauern, bis R alle Bibliotheken und Komponenten auf Ihrem Rechner installiert hat. Seien Sie geduldig! Sie dürfen diesen Prozess nicht abbrechen.</p>

Nachfolgend sehen Sie die ersten Schritte der Installation. 

```r
> install.packages("tidyverse")
also installing the dependencies ‘desc’, ‘pkgbuild’, ‘rprojroot’, ‘pkgload’, ‘praise’, ‘colorspace’, ‘sys’, ‘ps’, ‘highr’, ‘markdown’, ‘testthat’, ‘farver’, ‘labeling’, ‘munsell’, ‘RColorBrewer’, ‘viridisLite’, ‘askpass’, ‘rematch’, ‘prettyunits’, ‘processx’, ‘knitr’, ‘yaml’, ‘htmltools’, ‘evaluate’, ‘base64enc’, ‘tinytex’, ‘xfun’, ‘backports’, ‘ellipsis’, ‘generics’, ‘glue’, ‘assertthat’, ‘fansi’, ‘DBI’, ‘lifecycle’, ‘R6’, ‘tidyselect’, ‘blob’, ‘vctrs’, ‘digest’, ‘gtable’, ‘isoband’, ‘scales’, ‘withr’, ‘Rcpp’, ‘pkgconfig’, ‘curl’, ‘mime’, ‘openssl’, ‘utf8’, ‘clipr’, ‘BH’, ‘cellranger’, ‘progress’, ‘callr’, ‘fs’, ‘rmarkdown’, ‘whisker’, ‘selectr’, ‘stringi’, ‘cpp11’, ‘broom’, ‘cli’, ‘crayon’, ‘dbplyr’, ‘dplyr’, ‘forcats’, ‘ggplot2’, ‘haven’, ‘hms’, ‘httr’, ‘jsonlite’, ‘lubridate’, ‘magrittr’, ‘modelr’, ‘pillar’, ‘purrr’, ‘readr’, ‘readxl’, ‘reprex’, ‘rlang’, ‘rstudioapi’, ‘rvest’, ‘stringr’, ‘tibble’, ‘tidyr’, ‘xml2’


  There is a binary version available but the source version is later:
        binary source needs_compilation
openssl  1.4.2  1.4.3              TRUE

Do you want to install from sources the package which needs compilation? (Yes/no/cancel) yes
```

#### Andere Bibliotheken auf Ihrem Rechner installieren

Falls Sie andere Bibliotheken für R und R-Studio installieren möchten, verwenden Sie ebenfalls die `install.packages()`-Funktion. Geben Sie den Namen der gewünschten Bibliothek als [Zeichenkette](../3_Werte_Felder_Listen/02_zeichenketten.md) ein. 

<p class="alert alert-warning">Falls eine Bibliothek mit dem angegebenen Namen nicht existiert oder Sie geben gar keinen Namen an, wird R eine Fehlermeldung ausgeben. Lesen Sie die Fehlermeldung *genau* und beheben Sie den Fehler, damit Sie die gewünschte Bibliothek installieren können.</p>
