# 1. Številski sistemi, binarne predstavitve števil

## Pretvorba med številskimi sistemi
1. **Primer:** desetiško število $149,\!28125_{(10)}$ pretvorimo v dvojiški in šestnajstiški sistem.
   $$
    149,\!28125_{(10)} = 10010101,\!01001_{(2)} =95,\!48_{(16)}
   $$
   Postopek pretvorbe iz desetiškega sistema v dvojiški:
   * Število ločimo na celi in decimalni del. 
   * Najprej pretvorimo celi del števila. To storimo tako, da število zaporedoma celoštevilsko delimo z 2 (če pretvarjamo v dvojiški sistem), dokler ne pridemo do rezultata 0. Vsakič si zabeležimo ostanek pri deljenju. 
   * Ostanke preberemo odspodaj navzgor. Dobljeno zaporedje predstavlja zapis celega dela števila v dvojiškem sistemu. 
   $$
    \begin{aligned}
    &149\div2=74\,, &ost.\, 1\:\!\uparrow\\
    &74\div2=37\,, &ost.\, 0\, \vert\\
    &37\div2=18\,, &ost.\, 1\, \vert\\
    &18\div2=9\,, &ost.\, 0\, \vert\\
    &9\div2=4\,, &ost.\, 1\, \vert\\
    &4\div2=74\,, &ost.\, 0\, \vert\\
    &2\div2=1\,, &ost.\, 0\, \vert\\
    &1\div2=0\,, &ost.\, 1\,  \vert\\
    \end{aligned}
    \\[5pt]
    149_{(10)}= 10010101_{(2)}
   $$
   * Sedaj je na vrsti decimalni del. Tega zaporedoma množimo z 2 dokler ne pridemo do rezultata 1. Na vsakem koraku si posebej zabeležimo celi del števila, ki ga pri računanju v naslednjem koraku zavržemo. 
   * Pri izvajanju zaporednega množenja se lahko zgodi, da nikoli ne pridemo do rezultata 1. V tem primeru ima binarni zapis decimalnega števila neskončno števk, ki pa se ponavljajo na neki točki začnejo ponavljat. 
   * Cele dele dobljene pri množenju sedaj preberemo odzgoraj navzdol. Dobljeno zaporedje predstavlja zapis decimalnega dela števila v dvojiškem sistemu.
   * Celi del in decimalni del sedaj združimo in dobimo končni rezultat
    $$
    \begin{aligned}
    &0,\!28125\times2&=\underline{0},&5625& \vert\\
    &0,\!5625\times2&=\underline{1},&125& \vert\\
    &0,\!25\times2&=\underline{0},&5& \vert\\
    &0,\!5\times2&=\underline{1},&0& \downarrow\\
    \end{aligned}
    \\[5pt]
    0,\!28125_{(10)}= 0,\!01001_{(2)}\\[10pt]
    149,\!28125_{(10)} = 10010101,\!01001_{(2)}
    $$
    Postopek pretvorbe iz desetiškega v šestanjstiški sistem:
     * V šestnajstiškem sistemu uvedemo simbole za števila od 10 - 15:
       | Števke                    |   |   |   |   |   |   |   |   |   |   |    |    |    |    |    |    |
       |---------------------|---|---|---|---|---|---|---|---|---|---|----|----|----|----|----|----|
       | Desetiški zapis     | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
       | Šestnajstiški zapis | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A  | B  | C  | D  | E  | F  |

     * Pri pretvorbi v šestnajstiški sistem je postopek enak kot pri pretvorbi v dvojiškega, le da sedaj delimo/množimo s 16. 
     $$
    \begin{aligned}
    &149\div16=9\,, &ost.\, 5\:\!\uparrow\\
    &9\div16=0\,, &ost.\, 9\, \vert\\
    \end{aligned}
    \\[5pt]
    149_{(10)}= 95_{(16)}\\[10pt]
    \begin{aligned}
    &0,\!28125\times16&=\underline{4},&5& \vert\\
    &0,\!5\times2&=\underline{8},&0& \downarrow\\
    \end{aligned}
    \\[5pt]
    0,\!28125_{(10)}= 0,\!48_{(16)}\\[10pt]
    149,\!28125_{(10)} = 95,\!48_{(16)}
   $$

 2. **Primer**: $2F\!,8_{(16)}$ pretvorimo v desetiški sistem.

    Poljubno število v desetiškem zapisu lahko vedno zapišemo kot vsoto produktov posameznih števk s potencami osnove (10). Potenca osnove pri posamezni števki je odvisna od njenega položaja glede na decimalno vejico. Primer:
    $$
    125,\!15_{(10)}=1\times10^2+2\times10^1+5\times10^0+1\times10^{-1}+5\times10^{-2}
    $$
    Enako lahko naredimo v poljubnem številskem sistemu, le da ustrezno spremenimo osnovo. Če je število zapisano v šestnajstiškem sistemu uporabimo osnovo 16.
    $$
        2F\!,8_{(16)}= 2\times16^1+F\times16^0+8\times16^{-1}
    $$ 
    Sedaj lahko zamenjamo šestnajstiške števke z desetiškimi, poračunamo, in dobimo zapis števila v desetiškem sistemu.
    $$
    2\times16^1+15\times16^0+8\times16^{-1} = 32 + 15 + {1\over2}=47,\!5_{(10)}
    $$

