# x) Artikkelitiivistelmät
## Teoriasta käytäntöön pilvipalvelimen avulla (h4)
### a) Pilvipalvelimen vuokraus ja asennus
- Artikkelin kohdassa a) kuvailtiin, miten vuokrataan ja asennetaan pilvipalvelin ja sille domain-nimi, joka osoittaa kyseiselle palvelimelle
- Palvelimen voi saada käyttöön ilmaiseksi GitHub Educationin GitHub Student Developer Pack -paketin avulla, jota voi hyödyntää palvelimen vuokraamiseen DigitalOceanilta ja domain-nimen vuokraamiseen Namecheapiltä
- Palvelimen vuokraus DigitalOceanista tapahtuu aluksi luomalla tunnukset ja lisäämällä maksukorttitiedot
- Palvelimen asennus tapahtuu Droplets-valikosta
- Palvelinta asentaessa kannattaa valita halvimmat mahdolliset paketit ja muut palvelut, jos palvelimen haluaa vuokrata vain testikäyttöön.
- Datakeskus, jossa palvelin toimii, kannattaa valita mahdollisimman läheltä sen käyttöpaikkaa ja mieluiten EU-alueelta
### d) Palvelin suojaan palomuurilla
- Palomuurin asentaminen virtuaalipalvelimelle tapahtuu ottamalla ensin yhteys virtuaalipalvelimeen syöttämällä sen IP-osoite komennolla
    ```$ssh root@123.456.7.8``` ja tämän jälkeen syötetään palvelimelle luotu salasana
- Jos palvelinta käyttää ensimmäistä kertaa, kannattaa hakea koneen päivitystiedot komennolla
    ```$ sudo apt-get update```
- Palomuuri asenntaan komennolla
    ```$ sudo apt-get install ufw``` ja siihen tehdään reikä komennolla
    ```$ sudo ufw allow 22/tpc``` ja lopuksi palomuuri laitetaan päälle komennolla
    ```$ sudo ufw enable```
### e) Kotisivut palvelimelle
- Uuden web-palvelimen asennus aloitetaan lisäämällä virtuaalipalvelimen terminaalissa uusi käyttäjä komennolla
    ```$ sudo adduser kayttaja``` ja sille asetetaan salasana sekä annetaan nimitiedot
- Uudesta käyttäjästä tehdään pääkäyttäjä komennolla
    ```$ sudo adduser kayttaja sudo```
- Uudella käyttäjällä otetaan ssh-yhteys virtuaalipalvelimeen komennolla
    ```$ ssh kayttaja@123.456.7.8```
- Juuri lukitaan komennolla
    ```$ sudo usermod -lock root```
### f) Palvelimen ohjelmien päivitys
- Tiedot saatavilla olevista päivityksistä haetaan komennolla
    ```$ sudo apt-get update```
- Päivitykset asennetaan komennolla
    ```$ sudo apt-get upgrade```
- Tietoturvapäivitykset asennetaan komennolla
    ```sudo apt-get dist-upgrade```

## First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS
- Tässä artikkelissa kuvataan lyhyesti tärkeimmät työvaiheet virtuaalipalvelimen asennukseen DigitalOceanissa ja DNS-nimen vuokraamiseen Namecheapissa
- Ehkä tärkein asia on luoda hyvä salasana palvelimelle, jotta sinne ei pääse murtautumaan helposti
- Aluksi palvelimelle kirjaudutaan käyttämällä sen IP-osoitetta esimerkiksi komennolla
    ```$ ssh root@10.0.0.1```
- Ennen kuin palomuuri kytketään päälle, siihen tehdään reikä komennolla
    ```$ sudo ufw allow 22/tcp```. Palomuuri kytketään päälle komennolla
    ```$ sudo ufw enable```
- Palvelimelle luodaan uusi käyttäjä komennolla
    ```$ sudo adduser kayttaja``` ja käyttäjälle annetaan sudo-oikeudet komennolla
    ```$ sudo adduser kayttaja sudo```
- Palvelimen juuri lukitaan komennolla
    ```$ sudo usermod --lock root```
- Palvelimen ohjelmat päivitetään ensin hakemalla saatavilla olevat päivitykset komennolla
    ```$ sudo apt-get update``` ja päivitykset asennetaan komennolla
    ```$ sudo apt-get upgrade```

# a) Pilvipalvelimen vuokraus
Päätin vuokrata pilvipalvelimen DigitalOceanilta ja hyödynsin tähän GitHub Educationin tarjoamia ilmaisia krediittejä. Aloitin rekisteröitymällä käyttäjäksi sähköpostilla. Syötin käyttäjätietoni ja avasin sähköpostiini tulleen varmennusviesti ja seuraavaksi minulta kysyttiin, mihin tarkoitukseen käytän DigitalOceania sekä muita lisätietoja ja valitsin seuraavanlaiset vaihtoehdot:
![Näyttökuva (31).png](https://github.com/JukkaLak/h4MaailmaKuulee/blob/main/N%C3%A4ytt%C3%B6kuva%20(31).png)
Tämän jälkeen syötin maksutietoni ja kun olin ne syöttänyt onnistuneesti, minulle avautui seuraava etusivunäkymä:
![Näyttökuva (32).png](https://github.com/JukkaLak/h4MaailmaKuulee/blob/main/N%C3%A4ytt%C3%B6kuva%20(32).png)
Seuraavaksi valitsin vaihtoehdon "Deploy a virtual machine". Valitsin datakeskuksen sijainniksi Amsterdamin, koska se on lähimpänä nykyistä käyttöpaikkaani ja on myös suotavaa, että datakeskus sijaitsee toisessa EU-maassa. Valitsin käyttöjärjestelmäksi Debian 12 x64, koska sitä olen käyttänyt aiemmin kurssilla. Paketiksi valitsin peruspaketin, tavallisen prosessori SSD-kovalevyllä ja valitsin vaihtoehdon, jossa prosessorin koko on 1 GB ja kovalevyn koko 25 GB. Halvempikin vaihtoehto olisi ollut olemassa, mutta epäilin että siinä olisi ollut liian pieni prosessori ja kovalevy, joten valitsin toiseksi halvimman vaihtoehdon. Autentikaatiomenetelmäksi valitsin salasanan. Lopuksi kysyttiin, kuinka monta konetta halusin luoda ja loin vain yhden koneen ja annoin koneelle julkisen nimen (hostname) "muuli", jotta kone voidaan tunnistaa. Mitään lisämaksullisia palveluita en konetta luodessa valinnut, koska en niitä tarvitse. Kun olin saanut asetukset tehtyä, painoin "Create Droplet"-painiketta ja tämän jälkeen uusi virtuaalikone oli luotu ja koneen nimi ja IP-osoite näkyivät projektini Resources-välilehdellä
![Näyttökuva (33).png]


  
