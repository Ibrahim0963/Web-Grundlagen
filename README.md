# Web-Grundlagen

# DNS
## Was ist DNS in der IT-Sicherheit?
DNS (Domain Name System) ermöglicht die Übersetzung von Domänennamen in IP-Adressen  In Bezug auf die IT-Sicherheit hat DNS einige potenzielle Sicherheitsrisiken, die es zu berücksichtigen gilt.

1.  **DNS-Spoofing**: Hierbei manipulieren Angreifer einen DNS-Server, um falsche IP-Adressen für bestimmte Domänen bereitzustellen. Dadurch kann es zu Phishing-Angriffen oder zur Weiterleitung auf gefälschte Websites kommen.
    
2.  **DNS-Cache-Poisoning**: Hierbei werden Daten in den DNS-Caches von DNS-Servern eingefügt, um falsche Informationen bereitzustellen. Dies kann dazu führen, dass Benutzer auf gefälschte Websites weitergeleitet werden, wenn sie nach bestimmten Domänen suchen.
    
3.  **DNS-Amplification-Angriff**: Hierbei nutzen Angreifer eine Schwäche im DNS-Protokoll aus, um einen verstärkten Datenfluss (Amplification) auszulösen, was den Angriff ermöglicht.
    
4.  **Man-in-the-Middle-Angriffe**: Hierbei können Angreifer zwischen Benutzer und DNS-Server eindringen und somit DNS-Anfragen abfangen und manipulieren.
    
5.  **Unbefugter Zugriff**: Hierbei können Angreifer auf DNS-Server und -Datenbanken zugreifen und Informationen stehlen oder manipulieren.

Um diese und andere Risiken zu minimieren, gibt es Technologien wie DNSSEC (Domain Name System Security Extensions), die digitale Signaturen verwenden, um die Integrität von DNS-Informationen zu schützen.

- What is the maximum length of a subdomain? 63
- What is the maximum length of a domain name? 253

## Was sind Record Types
Record Types (auch als DNS-Eintragsarten bezeichnet) sind die verschiedenen Arten von Datensätzen, die in einer DNS-Datenbank gespeichert werden können. Jeder Record Type enthält spezifische Informationen über eine Domäne oder eine Ressource im Internet.

Einige der häufigsten Record Types sind:

1.  A (Address) Record: Dies ist ein Eintrag, der einer Domäne eine IP-Adresse zuordnet.
    
2.  MX (Mail Exchange) Record: Dies ist ein Eintrag, der einer Domäne die Informationen zu einem oder mehreren Mail-Servern zuordnet.
    
3.  CNAME (Canonical Name) Record: Dies ist ein Eintrag, der einer Domäne einen alias zu einer anderen Domäne zuordnet.
    
4.  NS (Name Server) Record: Dies ist ein Eintrag, der einer Domäne den Namen eines oder mehrerer Nameserver zuordnet.
    
5.  TXT (Text) Record: Dies ist ein Eintrag, der frei formatierte Textinformationen über eine Domäne bereitstellt.
    
6.  SRV (Service) Record: Dies ist ein Eintrag, der spezifische Informationen über einen bestimmten Dienst innerhalb einer Domäne bereitstellt.

Es gibt noch weitere Record Types, die in DNS-Datenbanken gespeichert werden können, je nach Bedarf. Jeder Record Type hat seine eigene Funktion und Bedeutung und ist wichtig für die korrekte Übersetzung von Domänennamen in IP-Adressen und andere Netzwerkressourcen.

## Was passiert, wenn man eine DNS-Anfrage stellt?

Wenn Sie eine DNS-Anfrage stellen, passiert Folgendes:

1.  Der Client sendet eine Anfrage an den lokalen DNS-Resolver, der auf dem Gerät oder im Netzwerk konfiguriert ist.
    
2.  Der lokale DNS-Resolver überprüft seinen Cache, um zu sehen, ob er eine Antwort auf die Anfrage bereits hat. Wenn ja, gibt er diese Antwort an den Client zurück.
    
3.  Wenn der lokale DNS-Resolver keine Antwort im Cache hat, leitet er die Anfrage an den nächsten Nameserver weiter. Dies kann ein öffentlicher Nameserver sein, wie z.B. ein Nameserver von einem Internetdienstanbieter, oder ein Nameserver, der speziell für das Netzwerk konfiguriert wurde.
    
4.  Der empfangene Nameserver überprüft ebenfalls seinen Cache und gibt eine Antwort zurück, wenn er eine hat. Andernfalls leitet er die Anfrage an den nächsten Nameserver weiter.
    
5.  Dieser Prozess wiederholt sich, bis ein Nameserver gefunden wird, der die Informationen hat, die gesucht werden.
    
6.  Sobald eine Antwort gefunden wurde, wird diese zurück zum Client übertragen und von dort aus an alle zurückliegenden Nameserver und schließlich zurück zum lokalen DNS-Resolver.
    
7.  Der lokale DNS-Resolver speichert die Antwort im Cache, damit er bei zukünftigen Anfragen diese Informationen schneller bereitstellen kann.
    
8.  Schließlich gibt der lokale DNS-Resolver die Antwort an den Client zurück, der nun die IP-Adresse der gesuchten Domäne hat und eine Verbindung zu dieser Ressource aufbauen kann.


# HTTP
## 
