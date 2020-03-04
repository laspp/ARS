# 2. Seštevanje celih števil, Zapis v plavajoči vejici

## Seštevanje celih števil



* ### Prenos in pravilnost rezultata pri seštevanju **nepredznačenih števil**

    Pravilnost rezultata pri seštevanju nepredznačenih števil določa prenos na zadnjem bitu $C_{MSB}$. Če je prenos na zadnjem bitu $C_{MSB}$, enak 0, rezulat je pravilen. Če je prenos enak $C_{MSB}$ rezultat je nepravilen. Nepravilnost rezultata pomeni da je prišlo do preliva (ang. *overflow*), oziroma rezultat se ne da predstaviti s porabljenim številom bitov. Torej:

    $$
   
    C_{MSB} = 
    \left\{\begin{matrix}
    0, &    Rezultat \: seštevanja \: je \:pravilen\\ 
    1, &    Rezultat \: seštevanja \: ni \: pravilen
    \end{matrix}\right. \quad,

    $$

    * **Primer**: Opazujte prenos pri seštevanju 190 in 70 :


        Najprej pretvorimo števili v dvojiški sistem:

        $$
        \begin{aligned}
        190_{(10)}=128+32+16+8+4+2 \rightarrow 1011\:1110_{(2)}     
        \end{aligned} \\
        \begin{aligned}
        70_{(10)}=64+4+2 \rightarrow 0100\:0110_{(2)}     
        \end{aligned}
        $$ 

        Seštejemo binarni števili po modulu 2 (1+1 = 0 -> prenos v naslednji bit enak 1)
        $$
        \begin{aligned}
        1011\:1110&\\
        +\quad 0100\:0110&\\
        \hline\\[-3pt]
        C_{MSB}=1\quad 0000\:0010&
        \end{aligned}\\[10pt]
         $$

        $C_{MSB}$ je enak 1, torej rezultat  ni pravilen.      
* ### Prenos in pravilnost rezultata pri seštevanju **predznačenih števil**

    Veljavnost rezultat pri seštevanju predznačenih števil določa bit preliva $V$. Če sta oba znaka seštevancev enaka in je znak rezultata različen potem je $V$ enak 1 ter je rezultat nepravilen. Drugače pa je $V=0$ in je rezultat pravilen. Lahko to predstavimo z naslednjo tabelo : 

    
    |  op1 | op2 |   rez    |$V$| 
    |------|-----|----------|---|
    |   +  |    -|  + ali - | 0 |           
    |   -  |    +|  + ali - | 0 | 
    |   +  |    +|    +     | 0 | 
    |   +  |    +|    -     | 1 | 
    |   -  |    -|    -     | 0 | 
    |   -  |    -|    +     | 0 | 

    $$
   
    V = 
    \left\{\begin{matrix}
    0, &    Rezultat \: seštevanja \: pravilen\\ 
    1, &    Rezultat \: seštevanja \: ni \: pravilen
    \end{matrix}\right. \quad,

    $$

    * **Primer**: Opazujte prenos pri seštevanju 123 in (-123) :
  
        Pretvorba v dvojiški sistem (Drugi komplement):

        $$
        \begin{aligned}
        124_{(10)} \rightarrow 0111\:1100_{(2)}     
        \end{aligned} \\
        \begin{aligned}
        -123_{(10)} \rightarrow 1000\:0101_{(2)}     
        \end{aligned}
        $$ 

        Seštejemo po modulu 2 

        $$
        \begin{aligned}
        0111\:1100&\\
        +\quad 1000\:0101&\\
        \hline\\[-3pt]
        C_{MSB}=1\quad 0000\:0001&
        \end{aligned}\\[10pt]
         $$

        Seštevanci sta pozitivna in je rezultat pozitivan -> $V=0$ -> Rezultat je pravilen čeprav je $C_{MSB} = 1$. Pri seštevanju predznačenih števil upoštevamo samo bit preliva $V$.

    * **Primer**: Opazujte prenos pri seštevanju -80 in (-60) :

        Pretvorba v dvojiški sistem (Drugi komplement):

        $$
        \begin{aligned}
        -80_{(10)} \rightarrow 1011\:0000_{(2)}     
        \end{aligned} \\
        \begin{aligned}
        -60_{(10)} \rightarrow 1100\:0100_{(2)}     
        \end{aligned}
        $$ 

        Seštejemo po modulu 2 

        $$
        \begin{aligned}
        1011\:0000&\\
        +\quad 1100\:0100&\\
        \hline\\[-3pt]
        C_{MSB}=1\quad 0111\:0100&
        \end{aligned}\\[10pt]
         $$

        Seštevanci sta pozitivna in je rezultat negativen -> $V=1$ -> Rezultat je nepravilen.

## Zapis realnih števil v plavajoči vejici

Zapis v plavajoči vejici ali IEEE 754 zapis porabljamo za predstavitvo realnih števil v računalniku. Obstajajo več vrst zapisa v plavajoči vejici. Najpogostojše se uporabljata dva zapisa: 

- IEEE 754 z enojno natančnosti:

  1. Znak - 1 bit 
  2. Eksponent - 8 bitov
  3. Mantisa ali vzlomljeni del - 23 bitov


<p align="center">
    <img  src="./figures/IEEE-754-single1.svg" width="500">
</p>

- IEEE 754 z dvojno natančnosti:

  1. Znak - 1 bit 
  2. Eksponent - 11 bitov
  3. Mantisa ali vzlomljeni del - 52 bitov


<p align="center">
    <img  src="./figures/IEEE-754-double1.svg" width="1000">
</p>


  * Primer: Število –210,5937510 najprej zapišimo v binarni
obliki s plavajočo vejico, nato pa še šestnajstiško v
prestavitvi IEEE 754 z enojno natančnostjo.


    $$
    \begin{aligned}
    –210,5937510_{(10)} \rightarrow ?_{(IEEE 754 \: z \: enojno \: natančnosti)}     
    \end{aligned} \\
    $$ 

    Postopek:

    1. Pretvorba v **dvojiški sistem**:
        $$
            \begin{aligned}
             –210,5937510_{(10)} \rightarrow -1101\:0010,1001\:1_{(2)}     
            \end{aligned} \\
        $$    

         To ni IEEE 754 zapis !!!!
    2. Normalizacija -> Pretvorimo v  zapis ($1.m\cdot2^e$)
        $$
            \begin{aligned}
             -1101\:0010,1001\:1 = - 1.1010\:0101\:0011 \cdot 2^{7}    
            \end{aligned} \\
        $$    

        pri čemu:
         - $m = 1010\:0101\:0011$, 
         - $e = 7$

    3. Zapis v IEEE 754 z enojno natačnosti
        - Predznak: Število negativno $\rightarrow$ $s = 1_{(2)}$ 
        - Eksponent: $E = e + 127 = 134_{(10)} \rightarrow 1000\:0110_{(2)}$
        - Mantisa: $m = 1010\:0101\:0011\:0000\:0000\:000_{(2)}$
  
    4. Rešitev:

       $1 \:  1000\:0110 1010\:0101\:0011\:0000\:0000\:000_{IEEE754} =0\texttt{x}C352\:9800_{IEEE754}$  

  * Primer: Število $0\texttt{x}BF580000$ je zapisano v IEEE 754 z enojno
natančnostjo. Zapišimo desetiško vrednost.

    $$
    \begin{aligned}
    0\texttt{x}BF580000_{(IEEE 754 \: z \: enojno \: natančnosti)}     
    \end{aligned} \rightarrow ?_{(10)} \\
    $$    

    Zapišimo podano število v binarnom sistemu:

    $$0\texttt{x}BF580000 = \underbrace{1}_{Predznak}\overbrace{011\:1111\:0}^{Eksponent}\underbrace{101\:1000\:0000 \cdot  \cdot  \cdot 0}_{Mantisa}$$

    1. 