**Naloge**
 1. Naloga

    Pretvorite $100010,\!0110_{(2)}$ v desetiški sistem.

    Rešitev:

    Poslužimo se postopka iz primera 2, pri čemer uporabimo osnovo 2.
    $$
        \begin{aligned}
        1&\times2^5+0\times2^4+0\times2^3+0\times2^2+1\times2^1+0\times2^0 \\
        &+ 0\times2^{-1}+ 1\times2^{-2}+1\times2^{-3}\\
        &= 32 + 2 + {1\over4}+{1\over8} = 34,\!375_{(10)}
        \end{aligned}
    $$

2. Naloga

    Pretvorite $110010101111,\!1111111_{(2)}$ v šestnajstiški sistem.

    Rešitev:

    Pri tej nalogi bi lahko število najprej pretvorili v desetiško in nato v šestnajstiško, vendar obstaja hitrejši način. Lepota šestnajstiškega zapisa in tudi glavni razlog zakaj se uporablja je v tem, da nam ena šestnajstiška števka predstavlja štiri dvojiške. Torej ga lahko uporabimo kot bolj kompakten zapis binarnih števil. 

    Binarno število razsekamo na četvorčke, pri tem pazimo, da vedno začnemo pri decimalni vejici. Če nam števk zmanjka levo in desno stran števila ustrezno dopolnemo z ničlami.
    $$
    \vert1100\vert1010\vert1111\vert,\!\vert\!1111\vert1110|
    $$
    Vsak posamezen četvorček pretvorimo v šestnajstiško števko in jih združimo.
    $$
    \begin{aligned}
    1100 &\rightarrow 1\times2^3+1\times2^2+0\times2^1+0\times2^0 =12_{(10)} = C_{(16)}\\
    1010 &\rightarrow  10_{(10)} = A_{(16)}\\
    1111 &\rightarrow  15_{(10)} = F_{(16)}\\
    1111 &\rightarrow  15_{(10)} = F_{(16)}\\
    1110 &\rightarrow  14_{(10)} = E_{(16)}\\
    \end{aligned}\\[10pt]
    110010101111,\!1111111_{(2)}= C\!AF\!,FE_{(16)}
    $$
#
## Binarne predstavitve celih števil

Pri zapisovanju celih števil v računalniku hitro naletimo na težavo, kako zapisati negativna cela števila, saj računalniki razumejo samo ničle in enice, torej ne moremo kar vriniti znaka '-' spredaj. Poleg tega smo omejeni z velikostjo pomnilniške besede in pomnilnika. Na primerih si poglejmo nekaj najpogostejših formatov zapisa celih števil.

1. **Primer**: celi števili 153_{(10)} in 33_{10} zapišimo v 8-bitni nepredznačeni obliki.
   $$
   \begin{aligned}
   153_{(10)}&= 128+16+8+1 =2^7+2^4+2^3+2^0 \rightarrow10011001\\
   33_{(10)}&= 32+1 = 2^5 + 2^0\rightarrow00100001
   \end{aligned}
   $$
   Komentar:

   Število pretvorimo v binarni zapis in ga, če je to potrebno, dopolnemo z ničlami na levi strani, da dobimo natanko 8 bitov. Pri pretvorbi smo se poslužili hitrega postopka za pretvorbo: poiščemo potence števila 2, ki jih lahko seštejemo, da dobimo naše število. Eksponenti teh potenc nam povedo položaje enic v binarnem zapisu števila. Skrajno desni bit je na položaju 0.

   Tabela potenc števila 2, ki si jih je vredno zapomniti:

    |          |       |       |       |       |       |       |       |       |       |       |        |
    |----------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
    | Potenca  | $2^0$ | $2^1$ | $2^2$ | $2^3$ | $2^4$ | $2^5$ | $2^6$ | $2^7$ | $2^8$ | $2^9$ | $2^{10}$ |
    | Vrednost |   $1$   |   $2$   |   $4$   |   $8$   |   $16$  |   $32$  |   $64$  |  $128$  |  $256$  |  $512$  |  $1024$  |

