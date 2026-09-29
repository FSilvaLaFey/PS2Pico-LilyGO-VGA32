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

### Limitación de la entrada USB-C

El montaje v1.5.5 se probó con una fuente que ya entrega 5 V. La carrier sólo
usa VBUS y GND del breakout Mauser 011-4653; no incorpora resistencias Rd en
CC1/CC2. Con una fuente USB-C ↔ USB-C pueden ser necesarias dos resistencias
de 5,1 kΩ: CC1 -> GND y CC2 -> GND, o un breakout que ya las incluya. No asumir
compatibilidad universal USB-C ↔ USB-C con esta versión tal como está montada.



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
