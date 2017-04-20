# Spring-Buch-Beispiel: Lies Mich

## Einf�hrung

Willkommen zu den Beispielanwendungen aus dem Spring-3-Buch!

Die Beispiele sind in verschiedenen Unterverzeichnissen
organisiert. Dadurch k�nnen Sie die Beispiel jeweils individuell
ausf�hren und mit ihnen experimentieren.

Viel Spa� dabei!

## Zwei Worte zu Maven

Die Beispiele basieren auf dem Build-Tool Maven. Das hat
verschiedene Vorteile:

* Es m�ssen keine abh�ngigen Bibliotheken installiert
werden

* Es ist auch kein Application- oder Web-Server zu installieren,
	auch das wird von Maven erledigt.

Zur Installation von Maven m�ssen Sie folgendes

* Installieren Sie maven 2.2.1 von <http://maven.apache.org/download.html>

* F�gen Sie das maven bin Verzeichnis in den Pfad ein.  Kontrolle: In
	einer Eingabeaufforderung m�ssen Sie nun `mvn` ausf�hren
	k�nnen.


## Maven-Projekte
Die Maven-Projekte haben ein festes Layout:

* In `src/test` liegt der Anteil des
Projekts, der f�r die Tests notwendig ist.

* In `src/main` liegt der Anteil des
	Projekts, der f�r die Funktionalit�ten ben�tigt wird.

Diese beiden Verzeichnisse haben identische Unterverzeichnisse:

* In `java` liegt der Java-Code.

* Und in `resources` die �brigen Ressourcen.

Meinstens haben die Projekte Tests, die die Benutzung der
Spring-Features verdeutlicht.

Allgemeine Einstellungen sind in dem `pom.xml` in diesem
Verzeichnis.

Sie k�nnen alle Projekt mit `mvn install` in dem
Hauptverzeichnis, in dem auch diese Datei liegt, compilieren, testen
und in Ihr lokales Maven-Repository kopieren. Dies geht auch f�r
einzelne Projekte, wenn Sie mvn install in dem Unterverzeichnis
ausf�hren.

Web-Anwendungen kann man mit `mvn jetty:run` in dem jeweiligen
Verzeichnis starten. Einige Projekt haben Tests in einem Package
remotetest. Diese Test setzen voraus, dass der Server l�uft und
werden bei einem mvn install nicht ausgef�hrt. Sie m�ssen
also nach dem Start des Servers manuell gestartet

##  Eclipse-Projekte erzeugen

Ich empfehle die Nutzung der Spring Tool Suite, da diese
Eclipse-Distribution schon einige wichtige Plug Ins integriert
hat. Sie k�nnen STS unter <https://spring.io/tools>
runterladen. Alternativ kann man ein Eclipse mit mindestens der
m2eclipse-Maven-Integration nutzen.

Legen Sie einen neuen Eclipse-Workspace an. Dazu kann man *File ->
Switch Workspace...* verwenden und in dem Dialog dann ein neues
Verzeichnis eingeben.

Anschlie�end m�ssen Sie im File-Men� den Eintrag
*Import*. In dem erscheinenden Dialog w�hlen Sie unter *General* den Punkt
*Maven Projects*. Dann dr�cken Sie den *Next*-Button.
Als *Root*-Verzeichnis w�hlen Sie das Verzeichnis mit den
ausgepackten Beispielen. Dann dr�cken Sie den *Finish*-Button. Der
Workspace baut sich dann auf.

Web-Anwendungen kann man dann in Eclipse einfach mit einem rechten
Mausklick auf das Projekt starten. Dort w�hlt man *Run As* und dann *Run
On Server*. Man muss dann nur noch einen Server ausw�hlen, auf dem die
Anwendungen laufen soll.

## [beispielanwendung](beispielanwendung)

Dieses Projekt enth�lt die Basis-Funktionalit�ten der
Beispielanwendung, also den Gesch�ftslogik-Kern. Dazu z�hlt
auch die Persistenz. Das Projekt enth�lt Tests f�r die
Funktionalit�ten. Dadurch kann man sehen, dass die Anwendung
tats�chlich funktioniert. Die Tests werden w�hrend der
Installation ausgef�hrt. Durch die Installation steht der
Gesch�ftslogik-Kern den andern Beispielen zur Verf�gung.

