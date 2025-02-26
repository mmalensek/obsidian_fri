ponovi še entropijo
### Kviz 1, 7. naloga:
![[predavanje-tis-2-teden 2025-02-26 11.22.18.excalidraw]]

### Kodi
Imamo abecedo vira (izvorna abeceda) npr. $A = \{a_1, ..., a_n\}$
Abecede koda $B = \{b_1, ..., b_r\}$, tipično je to $\{0, 1\}$

Kod je preslikava iz abecede vira v abecedo koda: $a_i \rightarrow b_jb_n$, ker imamo manj znakov abecede koda. Zaporedju znakov abecede koda imenujemo <font color="#4bacc6">kodna abeseda</font> (zamenjava). 
### Npr. morsejeva abeceda, morsejev kod.

![[predavanje-tis-2-teden 2025-02-26 11.35.58.excalidraw|200]]
Bolj pogosto uporabljene črke, imajo krajšo kodo, ...

### ASCII kod
$A \rightarrow 1000001$
$a \rightarrow 1100001$
$0 \rightarrow 0110000$
...

### Lastnosti kodov
Upoštevamo povprečno dolžino kodne besede, ki jo izračunamo če imamo:
- $A = \{a_1, ..., a_n\}$
- $P_A = \{p_1, ..., p_n\}$
- $L_A = \{l_1, ..., l_n\}$

$L = \Sigma p_i \cdot l_i$, kjer je pogoj da je $\Sigma p_i = 1$.  

Kaj je idealni kod? če je $L = H(A$

