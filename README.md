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

1.  **A (Address) Record**: Dies ist ein Eintrag, der einer Domäne eine IP-Adresse zuordnet.
    
2.  **MX (Mail Exchange) Record**: Dies ist ein Eintrag, der einer Domäne die Informationen zu einem oder mehreren Mail-Servern zuordnet.
    
3.  **CNAME (Canonical Name) Record**: Dies ist ein Eintrag, der einer Domäne einen alias zu einer anderen Domäne zuordnet.
    
4.  **NS (Name Server) Record**: Dies ist ein Eintrag, der einer Domäne den Namen eines oder mehrerer Nameserver zuordnet.
    
5.  **TXT (Text) Record**: Dies ist ein Eintrag, der frei formatierte Textinformationen über eine Domäne bereitstellt.
    
6.  **SRV (Service) Record**: Dies ist ein Eintrag, der spezifische Informationen über einen bestimmten Dienst innerhalb einer Domäne bereitstellt.

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
## Was ist HTTP(S)?
HTTP (Hypertext Transfer Protocol) ist ein Übertragungsprotokoll für das World Wide Web, das es ermöglicht, Daten, wie Webseiten und andere digitale Ressourcen, zwischen einem Client und einem Server auszutauschen. Es ist das Standardprotokoll für den Austausch von Daten im Web und wird von nahezu allen Websites und Web-Anwendungen verwendet.

HTTPS (Hypertext Transfer Protocol Secure) ist eine gesicherte Version von HTTP, bei der die Datenübertragung zwischen Client und Server verschlüsselt ist. Dies verhindert, dass Dritte die Übertragung mitlesen oder manipulieren können. HTTPS wird häufig auf Websites verwendet, auf denen sicherheitsrelevante Informationen, wie z.B. Passwörter oder Kreditkarteninformationen, übertragen werden.

In beiden Fällen (HTTP und HTTPS) arbeitet das Protokoll auf Schicht 7 des OSI-Modells (Anwendungsschicht). Es definiert die Regeln für den Austausch von Daten zwischen Client und Server, einschließlich der Art und Weise, wie Daten angefordert und übertragen werden, sowie der Formatierung von Antworten.

## HTTP(s) Anfragen und Antworten
Eine HTTP- oder HTTPS-Anfrage besteht aus einem Anfragezeilen (Request Line), einem Header (Request Header) und optionalem Nachrichteninhalt (Request Body). Hier ist ein Beispiel für eine HTTP-GET-Anfrage:
```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:91.0) Gecko/20100101 Firefox/91.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```

Die Anfragezeile besteht aus drei Teilen:
-   Das HTTP-Verb (hier: `GET`), das angibt, welche Art von Anfrage gestellt wird.
-   Der Pfad (hier: `/index.html`), der angibt, welche Ressource angefordert wird.
-   Die HTTP-Version (hier: `HTTP/1.1`), die angibt, welche Version des HTTP-Protokolls verwendet wird.

Der Header enthält weitere Informationen über die Anfrage, wie den Host-Namen (`Host`), den Benutzer-Agenten (`User-Agent`), die akzeptierten Inhaltsformate (`Accept`), die Spracheinstellungen (`Accept-Language`) und weitere.

Die Antwort auf eine HTTP- oder HTTPS-Anfrage besteht aus einer Statuszeile (Status Line), einem Header (Response Header) und dem Antwortinhalt (Response Body). Hier ist ein Beispiel für eine HTTP-Antwort:
```
HTTP/1.1 200 OK
Date: Mon, 14 Feb 2023 13:57:51 GMT
Server: Apache/2.4.41 (Ubuntu)
Last-Modified: Mon, 07 Feb 2023 10:06:51 GMT
ETag: "67a-5a5f6f40f5cc0"
Accept-Ranges: bytes
Content-Length: 1638
Content-Type: text/html

<!DOCTYPE html>
<html>
...
</html>
```
Die Statuszeile besteht aus drei Teilen:
-   Die HTTP-Version (hier: `HTTP/1.1`), die angibt, welche Version des HTTP-Protokolls verwendet wird.
-   Der Statuscode (hier: `200 OK`), der angibt, ob die Anfrage erfolgreich war oder nicht.
-   Der Statusbeschreibung (hier: `OK`), die weitere Informationen über den Statuscode bereitstellt.

