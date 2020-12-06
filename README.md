# <span style="text-decoration:underline;">Assignment  Integrated Testing</span>

Voor deze opdracht maak je opnieuw gebruik van de VM met daarin Jenkins uit de vorige lessen.

## Integratie testen (API)

Er werdt een simpele api gebouwd op [http://api.dubbadub.be/](http://api.dubbadub.be/) deze moet getest worden en deze tests willen we geïntegreerd zien in een Jenkins pipeline.

Om dit te doen gaan we gebruikmaken van Postman en zijn CLI variant Newman. Installeer deze alvorens te beginnen.

_De API is beveiligd met een simpele authentication key, deze key is 2TINDEVOPS (in hoofdletters). De key moet meegegeven worden in de header met als naam ‘key’ zoals ook terug te vinden in de Swagger documentatie op de API zelf._

*   Ga aan de slag met de documentatie van de API (deze is te vinden op de api zelf onder de subdir /api). Zorg dat jullie vertrouwd raken met de werking van de API en zijn werking.
*   Zorg ervoor dat ieder lid van jullie groep zichzelf ook manueel toevoegt in de API via postman.
*   Voorzie volgende stappen in een test collection (in Postman) en sla deze op onder de naam “api-testcollection-&lt;groepsnaam>”
    *   Geef een lijst weer van alle studenten in de API.
    *   Geef de specifieke details weer van een lid van jullie groep weer.
*   Sla de test collection op en exporteer deze in JSON format.

![alt_text](https://i.imgur.com/9leib3p.png "image_tooltip")
_Toon aan met screenshots & uitleg onder **punt (a)** in oplossing.md hoe je het handmatig testen van de API aangepakt hebt._

![alt_text](https://i.imgur.com/9leib3p.png "image_tooltip")
_Voeg de geëxporteerde JSON files van je postman test suite toe aan deze repository._


## End to end testen

Binnen onze calculator app willen we ook graag enkele automatische e2e testen voorzien. Je gebruikt hiervoor de gedeployde applicatie uit de vorige opdracht & de **selenium IDE** die we gezien hebben tijdens de les. Gebruik de selenium IDE om 2 testen te schrijven met onderstaande naam:



*   AppHasButton: Deze test check of er effectief een &lt;button> element op de webpagina aanwezig is. Indien niet moet deze test falen.
*   AppCanAdd: Deze applicatie test de functionaliteit van de Applicatie, telt de getallen 5 en 4 op en controleert dan of de uitkomst correct op de pagina staat. Indien niet, zal deze test falen.

![alt_text](https://i.imgur.com/9leib3p.png "image_tooltip")
_Toon met screenshots de verschillende stappen in je selenium IDE aan van de verschillende testen onder **punt (b)**._

![alt_text](https://i.imgur.com/9leib3p.png "image_tooltip")
_Sla het project op en voeg de .side file(s) toe aan deze repository._

## Pipeline

Graag zouden we de testen ook willen zien runnen in een pipeline. Bouw een nieuwe pipeline die volgende stages heeft:



*   “Fetch code”: Deze stapt haalt de  **.side files & .json files** uit de repository van de opdracht.
*   “Run e2e test”: Deze stap gebruikt de [selenium-side-runner](https://www.selenium.dev/selenium-ide/docs/en/introduction/command-line-runner) om de .side testen te runnen in de pipeline. Zorg voor een gegenereerd rapport (JUNIT formaat).

    _Tip: Denk eraan dat je zowel [Chrome](https://linuxize.com/post/how-to-install-google-chrome-web-browser-on-debian-9/#1-download-google-chrome) als [Chromedriver](https://chromedriver.chromium.org/) nodig hebt zoals gezien in de slides. Deze zal je handmatig eerst moeten installeren. De selenium-side-runner is een nodeJS package. Deze kan je installeren a.d.h.v. de global tool configuration(**Gebruik hiervoor NodeJS versie 10.19**) in Jenkins (zie slides). _

*   “Run integratie test”: Deze stap voert de postman testen uit en genereert ook een rapport (JUNIT formaat). Gebruik hiervoor de [newman](https://www.npmjs.com/package/newman) CLI omgeving.

    _Tip: Je kan newman ook opnemen in je global configuration tool op dezelfde manier als je dit gedaan hebt voor selenium-side-runner._

*   “Archive artifact”: Deze stap maakt een artifact van alle gemaakte rapporten uit de vorige stappen.

![alt_text](https://i.imgur.com/9leib3p.png "image_tooltip")
_Sla het pipeline script op in de file “automatedtesting.pipeline” en voeg deze toe aan de repository._
