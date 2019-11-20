Eine kurze Geschichte von SPDY und HTTP / 2

Das heißt, es sei denn, Sie implementieren einen Webserver (oder einen benutzerdefinierten Client) von
Wenn Sie mit rohen TCP-Sockets arbeiten, werden Sie keinen Unterschied bemerken:
Low-Level-Framing wird von Client und Server in Ihrem Namen durchgeführt. Das einzige
beobachtbaren Unterschiede werden die Leistung und Verfügbarkeit neuer verbessert
Funktionen wie Anforderungspriorisierung, Flusskontrolle und Server-Push.

SPDY war ein experimentelles Protokoll, das bei Google entwickelt und in angekündigt wurde
mitte 2009, deren primäres ziel es war, die ladelatenz von webseiten zu reduzieren
indem einige der bekannten Leistungseinschränkungen von HTTP / 1.1 behoben werden.
Im Einzelnen wurden die skizzierten Projektziele wie folgt festgelegt:

Hinweis: Um eine PLT-Verbesserung von 50% zu erzielen, hat SPDY eine effizientere Verwendung angestrebt
der zugrunde liegenden TCP-Verbindung durch Einführung einer neuen Binär-Framing-Schicht
Aktivieren Sie das Anforderungs- und Antwort-Multiplexing, die Priorisierung und den Header
Kompression; Siehe Latenz als Leistungsengpass {: .external}.

Nicht lange nach der ersten Ankündigung, Mike Belshe und Roberto Peon, beide
Softwareingenieure bei Google teilten ihre ersten Ergebnisse, Dokumentationen und
Quellcode für die experimentelle Implementierung des neuen SPDY-Protokolls:

Schneller Vorlauf bis 2012 und das neue experimentelle Protokoll wurde in Chrome unterstützt.
Firefox und Opera sowie eine schnell wachsende Anzahl von Websites, die beide groß sind (z. B.
Google, Twitter, Facebook) und kleine Unternehmen haben SPDY in ihrem Netzwerk implementiert
Infrastruktur. Tatsächlich war SPDY auf dem Weg, ein De-facto-Standard zu werden
durch wachsende Akzeptanz in der Industrie.

Als die HTTP-Arbeitsgruppe (HTTP-WG) diesen Trend beobachtete, startete sie eine neue
sich bemühen, die Lehren aus SPDY zu ziehen, sie auszubauen und zu verbessern, und
Liefern Sie einen offiziellen "HTTP / 2" -Standard. Eine neue Charta wurde ausgearbeitet, ein offener Aufruf
Für HTTP / 2 wurden Vorschläge gemacht, und nach vielen Diskussionen innerhalb der Arbeit
Gruppe wurde die SPDY-Spezifikation als Ausgangspunkt für das neue HTTP / 2 übernommen
Protokoll.

Anfang 2015 überprüfte und genehmigte die IESG den neuen HTTP / 2-Standard für
Veröffentlichung. Kurz darauf gab das Google Chrome-Team seinen Zeitplan bekannt
SPDY- und NPN-Erweiterung für TLS abzulehnen.