Der Header enthält Informationen über die Antwort, wie das Datum und die Uhrzeit (`Date`), den Server, der die Antwort bereitstellt (`Server`), das Datum der letzten Änderung (`Last-Modified`), einen eindeutigen Identifikator für die Ressource (`ETag`), die Größe des Antwortinhalts (`Content-Length`) und das Format des Antwortinhalts (`Content-Type`).

Der Antwortinhalt enthält die tatsächlichen Daten, die angefordert wurden, z.B. eine HTML-Seite, ein Bild oder eine andere Art von Ressource.

## HTTP-Methoden ?
HTTP-Methoden (auch bekannt als HTTP-Verben) sind Anweisungen, die an einen Server gesendet werden, um eine bestimmte Aktion auszuführen. Hier sind einige der häufigsten HTTP-Methoden:

-   `GET`: Die GET-Methode wird verwendet, um Daten von einem Server abzurufen. Dies ist die häufigste Methode und wird verwendet, um Webseiten, Bilder und andere Ressourcen anzufordern.
    
-   `POST`: Die POST-Methode wird verwendet, um Daten an einen Server zu senden. Diese Methode wird häufig verwendet, um Formulardaten an einen Server zu senden, z.B. bei der Anmeldung auf einer Webseite.
    
-   `PUT`: Die PUT-Methode wird verwendet, um eine Ressource auf einem Server zu aktualisieren oder zu ersetzen.
    
-   `DELETE`: Die DELETE-Methode wird verwendet, um eine Ressource auf einem Server zu löschen.
    
-   `HEAD`: Die HEAD-Methode ist ähnlich wie die GET-Methode, aber sie liefert nur den Header der Antwort zurück, ohne den Antwortinhalt.
    
-   `OPTIONS`: Die OPTIONS-Methode wird verwendet, um die verfügbaren HTTP-Methoden für eine bestimmte Ressource zu ermitteln.

Es gibt auch andere weniger häufig verwendete HTTP-Methoden, wie z.B. `CONNECT`, `TRACE` und `PATCH`. Jeder HTTP-Server kann jedoch andere Methoden unterstützen oder beschränken.

## HTTP-Statuscodes ?
HTTP-Statuscodes sind numerische Codes, die von einem HTTP-Server an einen Client gesendet werden, um anzugeben, ob eine Anfrage erfolgreich war oder nicht und welche Art von Antwort bereitgestellt wird. 

- **100-199 - Informationsantwort/Information Response**: Diese werden gesendet, um dem Kunden mitzuteilen, dass der erste Teil seiner Anfrage akzeptiert wurde und er mit dem Senden des Rests seiner Anfrage fortfahren sollte. Diese Codes sind nicht mehr sehr verbreitet.

- **200-299 - Erfolg/Success**: Dieser Bereich von Statuscodes wird verwendet, um dem Client mitzuteilen, dass seine Anfrage erfolgreich war.

- **300-399 - Umleitung/Redirection**: Diese werden verwendet, um die Anfrage des Clients an eine andere Ressource umzuleiten. Dies kann entweder auf eine andere Webseite oder auf eine ganz andere Website erfolgen.

- **400-499 - Clientfehler/Client Errors**: Wird verwendet, um den Client darüber zu informieren, dass bei seiner Anfrage ein Fehler aufgetreten ist.

- **500-599 - Serverfehler/Server Errors**:  Dies ist für Fehler reserviert, die auf der Serverseite auftreten und normalerweise auf ein ziemlich großes Problem mit dem Server hinweisen, der die Anfrage verarbeitet.


Hier sind einige der häufigsten HTTP-Statuscodes:

-  `200 OK`: Die Anfrage war erfolgreich und die gewünschten Daten werden im Antwortinhalt bereitgestellt.
    
-  `201 Created (**Erstellt**)`: Die Anfrage war erfolgreich und eine neue Ressource wurde auf dem Server erstellt.
    
-  `204 No Content`: Die Anfrage war erfolgreich, aber es wird kein Antwortinhalt bereitgestellt.

- `301 Permanent Redirect (**Permanente Weiterleitung**)`: Dies leitet den Browser des Clients auf eine neue Webseite um oder teilt Suchmaschinen mit, dass die Seite an eine andere Stelle verschoben wurde und stattdessen dort suchen soll.
  
