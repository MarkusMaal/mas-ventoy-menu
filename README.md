![Markuse mälupulk logo](mas_flash.png)

# Markuse mälupulk (Ventoy menüü)

* Keel: GRUB/JSON 

* Valmimise aasta: 2023

* Viimane uuendus: 20. oktoober 2025. a

* Ilmumine videotes: [Minu buutitav mälupulk (2023. aasta uuendus)](https://www.youtube.com/watch?v=2uEY5dso_ho) (ilmub ka mõnedes [Markuse arvuti meelelahutus](https://www.youtube.com/playlist?list=PL6WkVx7vhlojSbsJVSxdXE1-hRRr5DUhS) episoodides)

* Eelkäija: [Markuse mälupulk (YUMI menüü)](https://github.com/MarkusMaal/mas-yumi-menu)

## Paigaldamise juhised

Paigalda mälupulgale kõigepealt [Ventoy](https://www.ventoy.net/en/download.html). Seejärel loo järgmised kaustad mälupulgal:

* multiboot\ - Ära siia otse ISOsid lisa, kasuta järgmisi alamkaustu:
  
  * linux\ - Siia kopeerid Linuxi ISOd
  
  * live\ - Siia kopeerid Live keskkondade ISOd
  
  * macos\ - Siia saab kopeerida ISOd, mida saaks Macis käivitada või töövahendid muude arvutite hackintoshimiseks
  
  * misc\ - Kõik muud ISOd (ei lange teistesse kategooriatesse)
  
  * windows\ - Siia kopeerid Windowsi ISOd

* ventoy\ - **Klooni selle repo sisu siia** (git clone)

See ongi kõik! Nüüd on teie mälupulgale buutites kategoriseeritud menüüd ja "Markuse mälupulk" teema! ISOsid saab lisada lihtsalt faile õigetesse kaustadesse kopeerides.

Võib tekkida küsimus - miks ma just sellist faili struktuuri kasutan, miks mitte lihtsalt ISO faile mälupulga juurkausta lisada? Põhjus on lihtne - minu mälupulkadel on lisaks operatsioonsüsteemi ISOdele ka palju muid erinevaid faile ning selline struktuur aitab Ventoy-l filtreerida tavalisi ISOsid muudest failidest terve failipuu läbikäimise asemel, mis vähendab buutimise aega!

## Menüüfailide redigeerimine

Üldiselt ei pea seda tegema, aga kui on soov luua enda struktuuri või lisada püsivus mõnedele ISO failidele, saab menüüfaile redigeerida ametliku "VentoyPlugson" tööriistaga. Aga seda saab teha ka käsitsi, kui muuta `ventoy\ventoy.json` faili.

## Teema muutmine

Markuse mälupulk kasutab kohandustega "Distro" GRUB teemat, mis asub kaustas `\ventoy\theme\Distro`. Saate otse seal kaustas teema faile muuta (nt taustapilti vms). Kui teile ei meeldi Distro teema, saate mingi muu teema alla laadida [siit](https://www.gnome-look.org/browse?cat=109) ja seejärel lisada `\ventoy\theme\` kausta. Teema rakendamiseks tuleb teil muuta järgmist sektsiooni "ventoy.json" failis:

```json
{
    "theme":{
        "file": "/ventoy/theme/Distro/theme.txt",
        "gfxmode": "1280x1024"
    }
}
```

Lihtsalt muutke "file" väärtust nii, et see suunaks alla laaditud teema theme.txt failile.

## Tekstirežiim

Saate lülituda tekstirežiimile või sealt väljuda vajutades F7 klahvi. BIOS süsteemides aktiveeritakse tekstirežiim automaatselt.

## Klassikaline failisirvija

Juhul kui teile ei meeldi esteetilised menüüd, siis saate vajutada F2 klahvi, et minna klassikalisse failisirvija režiimi, mida Ventoy vaikesättena kasutab.

## Secure Boot

Kui märkisite Ventoy paigaldamisel linnukese Secure Booti jaoks ja üritate mälupulka buutida arvutis, mis kasutab Secure Booti, siis võite näha ühte sinise taustaga veateadet. Selleks, et sellest lahti saada peate lisama Ventoy sertifikaadi enda arvutisse. Õpetus siin (inglise keeles): [How To Add Ventoy as a Secure Boot Option [Ventoy Secure Boot Problem] (Tutorial) - YouTube](https://www.youtube.com/watch?v=Z0dNMWyIsJg&t=13).
