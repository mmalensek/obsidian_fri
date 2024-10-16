[[predavanje-ors-2-teden]]; #ors-flashcards 

V <font color="#92cddc">RAM</font>-u <font color="#92cddc">nastopa</font> samo (kakšno naslovno dekodiranje);; popolno naslovno dekodiranje, ker imamo <font color="#92cddc">zaporedne</font> pomnilniške naslove in <font color="#92cddc">ni aliasov</font>.
<!--SR:!2024-10-26,11,270-->

[[stm32h750_reference_manual.pdf]].

![[pomnilniška slika računalnika STM32H750 2024-10-10 11.41.32.excalidraw]]
Naslovi se razlikujejo v spodnjih 10-ih bitih -> naprava obsega $2^{10}$ besed -> $1K$ besed -> $256$ $32$-bitnih registrov, a v resnici jih je samo deset, ker uporabljamo nepopolno naslovno dekodiranje.