- `302 Temporary Redirect (**Temporäre Umleitung**)`: Ähnlich wie die obige permanente Weiterleitung, aber wie der Name schon sagt, ist dies nur eine vorübergehende Änderung und kann sich in naher Zukunft wieder ändern.

-  `400 Bad Request (**Ungültige Anfrage**)`: Die Anfrage konnte aufgrund eines Fehlers in der Syntax oder den angeforderten Daten nicht verarbeitet werden.
    
- `401 Unauthorized (**Nicht autorisiert**)`: Der Client konnte nicht authentifiziert werden und hat keinen Zugriff auf die gewünschte Ressource.
    
-  `403 Forbidden (**Verboten**)`: Der Client hat keine Berechtigung, auf die gewünschte Ressource zuzugreifen.
    
-  `404 Not Found (**Seite nicht gefunden**)`: Die gewünschte Ressource konnte auf dem Server nicht gefunden werden.

- `405 Method Not Allowed (**Methode nicht erlaubt**)`: Die Ressource lässt diese Methodenanforderung nicht zu, Sie senden beispielsweise eine GET-Anforderung an die Ressource /create-account, obwohl sie stattdessen eine POST-Anforderung erwartet hat.
    
-  `500 Internal Server Error (**Interner Dienstfehler**)`: Ein Fehler ist auf dem Server aufgetreten und die Anfrage konnte nicht verarbeitet werden.

- `503 Service Unavailable (**Dienst nicht verfügbar**)`: Dieser Server kann Ihre Anfrage nicht verarbeiten, da er entweder überlastet oder wegen Wartungsarbeiten ausgefallen ist.

Es gibt viele weitere HTTP-Statuscodes, die spezifischere Anwendungen und Fehler beschreiben können. Ein Client kann diese Codes verwenden, um die Antwort einer Anfrage zu interpretieren und entsprechend darauf zu reagieren.

## HTTP(s) Headers?
HTTP-Header sind Teil einer HTTP-Anfrage oder -Antwort und enthalten zusätzliche Informationen über die Anfrage oder Antwort. Ein Header kann Informationen wie die Art des Inhalts, die Sprache, die Länge des Inhalts, die Autorisierungsdetails und viele andere Informationen enthalten.

Einige häufig verwendete HTTP-Header sind:
- `Host:` Einige Webserver hosten mehrere Websites. Wenn Sie also die Host-Header angeben, können Sie angeben, welche Sie benötigen. Andernfalls erhalten Sie nur die Standard-Website für den Server.

-  `Accept`: Gibt an, welche Arten von Inhalten vom Client akzeptiert werden.
    
-  `Content-Type`: Gibt an, welcher MIME-Typ für den Antwortinhalt verwendet wird.
    
-  `Content-Length`: Gibt die Länge des Antwortinhalts in Bytes an.
    
-  `Authorization`: Enthält Informationen zur Authentifizierung des Clients.
    
-  `User-Agent`: Gibt Informationen über den Client und den verwendeten Browser an.
    
-  `Referer`: Gibt die URL der Seite an, von der die Anfrage stammt.
  
-  `Accept-Encoding`: Gibt an, welche Arten von Inhaltskodierungen vom Client akzeptiert werden.
    
-  `Accept-Language`: Gibt an, welche Sprachen vom Client bevorzugt werden.
    
-  `Cache-Control`: Steuert, wie der Antwortinhalt vom Browser gecacht wird.
    
-  `Connection`: Steuert, ob eine persistente Verbindung verwendet wird oder nicht.
    
-  `Cookie`: Enthält einen oder mehrere Cookies, die vom Client an den Server gesendet werden.
    
-  `Host`: Gibt die URL des Servers an, auf den die Anfrage gerichtet ist.
    
-  `If-Modified-Since`: Gibt an, dass die Antwort nur zurückgegeben werden soll, wenn die angeforderte Ressource seit dem angegebenen Datum geändert wurde.
    
-  `Referer`: Gibt die URL der Seite an, von der die Anfrage stammt.
    
-  `Server`: Gibt Informationen über den Server an, der die Antwort gesendet hat.

-  `Set-Cookie`: Setzt einen oder mehrere Cookies auf dem Client.

## Cookie?
Cookies sind kleine Textdateien, die von Webservern an den Browser des Benutzers gesendet werden. Sie werden auf dem Computer des Benutzers gespeichert und können bei zukünftigen Anfragen an den gleichen Server zurückgesendet werden.

