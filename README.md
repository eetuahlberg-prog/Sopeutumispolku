# Sopeutumispolku – staattinen verkkosivupaketti

Paketti sisältää nykyisen valmiin demon sellaisenaan. HTML, CSS, JavaScript,
toimenpideaineisto, fontit, Pohjois-Karjalan logo ja EU-tunnus ovat samoja kuin
lähtöversiossa. Sisältöä, ulkoasua, saavutettavuutta tai toimintalogiikkaa ei ole
muutettu. Juuka kuuluu Pielisen Karjalaan.

## Käyttö ja tiedostot

- Aloitussivu: `index.html`. Sen rinnalla ovat `style.css`, `data.js`, `app.js`
  ja `assets/`-kansio. Säilytä nämä nimet ja kansiorakenne.
- Ei asennusta, käännösvaihetta, npm-riippuvuuksia, tietokantaa, sovelluksen
  käyttäjätilejä, kirjautumista tai palvelinpuolen vastaustallennusta.
- Vastaukset ja muokkaukset säilyvät vain avoimen sivun muistissa. Sivun
  uudelleenlataus tai sulkeminen hävittää ne. Pysyvää selaintallennusta ei lisätty.
- Oma suunnitelma voidaan viedä TXT- tai CSV-tiedostoon, kopioida tai tulostaa
  ja tallentaa selaimen PDF-toiminnolla. Lataa lopputulos ennen sulkemista.
- Julkaise HTTPS-osoitteeseen myös leikepöydälle kopiointia varten. Pelkkään
  paikalliseen tiedoston avaamiseen voi liittyä selaimen rajoituksia.
- Fontit ja kuvat sisältyvät pakettiin. Lähdelinkit avaavat alkuperäisen
  tiekartan verkosta; lähde-PDF ei sisälly pakettiin.
- `.nojekyll` on GitHub Pagesin julkaisuasetus. README on julkaisuohje.
  ChatGPT Sitesin asetuksia tai riippuvuuksia ei ole mukana.

## GitHub Pages

1. Pura ZIP omalle koneellesi. Luo GitHubissa julkinen repositorio, esimerkiksi
   `sopeutumispolku`.
2. Lisää puretut tiedostot ja koko `assets/`-kansio repositorion `main`-haaran
   juureen (**Add file → Upload files**). Lisää myös `.nojekyll`.
   `index.html` tulee suoraan juureen, ei erillisen pakettikansion sisälle.
3. Avaa **Settings → Pages**. Valitse **Source: Deploy from a branch**,
   haaraksi **main** ja kansioksi **/(root)**. Tallenna.
4. Kun julkaisu valmistuu, avaa Pages-asetusten **Visit site** -linkki.
   Osoite on yleensä `https://KAYTTAJA.github.io/sopeutumispolku/`.
   Oma domain ei ole tarpeen. Käyttäjät avaavat julkisen sivun ilman kirjautumista.

Suhteelliset tiedostopolut toimivat myös repositorion alihakemistossa.
Päivitys tehdään korvaamalla vastaavat tiedostot samassa repositoriossa.

[GitHubin julkaisuohje](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## Azure Storage Static Website

1. Luo tai valitse Azure Portalissa staattisia verkkosivuja tukeva Storage account
   (esimerkiksi StorageV2). Avaa **Static website** ja valitse **Enabled**.
2. Aseta **Index document name** -kenttään `index.html` ja tallenna.
   Erillistä virhesivua ei toimiteta; jätä **Error document path** tyhjäksi.
3. Vie puretut `index.html`, `style.css`, `app.js`, `data.js` sekä koko `assets/`
   automaattisesti luotuun **$web**-säilöön. Käytä esimerkiksi Azure Storage
   Exploreria ja säilytä alikansiot: kuvan polun tulee olla
   `assets/eu-osarahoittama.png`, ei pelkkä tiedostonimi säilön juuressa.
   ZIP-tiedostoa ei julkaista sellaisenaan. README ja `.nojekyll` eivät ole
   Azure-julkaisussa tarpeen.
4. Käytä Static website -asetusten **Primary endpoint** -HTTPS-osoitetta.
   Jaa tämä verkkosivuosoite, älä Blob-palvelun tiedostolinkkiä. Varmista,
   että tilin verkkoasetukset sallivat sivun käytön julkisesta verkosta.

Jos HTML latautuu tiedostona, tarkista sen Content-Type: `text/html`.
CSS:n tyyppi on `text/css` ja JavaScriptin `text/javascript` tai
`application/javascript`. Oma domain tai erillinen sovelluspalvelin ei ole tarpeen.

[Microsoftin julkaisuohje](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website-how-to)

## Tarkistus julkaisun jälkeen

Avaa julkaistu HTTPS-linkki yksityisessä selainikkunassa. Kokeile esimerkkikuntaa,
valitse toimi, muokkaa kirjausta ja kokeile TXT-/CSV-vientiä sekä tulostusta.
Varmista samalla, että fontit, logot ja Saavutettavuus-linkki toimivat.
Nykyinen saavutettavuustoteutus ja sen ilmoittamat tarkistusten rajat säilyvät.

Paketoitaessa varmistettiin alkuperäisten sovellustiedostojen tavuntarkka
vastaavuus, paikallisten assettiviittausten löytyminen ja ZIP-tiedoston eheys.
Julkaisua käyttäjän GitHub- tai Azure-tilille ei ole tehty tämän paketin luonnissa.
