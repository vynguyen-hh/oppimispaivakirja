# Oppimispäiväkirja: Paikallinen git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__


Ensimmäiset kolme harjoitusta sekä perustoiminnoita olivat melko helppoja.

Ensimmäinen ongelma tuli oppimispäiväkirjan luomisen tehtävässä. Olin vahingossa luonut oppimispäiväkirjan kansion hello-repository-kansion sisälle. Jouduin perumaan tehdyn commitin ja järjestämään kansiot uudelleen niin, että oppimispäiväkirja ja Git-repository olivat erillään. Tässä opin paremmin, miten Git-repository liittyy kansiorakenteeseen.

Suurin haaste oli harjoitus 4, jossa käsiteltiin haaroja (branch) ja yhdistämistä (merge). Ymmärsin aluksi tehtävän väärin ja lisäsin style.css-tiedoston vahingossa master-haaraan. Luin tehtävän uudelleen ja käytin git reset --soft HEAD~1 -komentoa, jotta sain muutokset takaisin ja pystyin tekemään ne oikeassa haarassa.

Myöhemmin yhdistämisen vaiheessa tuli merge conflict. VS Coden merge editor teki tilanteesta aluksi sekavan, joten keskeytin mergen git merge --abort -komennolla ja tein sen uudelleen. Lopulta sain mergen onnistumaan.

Vaikeuksista huolimatta opin erityisesti haarojen ja yhdistämisten toimintaa. git status, git branch ja git log auttoivat tarkistamaan, missä tilanteessa repository oli. Tehtävänannon uudelleen lukeminen ja komentojen kokeileminen käytännössä auttoivat eniten.



## Osiossa käyttämäni Git-komennot

| Komento  | Kuvaus |
| ---------| ------ |
| git init | luo Git-repositorion |
| git status | näyttää repositorion nykyisen tilanteen |
| git add | lisää muutokset seuraavaan committiin |
| git commit -m " " | tallentaa muutokset commitiksi |
| git branch | näyttää olemassa olevat haarat |
| git switch main | vaihtaa main-haaraan |
| git log --oneline | näyttää commit-historian lyhyesti |
| git tag harjoitus | luo tagin viimeisimpään talletuksiin |
| cd ..\git-oppimispaivakirja | siirtyy Git-repositorion ulkopuolella olevaan oppimispäiväkirjan kansioon |
| git reset --soft HEAD~1 | peruu viimeisen talletuksen ja säilyttää muutokset |
| git merge --abort | keskeyttää yhdistämisen ja palauttaa tilanteen ennalleen |
| git merge --no-ff tyylit | yhdistää tyylit-haaran nykyiseen haaraan |