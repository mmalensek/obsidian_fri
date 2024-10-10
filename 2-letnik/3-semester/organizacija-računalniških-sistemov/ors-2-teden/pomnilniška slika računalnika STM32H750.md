[[predavanje-ors-2-teden]]; #ors-flashcards 

V RAM-u nastopa samo popolno naslovno dekodiranje, ker imamo zaporedne pomnilniške naslove in ni aliasov.

[[stm32h750_reference_manual.pdf]].

![[pomnilniška slika računalnika STM32H750 2024-10-10 11.41.32.excalidraw]]
Naslovi se razlikujejo v spodnjih 10-ih bitih -> naprava obsega $2^{10}$ besed -> $1K$ besed -> $256$ $32$-bitnih registrov, a v resnici jih je samo deset, ker uporabljamo nepopolno naslovno dekodiranje.