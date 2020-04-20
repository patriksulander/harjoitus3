# Palvelinten hallinta - harjoitus3

###### Aloitettu 20.4.2020 klo. 15:00

## A) Tehdään raportti MarkDownina.

  Ensimmäiseksi päivitin järjestelmän ja asensin gitin. 
 
 1.`sudo apt-get update`

2.`sudo apt-get install git`

3.`sudo salt '*' cmd.run 'whoami'` --> salt toimii

4. Loin githubissa uuden hakemiston. (Lisäsin README -tiedoston sekä GNU General Public License v3.0 ja hakemiston nimesin "harjoitus3"

![1]

5. Kloonasin uunituoreen hakemistoni virtuaalikoneelle --> `git clone https://github.com/patriksulander/harjoitus3.git`

6. Loin uuden MarkDown tiedoston hakemistoon--> `sudo vim harjoitus3.md`  

7. Kokeilin toimiiko muutokset Teron opettamalla komennolla: 
    `git add . && git commit; git pull && git push`
Kyseinen komento ajaa siis kaiken ja sain nyt sellaisen käsityksen, että tällä pitäisi pärjätä aika pitkälle.

8. error: cannot open .git/FETCH_HEAD: Permission denied, ongelma oli selkeä ei ollut tarpeeksi oikeuksia. Ratkaisuksi löysin komennon: `sudo chown -R patrik .git/` --> sen jälkeen lähti pelittämään
9. `git config --global credential.helper "cache --timeout=3600"` --> Tunnin ajan pystyy antamaan komentoja, ilman tunnusten laittamista.

## D) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

1. `git log` --> Komento näyttää committien historian (tekijä, aika, kommentti).

2. `git diff` --> ei tapahtunut mitään... Kokeilin luoda tiedostoja --> vim testi.txt hakemistoon --> add . ja git commit, mutta mitään ei tapahdu.
3. `git blame` --> Komento näyttää mitä, milloin ja kuka on päivittänyt tiedostoa.

## E) Tee tyhmä muutos gittiin

1. harjoitus3 hakemistossa muutin testi.txt tiedostoa --> `mv testi.txt testimuutos.txt` ja muokkasin sisältöä.

2. `git reset --hard`

3. Tiedostot palautuivat viimeisimpään commit tilaan.

## F) Uusi salt-moduli

1. Päätin asentaa openvpn (mietin konfigurointia, mutta aivokapasiteetti ei riittänyt muuhun kuin miettimiseen)

2. Loin kansion --> `sudo mkdir /srv/salt/openvpn/`

3. Sisälle loin init.sls tiedoston:

4. `sudo salt '*' state.apply openvpn` , ajoin komennon kaksi kertaa varmistuakseni modulin asennuksesta idempotenttina.


### Lähteet:

<!-- wp:paragraph -->
<p>http://terokarvinen.com/2016/publish-your-project-with-github  Luettu: 20.4.2020</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>http://terokarvinen.com/2020/configuration-managment-systems-palvelinten-hallinta-ict4tn022-spring-2020/#h3-versionhallinto  Luettu: 20.4.2020</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>https://github.com/salt-formulas/salt-formula-openvpn   Luettu: 21.4.2020</p>
<!-- /wp:paragraph -->


[1]: https://imgur.com/a/dP0dNCm
