<!-- V markdowne je možné použiť aj CSS -->

<style>

/* 
Cislovanie kapitol pomocou CSS:

https://gist.github.com/patik/89ee6092c72a9e39950445c01598517a */

h1 { counter-reset: h2counter; }
h2 { counter-reset: h3counter; }
h3 { counter-reset: h4counter; }
h4 { counter-reset: h5counter; }
h5 { counter-reset: h6counter; }
h6 {}

h2:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\0000a0\0000a0";
}

h3:before {
    counter-increment: h3counter;
    content: counter(h2counter) "." counter(h3counter) ".\0000a0\0000a0";
}

h4:before {
    counter-increment: h4counter;
    content: counter(h2counter) "." counter(h3counter) "." counter(h4counter) ".\0000a0\0000a0";
}

h5:before {
    counter-increment: h5counter;
    content: counter(h2counter) "." counter(h3counter) "." counter(h4counter) "." counter(h5counter) ".\0000a0\0000a0";
}

h6:before {
    counter-increment: h6counter;
    content: counter(h2counter) "." counter(h3counter) "." counter(h4counter) "." counter(h5counter) "." counter(h6counter) ".\0000a0\0000a0";
}

/*
Centrovanie obrazkov
https://stackoverflow.com/questions/255170/markdown-and-image-alignment/43691462#43691462

https://stackoverflow.com/questions/12090472/how-do-i-center-an-image-in-the-readme-md-file-on-github
*/

img[src*='#left'] {
    float: left;
}
img[src*='#right'] {
    float: right;
}
img[src*='#center'] {
    display: block;
    margin: auto;
}
</style>

# Nastavenie XAMPP

<center>Damián Nadžady Marek Šafařík Adrian Fáber</center>

# Obsah
[Nastavenie XAMPP](#nastavenie-xampp)
- [Nastavenie XAMPP](#nastavenie-xampp)
- [Obsah](#obsah)
  - [Nastavenie pre executable programy v CMD](#nastavenie-pre-executable-programy-v-cmd)
  - [Zapnutie PHP v CMD](#zapnutie-php-v-cmd)
  - [Pripojenie do databazy a orientovanie v nej](#pripojenie-do-databazy-a-orientovanie-v-nej)
<!-- Obsah vygenerovať neskor
ak mas extension tak CTRL+SHIFT+P a napisat create table of content
-->

## Nastavenie pre executable programy v CMD

Naprv si musíme skontrolovať ktoré cesty majú v sebe executable property pre zapnutie programov, ak v tomto výpise nemáme cestu k programu ktorý chceme spustit cez konzolu tak ho nebudeme mocť spustiť.

Do `CMD` napísemme príkaz `echo %PATH%` aby sme zistili aké cesty máme povolené.

![echo PATH](./images/WindowsTerminal_TpcCQFeGjS.png#center)

Ak chceme pridať executable cesty naprv potrebujeme zistiť kde sa nachádza `.exe` program ktorý hladáme

![echo PATH](./images/ApplicationFrameHost_ynTOqvZfCc.png#center)

![echo PATH](./images/ApplicationFrameHost_pj5wUYsKrQ.png#center)

Pre pridanie cesty stlacime `Windows + R` a zadáme daný príkaz. Následne pokračujeme podľa šipiek v obrázkoch.

![echo PATH](./images/explorer_lDulGpQVNR.png#center)

![echo PATH](./images/SystemPropertiesComputerName_1XK0tRg1aq.png#center)

![echo PATH](./images/SystemPropertiesComputerName_MGrynUjVVV.png#center)

Klikneme na Path a upraviť a pridáme novú cestu, zvýraznené cesty sú cesty k mysql a php

## Zapnutie PHP v CMD

Vďaka pridaniu cesty k programu `php.exe` vieme v CMD execuovať php súbory alebo zapnúť samotné PHP

![echo PATH](./images/WindowsTerminal_wRMf4cqHnH.png#center)

Prvým príkazom sme inicializovali PHP a druhým sme spustili daný súbor pomocou prikazu PHP v danej ceste

## Pripojenie do databazy a orientovanie v nej

Ujistime sa že máme zapnutý MySQL a Apache server

![echo PATH](./images/xampp-control_givBTwII7s.png#center)

Pripojíme sa na databázu ako `root` používateľ

príkaz: `mysql -uroot -p`

![echo PATH](./images/WindowsTerminal_rahEHSu4Pk.png#center)

pre `root` používateľa vieme zistiť heslo a IP adresu na ktorú by sa mal pripojiť v phpMyAdmin configu

![echo PATH](./images/notepad_I0QaT74f4X.png#center)

Databázu už máme vytvorenú tak si do nej vytvoríme tabuľku ktorá bude obsahovat 2 polia.

![echo PATH](./images/Clipboard.jpg)

Prvé pole bude `ID` ktoré je základom takmer každej databázy. Nastavíme si typ integer lebo `ID` sa udáva v číslach dlžku si nastavíme na 4 cifry to by malo zďaleka stačiť a ešte si nastavíme `auto increment` aby sa nám ID číslo samo zväčšovalo. Ďalší riadok si spravíme poľe `Name` ktoré bude mať kapacitu 30 znakov a ako typ si dáme samozrejme text.

![echo PATH](./images/Clipboard1.jpg)

Tu si môžme pozrieť SQL kód ktorý sa nám vygeneroval a môžme si ho skontrolovať. Potom už len stlačíme `Uložiť` a vytvorí sa nám tabuľka.

![echo PATH](./images/Clipboard2.jpg)

Prehľad štruktúry našej tabuľky.

![echo PATH](./images/Clipboard3.jpg)

Pomocou formulára odošleme do databázy meno, ktoré sa nám uloží a pridelí sa mu ID.

![echo PATH](./images/Clipboard4.jpg)

Tu môžeme vidieť kód zápisu dát do tabuľky kde je na začiatku úpnom začiatku jednoduchý html formulár a potom prepojenie s
databázou. V spodnej časti je odoslanie a zápis dát do databázi.

![echo PATH](./images/Clipboard5.jpg)

Tu môžeme vidieť ako sa nám spokojne zapísali naše mená do tabuľky.

![echo PATH](./images/Clipboard6.jpg)

# PID porty

## Príkaz Netstat

Ak chcete začať, otvorte príkazový riadok kliknutím na tlačidlo `Štart` a zadaním príkazu `cmd` . V príkazovom okne pokračujte a napíšte nasledujúci príkaz:


<!-- TODO: -->
<!-- Pridat aj veci dajake zo zaciatku roka co sme robili a aj dorobit fotky do pondelka (PID porty atd)
Potom este pridat dajaky problem co sme mali -->
