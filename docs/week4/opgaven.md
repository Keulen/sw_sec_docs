# Opgave week 4: threat modelling van een "slimme" thermostaat

We gaan deze week bezig met het bepalen van risico’s van een geheel systeem in een voorbeeldcasus aan de hand van de STRIDE-methode. 

## Casus

Een bedrijf heeft contact met je opgenomen om een systeem te ontwerpen voor een nieuwe slimme thermostaat. De thermostaat zal gebruikers in staat stellen om de temperatuur van hun huis op afstand te regelen met behulp van een mobiele app of webinterface. Het bedrijf heeft je de volgende informatie verstrekt ( vul waar nodig aan op een logische manier).

De thermostaat wordt geïnstalleerd in het huis van een gebruiker en wordt aangesloten op hun AIRCO-systeem. Het wordt van stroom voorzien door een standaard stopcontact en maakt verbinding met internet via Wi-Fi. De thermostaat heeft een temperatuursensor en een touchscreen-interface die de huidige temperatuur weergeeft en gebruikers in staat stelt de gewenste temperatuur in te stellen.

De thermostaat heeft ook een ingebouwde microfoon en luidspreker waarmee gebruikers het kunnen bedienen met behulp van spraakopdrachten. Het bedrijf van plan om natuurlijke taalverwerkingsalgoritmen te gebruiken om de spraakopdrachten van de gebruiker te begrijpen en hierop gepast te reageren.

De mobiele app en webinterface zullen gebruikers in staat stellen om de thermostaat op afstand te bedienen. Ze kunnen de huidige temperatuur bekijken en de gewenste temperatuur aanpassen met behulp van het touchscreen of spraakopdrachten. Ze kunnen ook schema's instellen voor wanneer de temperatuur moet veranderen, zoals wanneer ze aan het werk zijn of slapen.

Alle gebruikersgegevens worden opgeslagen in een cloud gebaseerde database. De database bevat informatie over de thermostaatinstellingen en gebruikspatronen van elke gebruiker. De database is alleen toegankelijk voor geautoriseerde gebruikers. De webinterface maakt gebruik van HTTP richting de gebruikers browser.

Om de beveiliging van het systeem te waarborgen, wordt de thermostaat ontworpen met een verzegelde behuizing die ongeautoriseerde toegang voorkomt. Op de behuizing zit een sticker met een nummer (25 random getallen) waarmee je een account kunt maken op de webinterface. De behuizing kan geopend worden met een sleutel voor onderhoud, maar hierdoor verbreekt uiteraard het zegel. Tijdens onderhoud kunnen er via USB commando’s verstuurd worden voor bijvoorbeeld updates.

De microfoon en luidspreker zijn standaard ingeschakeld en gebruikers moeten deze handmatig uitschakelen via de app of webinterface.

Het bedrijf is van plan de thermostaat aan te bieden als een abonnementsservice, waarbij gebruikers een maandelijks bedrag betalen om het apparaat te gebruiken en toegang te krijgen tot de app en webinterface. Het bedrijf biedt ook klantenondersteuning en onderhoudsdiensten aan als onderdeel van het abonnement. De klantgegevens worden door de afdeling Facturatie gebruikt om de kosten door te berekenen aan de klant. Deze afdeling maakt via een intern netwerk verbinding met de database over TCP.

## Opdrachten

1.\ Teken het Data Flow Diagram (DFD) van de beschreven casus. Het diagram moet het systeem op een niveau laten zien dat geschikt is voor een risicoanalyse. Zorg dat de DFD overzichtelijk en navolgbaar neergezet wordt. Dit kan op papier, maar mag uiteraard ook met een softwaretool (zie het lijstje op Blackboard).

2.\ Pas threat modelling toe op je DFD. Geef in je DFD aan waar welke risico’s zitten (interfaces: plekken waar data over een trust boundary gaat). Gebruik hiervoor de STRIDE-methodiek. Denk hierbij aan de afkorting:

* <b>S</b>poofing: je voordoen als iemand anders of een ander system, bijv. doordat er geen wachtwoord eisen zijn
* <b>T</b>ampering: aanpassen van data op een systeem of netwerk, bijv. XSS
* <b>R</b>epudiation: ontkennen van iets dat je gedaan hebt, bijv. doordat er geen logging is
* <b>I</b>nformation Disclosure: ongeautoriseerd toegang verschaffen tot data, bijv. mogelijk gemaakt door plaintext versturen van data
* <b>D</b>enial of Service: werking van services verhinderen, bijv. DDOS-aanval
* <b>E</b>levation of Privilege: toegang krijgen tot rechten die je niet had, bijv. door gebruik te maken van kwetsbaarheden in slechte/oude software

3.\ 

A. Maak een opsomming van de interfaces waarvan jij denk dat ze getest moeten worden op security-aspecten.

B. Prioriteer deze lijst en onderbouw je keuzes daarin. 

C. Beschrijf voor de top 3 van kwetsbare interfaces welke maatregelen er genomen kunnen worden (geef meerdere opties; denk ook aan tijd-/geld-investering van het bedrijf!). Denk hierbij aan de afkorting META:

* <b>M</b>itigate: een tegenmaatregel implementeren
* <b>E</b>liminate: de interface geheel verwijderen
* <b>T</b>ransfer: de verantwoordelijkheid overdragen aan een andere partij
* <b>A</b>ccept: het risico voor lief nemen en niets doen