# Komponentit
## Asiakaspuolen sovellukset
TMC-serverin käyttöön tarjotaan kaksi asiakaspuolen työkalua. Toinen näistä on NetBeans kehitysympäristöön integroitu lisäosa, jonka avulla voidaan ladata, päivittää ja lähettää tehtäviä palvelimelle kehityksen lomassa, sekä suorittaa testit lokaalisti. Vaihtoehtoisesti asiakas voi käyttää komentoriviohjelmaa jolla voidaan suorittaa kaikki samat toimminot. Lisää tietoja NB-integraatiosta [tässä](https://github.com/TMCee/tmc-netbeans) ja komentorivityökalusta [tässä](https://github.com/TMCee/tmc-client).

## NB-plugin
NB-clientin arkkitehtuuri on NB-plugin frameworkille tyypillinen sen GUI komponenteilla toteutettu MVC-malli. Siinä erilaiset toiminnot tapahtuvat Action-olioilla.

## Palvelimen komponentit
### TMC-server
TMC-palvelimen ydin on TMC-server sovellus, joka on toteutettu Ruby on Rails ohjelmointikehyksellä. Se noudattaa Rails sovelluksille tuttua MVC-mallia.
Rails sovelluksen app/models kansio sisältää kaikki model-oliot, kun taas lib kansio sisältää kaikki puhtaasti tai ainakin lähtes puhtaasti toiminnalliset oliot. 

### TMC-sandbox
TMC-sandbox on hiekkalaatikko joka suorittaa opiskelijan koodin Linux virtuaalikoneessa. Se vastaanottaa pyyntöjä suorittaa koodia TMC-server palvelimelta ja vastaa tuloksen ilmoittamisesta takaisin palvelimelle. TMC-sandbox käyttää testien suorittamiseen omaa "TestRunneria", joka suorittaa testit, ja kirjoittaa niiden tulokset NetBeans-palikan haluamaan muotoon.

## Ohjelmistotuotantoprojektin muutokset TMC-ohjelmistojen rakenteeseen
Emme toteuttaneet rakennetta muuttavia toiminnallisuuksia kurssin aikana. Lisäsimme tuen C ja 'universal' projektityypeille, sekä lukuisa muita pieniä lisäyksiä ja parannuksia. Palvelimen muutokset olivat lähinnä uusia periviä luokkia, moduuleita, sekä metodeita, eivätkä ne siten muuttaneet ohjelmiston rakennetta. NB-clienttiin lisättiin lähinnä uusia Action-olioita, sekä uusia GUI komponentteja, eivätkä nekään vaikuttaneet ohjelman yleisrakenteeseen.
