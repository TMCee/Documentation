# Testaus
Tässä projektissa noudatettiin boy scout -sääntöä, eli codebasen testikattavuus jätettiin vähintäänkin yhtä hyvään kuntoon (kattavuuteen) kun projektin alkaessa. Tämä saavutettiin sillä, että tehtiin uusille ominaisuuksille testit niitä lisättäessä. Kaikki testattiin myös käsin kehitysvaiheessa varsinkin projektin alussa, sillä codebasen tuntemus ei ollut vielä kovin hyvällä mallilla joten testien kirjoittaminen olisi ollut hankalaa ilman kokonaiskuvaa testattavan komponentin rakenteesta. Tuntemus kuitenkin parani projektin edetessä ja testien kirjoittamisesta tuli huomattavasti nopeampaa. Projektin luonteen vuoksi testit usein käyttivät erityisiä fixtureita, joiden tekeminen oli paikoittain hieman vaivalloista, jolloin koettiin taas asian testaaminen käsin hiemn helpommaksi, ja testit tehtiin vasta lopuksi kun oltiin jo huomattu lisäyksen/muutoksen toimivuus.

## NetBeans-lisäosan testaus
NetBeans-lisäosaan lisätty toiminnallisuus koostuu pääosin C:lle toteutetusta "TestRunner":ista, sekä testituloksten parsijasta C:lle, sekä universaalille projektityypille. Pääosin lisätyt testit testaavat juuri näitä lisäyksiä. Testitulosten parsimisen yksittäiset vaiheet on testattu JUnit yksikkötesteillä. Testien suorittaminen (ohjelmakoodin kääntäminen ja suoritus) on testattu qa funktionaalisilla testeillä.

## TMC-komentorivityökalun testaus
TMC-komentirivityökalu on Ruby:lla kirjoitettu sovellus, jonka testit pohjautuvat vahvasti fixtureiden käyttöön. Testit on kirjoitettu RSpec BDD-testikehyksellä siten, että jokaisen toiminnon (päivitys, lähetys, lataus jne.) päätavoite testataan kaikilla reunatapauksilla.

## TMC-serverin testaus
TMC-server on myös testattu RSpec BDD testeillä. Useat toiminnallisuudet on täysin riippuvaisia lähetetystä tehtävästä, joten niiden testaaminen vaatii vahvasti fixtureiden käyttämistä. Siksi jokaisesta projektityypistä on tehty oma fixtuurinsa, joista jokaista käytetään jokaisen toiminnallisuuden testaamisessa. TMC-serveriin lisätyt muutokset ovat melko pieniä, joten niiden tekeminen vaati useimmiten vain muutaman testitapauksen lisäämistä.

# Tänne jotian CI:stä ja raportteihin linkki blaablaa
Tmc-server, tmc-netbeans ja tmc-client kukin ajaa testit ci palvelimella aina muutoksen githubiin pushattaessa.
## TMC-komentorivityökalu
tmc-client käyttää CInä [travis-ci:tä](http://travis-ci.org), joka on suosittu ryby yms. kevyiden ohjelmien testaamiseen.
## TMC-netbeans
Käyttää ci:nä [jenkinsiä](http://jenkins-ci.org/). Testiraportin löydät (täältä)[http://ci.testmycode.net/job/tmc-netbeans/]
## TMC-server
Käyttää ci:nä [jenkinsiä](http://jenkins-ci.org/). Testiraportin löydät (täältä)[http://ci.testmycode.net/job/tmc-server/]