2. **Primer:** izračunaj desetiško vrednost naslednjih 8-bitnih binarnih predstavitev:

   * $00100001$, nepredznačeno celo število.
  
        Zapis samo pretvorimo v desetiški sistem in dobimo število, ki ga predstavlja.
    $$
    00100001 \rightarrow 2^0+2^5 = 1+ 32 = 33
    $$
    
   * $10011001$, predznak in velikost.

        Najpomembnejši (skrajno levi) bit v zapisu predstavlja predznak števila. Nič pomeni, da je število pozitivno, ena pa, da je število negativno. Preostalih sedem bitov nam da velikost števila.
    $$
        \underline{1}0011001 \rightarrow - (2^0+2^3+2^4) = -(1+ 8 + 16)=-25
    $$
   * $00100001$, predznak in velikost.

    $$
    \underline{0}0100001 \rightarrow +(2^0+2^5) = 1+ 32 =33
    $$
  
   * $01100110$, z odmikom $2^{n-1}$.

        Pri tem zapisu imamo specificiran odmik $2^{n-1}$, ki za 8-bitna števila znaša $2^{8-1}=128$. Da dobimo vrednost, ki jo zapis predstavlja, tega pretvorimo v desetiško število in odštejemo odmik (128).
    $$
        01100110\rightarrow 2 + 4 + 32 + 64 - 128 = 102-128 = -26
    $$
   * $10100000$, z odmikom $2^{n-1}$.
    $$
        10100000\rightarrow 32 + 128 - 128 = 32
    $$

   * $11100111$, dvojiški komplement.

    Pri zapisu v dvojiškem komplementu vrednost dobimo tako, da najprej pogledamo najpomembnejši (skrajno levi) bit. Če je ta enak 0, pomeni, da je število pozitivno. V tem primeru zapis preprosto pretvorimo v desetiški sistem po postopku za nepredznačena števila. Če je najpomembnejši bit enak 1, potem je število negativno in moramo postopati drugače. Vrednost lahko izračunamo na dva načina:

    1. Zapis pretvorimo kot nepredznačeno celo število in odštejemo $2^n= 2^8=256$.
    $$
        11100111\rightarrow 1+2+4+32+64+128-256=231-256=-25
    $$
    2. V zapisu invertiramo vse bite in prištejemo 1. Dobljeni binarni zapis predstavlja velikost števila, ki mu nato dodamo še predznak -.
    $$
    \begin{aligned}
    11100111&\\
    \hline\\[-11pt]
    00011000&\\
    \hline\\[-11pt]
    +1&\\
    \hline\\[-11pt]
    00011001&
    \end{aligned}\\[10pt]
    00011001\rightarrow -(1+8+16)=-25
    $$

   * $00100001$, dvojiški komplement.

    $$
    00100001\rightarrow 1 + 32 = 33
    $$
   
**Naloge**
 1. Naloga
   
    Predpostavite 8-bitno predstavitev celih števil. V vsaki od štirih predstavitev zapišite desetiško vrednost in binarni zapis za: 
    * najmanjše možno število,
    * največje možno število,
    * število nič.


    Rešitev:
    | Predstavitev         | Min                        | Max                       | Nič                    |
    |----------------------|----------------------------|---------------------------|------------------------|
    | Nepredznačeno        | $00000000$                 | $11111111\rightarrow255_{(10)}$ | $00000000$             |
    | Predznak in velikost | $11111111\rightarrow-127_{(10)}$ | $01111111\rightarrow127_{(10)}$  | $00000000$, $10000000$ |
    | Odmik                | $00000000\rightarrow-128_{(10)}$ | $11111111\rightarrow127_{(10)}$  | $10000000$             |
    | Dvojiški komplement  | $10000000\rightarrow-128_{(10)}$  | $01111111\rightarrow127_{(10)}$  | $00000000$             |

 2. Naloga

    Desetiška števila 3, 60, -55, -127 pretvorite v naslednje 8-bitne binarne predstavitve:
    * nepredznačeno celo število,
    * predznak in velikost,
    * odmik,
    * dvojiški komplement.

    Rešitev:

    |         | $3$        | $60$       | $-55$      | $-127$     |
    |----------------------|------------|------------|------------|------------|
    | Nepredznačeno        | $00000011$ | $00111100$ | /          | /          |
    | Predznak in velikost | $00000011$ | $00111100$ | $10110111$ | $11111111$ |
    | Odmik                | $10000011$ | $10111100$ | $01001001$ | $00000001$ |
    | Dvojiški komplement  | $00000011$ | $00111100$ | $11001001$ | $10000001$ |

 3. Naloga

    Število $-1080_{(10)} zapišite v 16-bitni predstavitvi z dvojiškim komplementom v binarnem zapisu, nato pa 16-bitni binarni zapis pretvorite še v šestnajstiški zapis.

    Rešitev:
    $$
    \begin{aligned}
        -1080_{(10)}&=-(1024+32+16+8)\\
        &=-(2^{10}+2^5+2^4+2^3)\rightarrow 0000010000111000
    \end{aligned}\\[10pt]
    \begin{aligned}
    0000010000111000&\\
    \hline\\[-11pt]
    1111101111000111&\\
    \hline\\[-11pt]
    +1&\\
    \hline\\[-11pt]
    1111101111001000&
    \end{aligned}\\[10pt]
    1111|1011|1100|1000\rightarrow F\!BC8_{(16)}
    $$
    Komentar: V literaturi boste pogostokrat opazili, da je šestnajstiškemu zapisu števil dodana predpona $0x$, kar omogoča enostavno ločevanje med desetiškim in šestnajstiškim zapisom. Rešitev zgornje naloge bi torej lahko zapisali kot $0xF\!BC8$.