## [beispielanwendung-annotations](beispielanwendung-annotations)

Im Prinzip wie die Beispielanwendung - aber mit Annotationen statt
XML-Konfiguration. 

## [beispielanwendung-jsr330](beispielanwendung-jsr330)

Im Prinzip wie die Beispielanwendung - aber mit JSR330-Annotationen statt
XML-Konfiguration.

## [beispielanwendung3](beispielanwendung3)

Eine vollst�ndige Spring-3-Anwendung zum Beispiel mit REST.

## [el](el)

Einige Beispiele f�r die Spring Expression Language (SpEL).

## [web](web)

Das Web-Projekt ist ein Web-Frontend auf Basis von Spring MVC.  Damit
dieses Projekt funktioniert, muss vorher die Beispielanwendung
installiert worden sein. Es kann dann mit jetty:run gestartet
werden. Die URL ist <http://localhost:8080/web>.

## [jsf](jsf)

Das JSF-Projekt ist ein Web-Frontend auf Basis von JSF mit Integration
in Spring. Damit dieses Projekt funktioniert, muss vorher die
Beispielanwendung installiert worden sein. Es kann dann mit `mvn
jetty:run` gestartet werden.

Die URL ist <http://localhost:8080/jsf>.

## [springsecurity](springsecurity)

Das Spring-Security-Beispiel setzt auf dem Web-Beispiel auf.  Das
Spring-Security-Projekt l�dt das Web-Projekt und erg�nzt es um den
Sicherheits-Aspekt mit Hilfe von Spring Security.

Man kann es dann mit `mvn jetty:run` starten.

Die Anwendung steht dann unter der URL <http://localhost:8080/acegi/>
zur Verf�gung.

Leider unterst�tzt die Maven-Eclipse-Integration die
Erg�nzung von Web-Anwendungen nicht, man kann die Anwendung in
Eclipse also nicht starten.

## [webflow](webflow)

Dieses Projekt benutzt Spring Web Flow zum Aufbaue eines etwas
komplexeren Bestell-Prozesses. Man kann es mit `mvn jetty:run` starten.

Die Anwendung steht dann unter der URL <http://localhost:8080/webflow/>
zur Verf�gung.

## [remoting](remoting)

Das Remoting-Projekt zeigt die Remoting-Technologien aus Spring.
Dabei wird Hession, Burlap und der HttpInvoker von Spring
gezeigt. Dazu muss die Beispielanwendung im Maven-Repository
installiert sein. Dann muss man den Web-Server mit `mvn jetty:run`
starten. Dann kann man auch die Tests aus dem Package remotetest
ausf�hren.

## [webservice](webservice)

Dieses Projekt nutzt Spring Web Services f�r die Implementierung eines
Web Service. Man kann den Web Service mit `mvn jetty:run`
starten. Dann kann man auch die Tests aus dem Package remotetest
ausf�hren.


## [webservice-annnotations](webservice-annotations)

Wie webservice - allerdings werden hier Annotationen f�r die
Implementierung der Web Services genutzt.

## [enterprise](Enterprise)

Dieses Projekt zeigt die Verwendung der Enterprise-Features wie JMS,
Timer und JMX. JMS und Timer werden durch `mvn test` laufen
gelassen. Bei JMX muss man mit `mvn exec:exec` die Anwendung
starten. Anschlie�end kann man die `jconsole` die
JDK-Management-Console starten und sich die JMX-Beans anschauen. Sie
�ndern auch regelm��ig ihre Werte.

## [aop2](aop2)

In diesem Projekt werden die AOP-Features von Spring 2 gezeigt.  Dazu
sind entsprechende Tests vorhanden, die man mit `mvn test`
ausprobieren kann.

## [beispiele](beispiele)

In diesem Projekt werden verschiedene kleiner Beispiele mit Spring
gezeigt. Dazu sind entsprechende Tests vorhanden, die man mit `mvn
test` ausprobieren kann.

## [aop-benchmark](aop-benchmark)

Dieses Projekt enth�lt den Code f�r den AOP-Benchmark. Er wird mit
	`mvn test` gestartet.

## [feedback](Feedback)
Feedback bitte an [Eberhard Wolff](mailto:eberhard.wolff@gmail.com).
