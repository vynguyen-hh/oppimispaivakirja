# Oppimispäiväkirja: Hajautettu git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__

## Harjoitus 5

Etärepositorion perustaminen GitHubiin oli melko helppoa. Tyhjän repositorion luominen, origin-etärepositorion lisääminen ja master-haaran vieminen GitHubiin onnistuivat ohjeita seuraamalla, ja git remote -v auttoi tarkistamaan, että asetukset olivat oikein.

Haastavampaa oli ymmärtää, miten paikallinen repository ja GitHubissa oleva repository eroavat toisistaan. Tehtävässä tein muutoksen suoraan GitHubin web-käyttöliittymässä ominaisuushaaraan, jolloin etärepositoriossa oli eri sisältö kuin paikallisessa. Aluksi en ollut varma, mitä fetch oikeastaan tekee. Vertasin git status -komennon tulostetta ennen fetchiä ja sen jälkeen ja huomasin, että Git kertoo vasta fetchin jälkeen paikallisen haaran olevan jäljessä. Tästä ymmärsin, että fetch vain hakee muutokset eikä yhdistä niitä, vaan yhdistäminen pitää tehdä erikseen.

Eniten auttoi se, että kokeilin komentoja järjestyksessä ja katsoin joka vaiheessa git status- ja git branch -komennoilla, missä tilanteessa paikallinen ja etärepository olivat. Myös GitHubin web-käyttöliittymän katsominen rinnakkain auttoi hahmottamaan, mitä haaroja missäkin oli.

## Harjoituksessa 5 käyttämäni Git-komennot

| Komento  | Kuvaus |
| ---------| ------ |
| git remote add origin <url> | lisää GitHubissa olevan repositorion etärepositorioksi nimellä origin |
| git remote -v | näyttää etärepositorioiden asetukset |
| git push -u origin main | vie main-haaran GitHubiin ja asettaa sen seurattavaksi haaraksi |
| git switch -c new-feat | luo uuden ominaisuushaaran ja siirtyy siihen |
| git add | lisää muutokset seuraavaan committiin |
| git commit -m " " | tallentaa muutokset commitiksi |
| git branch | näyttää paikalliset haarat |
| git push -u origin new-feat | vie uuden haaran etärepositorioon |
| git status | näyttää repositorion tilanteen, esimerkiksi onko paikallinen haara jäljessä etärepositoriosta |
| git fetch | hakee etärepositorion muutokset yhdistämättä niitä |
| git switch --detach origin/new-feat | siirtyy tarkastelemaan etärepositoriosta haettua haaraa ilman, että se muuttuu paikalliseksi haaraksi |
| git switch new-feat | palaa paikalliseen new-feat-haaraan |
| git merge origin/new-feat | yhdistää etärepositorion haaran muutokset paikalliseen haaraan |
| git switch main | vaihtaa main-haaraan |
| git merge new-feat | yhdistää new-feat-haaran main-haaraan |
| git push | vie muutokset etärepositorioon |
| git tag harjoitus5 | lisää tunnisteen viimeisimpään talletukseen |
| git push origin harjoitus5 | vie tunnisteen GitHubiin |
| git log --oneline | näyttää commit-historian lyhyesti |