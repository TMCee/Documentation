# Komponentit
## Asiakaspuolen sovellukset
TMC-serverin käyttöön tarjotaan kaksi asiakaspuolen työkalua. Toinen näistä on NetBeans kehitysympäristöön integroitu lisäosa, jonka avulla voidaan ladata, päivittää ja lähettää tehtäviä palvelimelle kehityksen lomassa, sekä suorittaa testit lokaalisti. Vaihtoehtoisesti asiakas voi käyttää komentoriviohjelmaa jolla voidaan suorittaa kaikki samat toimminot. Lisää tietoja NB-integraatiosta [tässä](https://github.com/TMCee/tmc-netbeans) ja komentorivityökalusta [tässä](https://github.com/TMCee/tmc-client).

## Palvelimen komponentit
### TMC-server
TMC-palvelimen ydin on TMC-server sovellus, joka on toteutettu Ruby on Rails ohjelmointikehyksellä. Se noudattaa Rails sovelluksille tuttua MVC-mallia.

### TMC-sandbox
TMC-sandbox on hiekkalaatikko joka suorittaa opiskelijan koodin Linux virtuaalikoneessa. Se vastaanottaa pyyntöjä suorittaa koodia TMC-server palvelimelta ja vastaa tuloksen ilmoittamisesta takaisin palvelimelle. TMC-sandbox käyttää testien suorittamiseen omaa "TestRunneria", joka suorittaa testit, ja kirjoittaa niiden tulokset NetBeans-palikan haluamaan muotoon.

# Tänne jotain deltajeja jos tarvitsee, mutta ei kai ainakaan tmc-serveristä
