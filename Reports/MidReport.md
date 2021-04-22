# Harjoitustyö väliraportti

Ryhmän harjoitustyön tarkoituksena on todentaa yrityksen tietoturvaa tekemällä sen infrastruktuuria vastaan penetraatiotestaus ja näin myös oppia lisää penetraatiotestauksen työkaluista. 
Projektin eteneminen on sujunut hyvin ja vaikuttaa valmistuvan ajallaan. 

Projekti ryhmän on saanut suoritettua tavoitteensa maalikoneessa ja Kohteena harjoituksessa käytettiin HackTheBox ympäristöstä löytyvää "Laboratory" maalikonetta. 
Kyseinen maali valittiin sen haavoittuvuuden takia sillä sen todettiin olevan todella oleellinen yritysten kannalta. Kohteeseen hyökätessä osoittautui tärkeäksi se, että tutkimme haavoittuvuuksia liittyen muihin tietoturvariskeihin, kuten siihen, että miten henkilöstö säilyttää tärkeitä tietoja yms. on myös tärkeää. 
Maalikoneen haavoittuvuus oli Gitlab palvelussa jota käytetään versionhallintaan monessa eri yrityksessä.  
Kyseinen haavoittuvuus (CVE-2020-10086) mahdollisti hyökkääjän hankkia tietoa järjestelmästä jossa Gitlabia ylläpidettiin. kyseisessä järjestelmäversiossa oli arbitary file read ja remote code execution exploitit, joten tämä yksi versionhallintaan liittyvä tietoturvariski, muiden riskien ohella saattoi koko yrityksen infran vaaraan. 
Koneen penetraatiotestauksesta on tehty raportointi ja siinä avataan kuinka haavoittuvuus on löydetty ja miten sitä käytetään hyödyksi hyökkäyksessä (https://github.com/KakoMirai/CTF_analyzation/tree/main/Laboratory_HTB).

Ryhmä on analysoinut haavoittuvuutta ja alkanut kartoittamaan kuinka yritys pystyisi suojaamaan omaa toimintaansa, jotta kyseinen tai samanlainen haavoittuvuus ei häiritsisi toimintaa. Haavoittuvuus mahdollisti hyökkääjän varastaa järjestelmän tietoja, kuten esimerkiksi kohdekoneen käyttäjien käyttäjänimet. Järjestelmästä myös saatiin hankittua Gitlabin käyttämä "secret_key_base", jonka avulla voidaan todentaa hyökkäävä kone osaksi Gitlab ympäristöä. Tämän haavoittuvuuden avulla pystyimme huijaamaan kohdejärjestelmää niin, että se luuli meidän käyttämiä keksejä sen omiksi evästeiksi.

Harjoitustyö jatkuu raporttien kirjaamisella ja anasyloinnin kehittämisellä. Mahdollisuuden mukaan ryhmä yrittää ratkaista myös toisenkin HackTheBox maalikoneen jossa olisi joko samantyyppinen haavoittuvaisuus tai mahdollisimman erillainen haavoittuvaisuus.

Projekti on syventänyt osaamistamme tietoturvan hallinnasta siinä mielessä, että vaikka ymmärrämme sen, että kohdejärjestelmään on luotu paljon tietoturvaongelmia, voisivat nämä ongelmat ja riskit löytyä myös oikean elämän esimerkeistä. Yksi viimeisimmistä suomessa olevista tietomurroista, jota ei välttämättä tarvitse mainita nimeltä, johtui mitä todennäköisemmin siitä, että henkilöstä ei oltu koulutettu oikein suojaamaan tietoja. 

Tommi Muhonen ja Aki Ronkainen
