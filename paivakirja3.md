# Oppimispäiväkirja: Hajautettu git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__

## Harjoitukset 6 ja 7

Nämä harjoitukset olivat osion vaikeimmat, ja niissä tuli eniten ongelmia. Harjoituksessa 6 minun ja virtuaalisen tiimikaverin muutokset osuivat samaan styles.css-tiedostoon. Push hylättiin, koska etärepositoriossa oli uusia muutoksia, ja git pull aiheutti merge conflictin. Tällä kertaa en säikähtänyt, koska harjoituksesta 4 muistin, ettei konflikti ole vaarallinen. Ratkaisin sen pitämällä molempien muutokset ja poistamalla konfliktimerkinnät. Tilannetta sekoitti hetken se, että VS Coden sync-nappi ehti tehdä pullin ja pushin puolestani, joten tarkistin git statuksella ja git logilla, missä vaiheessa olin.

Toinen ongelma oli, että kello ei päivittynyt jatkuvasti, vaikka tiimikaverin piti jo olla toteuttanut sen. Selvisi, että hän oli tehnyt uuden talletuksen vasta sen jälkeen, kun olin viimeksi hakenut muutokset. Löysin syyn komennoilla git fetch ja git status, ja git pull toi puuttuvan muutoksen. Tästä opin, että muiden muutokset kannattaa hakea aina ennen oman työn jatkamista. Aluksi tuntui hassulta, että nappi tehtiin ensin ja poistettiin sitten, mutta ymmärsin, että tarkoitus oli harjoitella tiimityötä ja sitä, että vaatimukset muuttuvat kesken projektin.

Harjoitus 7 oli helpompi, koska harjoituksen 6 jälkeen etärepositorion kanssa toimiminen oli jo tuttua. Yhdistämispyynnön tekeminen GitHubissa oli selkeää, ja siitä näki hyvin, miten muutokset kulkevat ominaisuushaarasta päähaaraan. Hetken hämmensi, että haaran poistamisen jälkeen origin/ominaisuus näkyi vielä git logissa, mutta git fetch --prune poisti sen. Samalla ymmärsin, että haaran poistaminen poistaa vain nimen, ja talletukset sekä yhdistämispyynnön historia säilyvät.

Eniten auttoivat git status, git log --graph ja virheilmoitusten rauhallinen lukeminen. Opin erityisesti, että tiimityössä pitää hakea muiden muutokset ennen omien viemistä ja että kokeileminen itse selventää, mitä repositoriossa oikeasti tapahtuu.


## Harjoituksissa 6 ja 7 käyttämäni Git-komennot

| Komento  | Kuvaus |
| ---------| ------ |
| git remote add actions <url> | lisää tiimikaverin repositorion etärepositorioksi nimellä actions |
| git fetch actions main | hakee actions-repositorion main-haaran muutokset |
| git merge actions/main --allow-unrelated-histories | yhdistää repositorion, jolla ei ole yhteistä historiaa oman repositorion kanssa |
| git switch -c develop | luo develop-haaran ja siirtyy siihen |
| git push -u origin develop | vie develop-haaran GitHubiin |
| git add | lisää muutokset seuraavaan committiin |
| git commit -m " " | tallentaa muutokset commitiksi |
| git push | vie muutokset etärepositorioon |
| git pull | hakee etärepositorion muutokset ja yhdistää ne nykyiseen haaraan |
| git pull --no-rebase | hakee muutokset ja yhdistää ne mergellä |
| git status | näyttää repositorion nykyisen tilanteen, esimerkiksi konfliktit |
| git log --oneline | näyttää commit-historian lyhyesti |
| git log --oneline -- scripts.js | näyttää vain tiedostoon scripts.js vaikuttaneet commitit |
| git log -1 <talletus> | näyttää yhden commitin tiedot ja commit-viestin |
| git fetch origin | hakee etärepositorion muutokset yhdistämättä niitä |
| git show <talletus>:scripts.js | näyttää tiedoston sisällön tietyssä commitissa |
| git show <talletus> --stat | näyttää, mitkä tiedostot commit muutti |
| git show <talletus> | näyttää commitin sisällön ja muutokset |
| git switch main | vaihtaa main-haaraan |
| git pull origin main | hakee ja yhdistää muutokset origin-etärepositorion main-haarasta |
| git merge develop | yhdistää develop-haaran main-haaraan |
| git push origin main | vie main-haaran etärepositorioon |
| git tag harjoitus6 | lisää tunnisteen harjoitus6 viimeisimpään talletukseen |
| git push origin harjoitus6 | vie tunnisteen GitHubiin |
| git log --oneline --graph --all | näyttää kaikkien haarojen historian graafina |
| git switch -c ominaisuus | luo ominaisuushaaran yhdistämispyyntöä varten |
| git push -u origin ominaisuus | vie ominaisuushaaran GitHubiin, jotta siitä voi tehdä yhdistämispyynnön |
| git branch -d ominaisuus | poistaa paikallisen ominaisuushaaran sen jälkeen, kun se on yhdistetty |
| git fetch --prune | poistaa paikallisesta repositoriosta tiedot etärepositoriosta poistetuista haaroista |
| git tag harjoitus7 | lisää tunnisteen harjoitus7 viimeisimpään talletukseen |
| git push origin harjoitus7 | vie tunnisteen GitHubiin |