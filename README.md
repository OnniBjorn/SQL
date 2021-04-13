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
SELECT nimi FROM Kurssi LEFT JOIN Kurssitehtävä ON Kurssi.kurssitunnus= Kurssitehtävä.kurssi WHERE Kurssitehtävä.kurssi IS null
## Tehtävä 16
SELECT kurssi AS kurssikoodi, COUNT(*) AS lukumäärä FROM Kurssisuoritus GROUP BY kurssi
## Tehtävä 17
SELECT kurssi.nimi AS kurssi, COUNT(Kurssisuoritus.kurssi) AS lukumäärä FROM Kurssi, Kurssisuoritus Where kurssi.kurssitunnus = kurssisuoritus.kurssi GROUP BY kurssi.nimi
## Tehtävä 18
SELECT kurssi.nimi AS kurssi, COUNT(Kurssisuoritus.kurssi) AS lukumäärä FROM Kurssi LEFT JOIN Kurssisuoritus ON kurssi.kurssitunnus = kurssisuoritus.kurssi GROUP BY kurssi.nimi
## Tehtävä 19
CREATE TABLE Kurssi (kurssitunnus, nimi, kuvaus)
## Tehtävä 20
INSERT INTO Kurssi (kurssitunnus, nimi, kuvaus) VALUES('12345','SQL-kielen perusteet', "SELECT 'Hei maailma'")
## Tehtävä 21
CREATE TABLE Testi(testi integer, taulu date)  
PRAGMA TABLE_INFO(Testi)
## Tehtävä 22
CREATE TABLE Kurssi  
(  
   kurssitunnus integer, nimi var(500), kuvaus var(500)  
)  
PRAGMA TABLE_INFO (Kurssi)  
## Tehtävä 23
Opiskelijanumero asettuu automaattisesti seuraavaksi numeroksi, jollei sitä ole asetettu.  
Kun yrität lisätä saman ennalta määritettyn opiskelijanumeron useasti tulee  Virhe:Error: UNIQUE constraint failed, joka johtuu siitä että kahta samaa opiskelijanumeroa ei voi olla vaan kaikkien pitää olla uniikkeja.
## Tehtävä 24
CREATE TABLE Kurssi  
(  
 kurssitunnus integer PRIMARY KEY,  
 nimi varchar(500),  
 kuvaus varchar(500)  
)

INSERT INTO Kurssi (kurssitunnus, nimi) VALUES (42, 'Meaning of Life')  
Tämän kyselyn usein suorittaminen ei onnistunut, koska kurssitunnus ei ole uniikki.
## Tehtävä ?
INSERT INTO Kurssisuoritus (opiskelija,kurssi,päivämäärä,arvosana,opintopistemäärä) VALUES ('1','2','24.2.2021','4','1')
## Tehtävä 25
PRAGMA foreign_keys = ON;  

CREATE TABLE Tehtävä (  
   tunnus interger PRIMARY KEY,  
   nimi varchar(500) NOT NULL,  
   kuvaus varchar(500)  
);

CREATE TABLE Kurssitehtävä (  
   tunnus interger PRIMARY KEY,   
   tehtävä varchar(500) ,  
   kurssi varchar(500),  
   FOREIGN KEY(tehtävä) REFERENCES Tehtävä(tunnus),  
   FOREIGN KEY(kurssi) REFERENCES Kurssi(kurssitunnus)  
);
## Tehtävä 26
INSERT INTO Tehtävä (tunnus,nimi, kuvaus) VALUES('44','Matematiikka', 'Geometria');  
INSERT INTO Tehtävä (tunnus,nimi, kuvaus) VALUES('45','Englanti', 'Perusteet');

INSERT INTO Kurssi (kurssitunnus,nimi,kuvaus) VALUES('44','Matikka','Geometrian perusteet');  
INSERT INTO Kurssi (kurssitunnus,nimi,kuvaus) VALUES('45','Englanti','Englannin perusteet');
## Tehtävä 27

ALTER TABLE komennolla voi lisätä, poistaa tai muokata taulukoita.  

Tällä komennolla voi lisätä uuden sarakkeen esimerkiksi opiskelijan sähköpostin.  
```
ALTER TABLE Opiskeljia  
ADD Sähköposti varchar(100);  
```
```
ALTER TABLE Opiskeljia  
ADD Syntymävuosi varchar(100);  
```

Tällä komennolla sarakkeen voikin poistaa.  

```
ALTER TABLE Opiskelija  
DROP COLUMN Sähköposti;  
```

Tällä komennolla sarakkeissa olevaa datan tyyppiä voi muuttaa esimerkiksi perus tekstistä päivämääräksi.  

```
ALTER TABLE Opiskelija  
ALTER COLUMN Syntymävuosi year;  
```