Cookies werden häufig verwendet, um Benutzer-Sitzungen und Benutzerpräferenzen zu verfolgen und zu speichern, wie beispielsweise den Inhalt des Warenkorbs eines Online-Shops oder den Standort des Benutzers. Ein Webserver kann auch Informationen in einem Cookie speichern, die später für die Authentifizierung oder Autorisierung des Benutzers verwendet werden können.

# Andere Web-Komponente?

**Load Balancer**: Ein Load Balancer ist ein Gerät oder eine Software, die Netzwerkverkehr auf mehrere Server aufteilt, um die Last auf mehrere Systeme zu verteilen und dadurch die Verfügbarkeit und Skalierbarkeit zu verbessern.

**Content Delivery Network (CDN)**: Ein CDN ist ein weit verbreitetes Netzwerk aus Servern, die Inhalte wie Bilder, Videos und andere statische Daten für Webseiten bereitstellen. Ein CDN repliziert Inhalte auf mehreren Servern in verschiedenen geografischen Standorten, so dass Benutzer schnelleren Zugriff auf diese Inhalte haben.

**Datenbank**: Eine Datenbank ist ein System zur Speicherung, Verwaltung und Abfrage von Daten. Webseiten verwenden oft Datenbanken, um dynamische Inhalte wie Benutzerdaten, Produktdaten und mehr zu speichern und abzurufen.

**Web Application Firewall (WAF)**: Eine Web Application Firewall ist eine Firewall-Lösung, die speziell für Web-Anwendungen entwickelt wurde. Sie überwacht den Netzwerkverkehr nach Bedrohungen wie SQL-Injection-Angriffen, Cross-Site-Scripting (XSS) und anderen Arten von Angriffen auf Web-Anwendungen.

**Cache-Systeme**: Diese Systeme speichern oft verwendete Daten in einem schnell zugreifbaren Cache, um die Leistung und die Reaktionszeit zu verbessern.

**Proxies**: Ein Proxy ist ein Server, der Anfragen für andere Server aufnimmt und bearbeitet. Proxies können verwendet werden, um die Sicherheit zu erhöhen, den Datenverkehr zu beschleunigen oder andere Funktionen bereitzustellen.

**Application Server**: Ein Application Server ist ein Server, der speziell für die Ausführung von Anwendungen entwickelt wurde.

**Object Storage**: Object Storage ist ein spezialisiertes System zur Speicherung unstrukturierter Daten wie Bilder, Videos und andere große Datenmengen.

**Virtuelle Hosts**: Virtuelle Hosts sind ein Konzept in der Webserver-Administration, bei dem ein einzelner Webserver mehrere unabhängige Websites oder Web-Anwendungen ausführt, indem er Anfragen für unterschiedliche Domains oder IP-Adressen unterschiedlich verarbeitet.

## Funktionsweise von Webservern?
Webserver sind Anwendungen, die Anfragen von Clients (z.B. Webbrowser) empfangen und darauf reagieren, indem sie geforderten Inhalte bereitstellen. Hier ist ein kurzer Überblick über den Ablauf:

1.  **Client sendet Anfrage**: Ein Client, wie ein Webbrowser, sendet eine HTTP-Anfrage an den Webserver, um eine bestimmte Ressource zu erhalten, z.B. eine Webseite oder ein Bild.
    
2.  **Webserver empfängt Anfrage**: Der Webserver empfängt die Anfrage und verarbeitet sie.
    
3.  **Verarbeitung der Anfrage**: Der Webserver prüft die Anfrage, um sicherzustellen, dass sie gültig ist. Dann ruft er die angeforderte Ressource aus dem Dateisystem oder einer Datenbank ab.
    
4.  **Erstellung der Antwort**: Der Webserver erstellt eine HTTP-Antwort auf die Anfrage, die die angeforderte Ressource enthält. Die Antwort enthält auch Informationen im Header, wie z.B. den HTTP-Statuscode und weitere Metadaten.
    
5.  **Senden der Antwort**: Der Webserver sendet die Antwort an den Client zurück.
    
6.  **Client empfängt Antwort**: Der Client empfängt die Antwort vom Webserver und verarbeitet sie, indem er die Ressource darstellt oder weiterverarbeitet.

Dies ist ein einfacher Überblick über den Ablauf von Anfragen und Antworten zwischen einem Client und einem Webserver.
