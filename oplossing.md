Vul onderstaande aan met de antwoorden op de vragen uit de readme.md file. Wil je de oplossingen file van opmaak voorzien? Gebruik dan [deze link](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) om informatie te krijgen over
opmaak met Markdown.

a)
Ik ben eerst gaan kijken in http://api.dubbadub.be/ en hierin het token '2TINDEVOPS' ingegeven. Als ik dan de verschillende GET's en POST's uitprobeer door op 'Try it out' te klikken en iets in te geven kan ik zien wat er van mij verwacht wordt. In de afbeelding hoeronder bijvoorbeeld zie ik dat ik bij de GET om de lijst van alle studenten te krijgen de URL die gerequest wordt http://api.dubbadub.be/api/students is. Door dit dan door te geven in een Postman GET-request en niet te vergeten onder 'Headers' als 'KEY' 'key' te zetten en als 'VALUE' '2TINDEVOPS', kan je testen of de API doet wat hij hoort te doen via de Response op Postman.

![alt_text](https://i.imgur.com/7gn6KB4.png)
![alt_text](https://i.imgur.com/MnYSb0V.png)

Op dezelfde manier heb ik dit gedaan om de specifieke info te krijgen van een student volgens zijn 'id'.

![alt_text](https://i.imgur.com/8bsPUBB.png)
![alt_text](https://i.imgur.com/9Wpn06o.png)

b)
Om te beginnen heb ik selenium geopend en ingesteld dat hij gaat testen op localhost.
Vervolgens heb ik op 'record' geduwd en op de knop geduwd, selenium hield dit bij en zo heb ik de test 'AppCanAdd' af.
![alt_text](https://i.imgur.com/MYZd6XA.png)

Voor de 2de test heb ik weer op record geduwd, en vervolgend 5 ingegeven in de eerste balk, 4 in de 2de balk en op de knop add geduwd.
Hierna heb ik het recorden gestopt en op de knop 'select target in page' geduwd, hiervoor heb ik op de outputbalk geklikt. Vervolgens moest de output in deze
balk gelijk zijn aan 'The result of adding 5 and 4 is 9'. En zo kan ik zien dat het optellen werkt
![alt_text](https://i.imgur.com/cOh0BwT.png)
