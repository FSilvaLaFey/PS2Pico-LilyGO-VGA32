# Montaje v1.5.5 — orden recomendado

1. R1/R3 = 10 kΩ; R2/R4 = 2,2 kΩ.
2. D1/D2 = Zener 3,6 V. La banda debe coincidir con la barra de la serigrafía.
3. D3/D4 = 1N5817. La banda debe coincidir con la barra de la serigrafía.
4. C1 = 100 nF, sin polaridad.
5. Q1/Q2 = BC547C, respetando C-B-E.
6. F1/F2 = RXEF040, sin polaridad.
7. C2 = 100 µF / 16 V. Respetar + y -; la franja del cuerpo indica negativo.
8. Headers de la Pico.
9. Breakout USB-C: sólo GND y VBUS.
10. Cable PS/2: DATA / GND / +5V / CLK.
11. Programar la Pico antes del montaje definitivo.
12. Conectar teclado mediante adaptador OTG USB-A hembra -> micro-USB B macho.

### Compatibilidad de la entrada USB-C

El breakout Mauser 011-4653 usado en el montaje incorpora dos resistencias Rd
de 5,1 kΩ: CC1 -> GND y CC2 -> GND (marcado SMD `512`). La carrier sólo conecta
VBUS y GND al breakout; no se deben añadir resistencias Rd externas. Con una
fuente USB-C ↔ USB-C, ésta debe poder proporcionar los 5 V y la corriente
necesaria para el conjunto.



## Orientación de la Pico

La micro-USB de la Pico queda hacia el lado indicado por `PICO USB >` en la serigrafía.

Contactos usados:
18 GND
19 GP14 CLOCK input
20 GP15 CLOCK drive
21 GP16 DATA drive
22 GP17 DATA input
23 GND
38 GND
40 VBUS
