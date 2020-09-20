# Alternativen zu R

R ist nicht die einzige statistische Programmiersprache. Hier werden ein paar der bekanntesten Alternativen diskutiert.

Direkt lässt sich R mit [IBM's `SPSS`](https://www.ibm.com/analytics/spss-statistics-software) vergleichen. Die grundsätzlichen Vorgehensweisen zur Problemlösung sind in beiden Umgebungen sehr ähnlich. `SPSS` ist keine Open Source Anwendung und muss kommerziell lizensiert werden. Die Funktionen von SPSS lassen sich weniger leicht mit modernen Data Science Anforderungen verbinden, weil `SPSS` ähnlich wie `EXCEL` den Fokus auf die Datenauswertung legt und nicht auf die statistische Programmierung. 

Die beiden Erweiterungen [`SciPy`](https://www.scipy.org/) und [`Pandas`](https://pandas.pydata.org/) für die Programmiersprache [`Python`](https://www.python.org/) wurden direkt von modernen R-Konzepten inspiriert. Die meisten Prinzipien von Modern R lassen sich mit `Pandas` nahezu identisch umsetzen, wobei jeweils die Python-Syntax zur Anwendung kommt. Die Entscheidung ob R oder Python und Pandas genutzt wird oft auf Projektebene entschiedene. Viele Unternehmen arbeiten mit beiden Umgebungen parallel. 

Einige R-Konzepte finden sich in [`Mathlab`](https://ch.mathworks.com/de/products/matlab.html) wieder. Das gilt vor Allem für Vektoren und Matrix-Operationen. Mathlab ist jedoch nicht als statistische Programmierumgebung konzipiert, sondern als Umgebung für die nummerische Programmierung. Mathlab ist nicht als Open Source verfügbar. 

Die Programmiersprache [`Julia`](https://julialang.org/) ist eine kompilierte Programmiersprache für das statistische Rechnen. Die Sprache wurde speziell für sehr grosse Datenmengen entwickelt. Hierbei handelt es sich um eine sog. *Optimierungssprache*, die dann engesetzt wird, wenn die Leistung von R oder Python nicht mehr ausreicht.

