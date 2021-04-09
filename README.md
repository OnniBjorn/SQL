## Tehtävä 1

Omalla etunimelläni löytyi 1834 tapahtumaa. Hakemalla nimellä Matti suurinmassa osassa tuloksista nimenä oli jokin Matti nimen variaatio kuten Matz tai Matthias. Hakiessani Maija suurin osa nimistä oli Maja.

## Tehtävä 2

Olen syöttänyt sähköpostini lukuisiin eri palveluihin, nimeä ja syntymäpäivää kysytään loppujen lopuksi aika vähän.

## Tehtävä 3

![Kaavio](/kurssit.png)

## Tehtävä 4
SELECT * FROM Kurssisuoritus
## Tehtävä 5
SELECT kurssi FROM Kurssisuoritus
## Tehtävä 6
SELECT DISTINCT kurssi FROM Kurssisuoritus
## Tehtävä 7
SELECT * FROM Opiskelija WHERE nimi='Anna'
## Tehtävä 8 
SELECT * FROM Kurssisuoritus WHERE opiskelija='999999'
## Tehtävä 9
SELECT DISTINCT  pääaine FROM Opiskelija WHERE pääaine LIKE '%tiede%'
## Tehtävä 10
SELECT nimi, päivämäärä, arvosana FROM Kurssi, Kurssisuoritus WHERE Kurssi.kurssitunnus = Kurssisuoritus.kurssi
## Tehtävä 11
SELECT nimi, päivämäärä, arvosana FROM Opiskelija, Kurssisuoritus WHERE Opiskelija.opiskelijanumero = Kurssisuoritus.opiskelija
## Tehtävä 12
SELECT Kurssi.nimi AS kurssi, Tehtävä.nimi AS tehtävä FROM Kurssi, Tehtävä, Kurssitehtävä WHERE  Kurssi.kurssitunnus = Kurssitehtävä.kurssi AND Kurssitehtävä.tehtävä = Tehtävä.tunnus
## Tehtävä 13
SELECT Kurssi.nimi AS kurssi, Tehtävä.nimi AS tehtävä FROM Kurssi, Kurssitehtävä, Tehtävä, Tehtäväsuoritus, Opiskelija WHERE Opiskelija.nimi ='Anna' AND Kurssi.kurssitunnus = Kurssitehtävä.kurssi AND Tehtävä.tunnus = Kurssitehtävä.tehtävä AND Tehtäväsuoritus.tehtävä = Kurssitehtävä.tunnus  AND Tehtäväsuoritus.opiskelija = Opiskelija.opiskelijanumero
## Tehtävä 14
Ensimmäinen kyselyn tulos näyttää kaikki kolme Tietokantojen perusteet kurssin tehtävää, mutta toinen kysely näyttää kaikki opiskelijat, jotka ovat suorittaneet kyseisen kurssin tehtäviä. Eli toisessa taulukossa on viisi riviä kolmen sijaan, koska kolmesta tehtävästä on tehtäväsuorituksia tullut yhteensä viisi.
## Tehtävä 15







