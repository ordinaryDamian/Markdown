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
<!-- Obsah vygenerovať neskor-->

## Nastavenie pre executable programy v CMD

Naprv si musíme skontrolovať ktoré cesty majú v sebe executable property pre zapnutie programov, ak v tomto výpise nemáme cestu k programu ktorý chceme spustit cez konzolu tak ho nebudeme mocť spustiť.

Do `CMD` napísemme príkaz `echo %PATH%` aby sme zistili aké cesty máme povolené.

![echo PATH](./images/WindowsTerminal_TpcCQFeGjS.png#center)

Ak chceme pridať executable cesty naprv potrebujeme zistiť kde sa nachádza .exe program ktorý hladáme

![echo PATH](./images/ApplicationFrameHost_ynTOqvZfCc.png#center)

![echo PATH](./images/ApplicationFrameHost_pj5wUYsKrQ.png#center)

Pre pridanie cesty stlacime `Windows + R` a zadáme daný príkaz.

![echo PATH](./images/explorer_lDulGpQVNR.png#center)
 
![echo PATH](./images/SystemPropertiesComputerName_1XK0tRg1aq.png#center)

![echo PATH](./images/SystemPropertiesComputerName_MGrynUjVVV.png#center)

Klikneme na Path a upraviť a pridáme novú cestu, zvýraznené cesty sú cesty k mysql a php

## Pripojenie do databazy a orientovanie v nej 

Ujistime sa že máme zapnutý MySQL a Apache server

![echo PATH](./images/xampp-control_givBTwII7s.png#center)

Pripojíme sa na databázu ako `root` používateľ

príkaz: `mysql -uroot -p`

![echo PATH](./images/WindowsTerminal_rahEHSu4Pk.png#center)