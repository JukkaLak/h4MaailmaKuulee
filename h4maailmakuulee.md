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
- 

  
