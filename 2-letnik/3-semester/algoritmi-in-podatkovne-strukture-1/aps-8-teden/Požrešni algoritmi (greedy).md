[[predavanje-aps-8-teden]]; #aps1-flashcards 

### Problem <font color="#8064a2">bencinskih črpalk:</font>
- imamo tank $T$,
- pot dolžine $K$
- črpalke $N$
- na razdaljah $0<x_1<x_2<...<x_n<K$

![[Požrešni algoritmi (greedy) 2024-11-22 12.28.34.excalidraw]]

Ideja rešitve je to, da pogledaš do kam se lahko pelješ ne da tankaš in se na to ustaviš na zadnji možni črpalki in to ponavljaš dokler ne prideš do konca.

### Problem <font color="#8064a2">izbiranja aktivnosti:</font>
- imamo neke intervale $a_i = (s_i, e_i)$
- kako izbrati čim več aktivnosti, ki jih lahko zberem v urnik

![[Požrešni algoritmi (greedy) 2024-11-22 12.44.13.excalidraw]]

Kako se tega lotit? 
- prva ideja, je to da najprej izberemo najkrajše. ❌
- druga ideja, najzgodnejši interval. ❌
- tretja ideja, najmanj konflikten interval. ❌
- četrta ideja, najzgodnejši konec, $O(n^2) \rightarrow O(n \log n)$. ✅

### Problem <font color="#8064a2">rezervacije učilnic: </font>
- imamo $N$ učilnic, zasedenost teh $p_i = (s_i, e_i)$
- želimo minimalno število predavalnic da izvedemo vse

Ideje:
- potrebujemo najmanj toliko učilnic kolikor je $max$ predavanj naenkrat