# PS2Pico-LilyGO-VGA32

Carrier PCB v1.5.5 para usar **ps2pico** con la **LilyGO / FabGL VGA32**, manteniendo el firmware original de No0ne y añadiendo protección de alimentación, desacoplo y una entrada auxiliar USB-C para teclados USB modernos.

> Este repositorio no es un fork del firmware. El firmware original se obtiene de:
> https://github.com/No0ne/ps2pico

## Estado

**Prototipo fabricado y probado con éxito.**

Probado con:
- K-1000 Mini Keyboard USB
- Razer Huntsman V3 X Tenkeyless RGB, con RGB activo y alimentación auxiliar USB-C de 5 V

## Qué añade esta carrier

- PCB dedicada de 98 x 56 mm, 2 capas
- Plano de masa continuo en la cara inferior
- Protección de alimentación mediante dos PPTC
- Aislamiento entre las dos fuentes mediante 1N5817 Schottky
- Entrada auxiliar USB-C de 5 V
- Desacoplo local de 100 nF + 100 µF
- Conexión PS/2 de cuatro señales hacia la VGA32
- Sólo los 8 contactos de la Raspberry Pi Pico necesarios para el circuito

## Alimentación

Desde la VGA32:

```text
+5 V PS/2 -> F1 RXEF040 -> D3 1N5817 -> VBUS
```

Desde la entrada auxiliar:

```text
USB-C AUX -> F2 RXEF040 -> D4 1N5817 -> VBUS
```

Los PPTC realmente montados en el prototipo son **RXEF040: 0,40 A hold / 0,80 A trip**.

> La serigrafía de la PCB indica `0.5A` porque el diseño inicial estaba previsto para PPTC de 500 mA.

## Breakout USB-C probado

Se utilizó la **placa adaptadora USB Type-C Mauser 011-4653**.

La carrier sólo conecta:
- GND
- VBUS

## BOM

| Ref. | Cant. | Componente | Valor / modelo | Referencia |
|---|---:|---|---|---|
| U1 | 1 | Raspberry Pi Pico | RP2040 | Mauser 096-9421 |
| Q1, Q2 | 2 | Transistor NPN | BC547C | Mauser 002-0243 |
| D1, D2 | 2 | Zener | 3,6 V / 0,5 W | Mauser 007-0005 |
| R1, R3 | 2 | Resistencia | 10 kΩ | Mauser 104-6020 |
| R2, R4 | 2 | Resistencia | 2,2 kΩ | Mauser 104-7040 |
| F1, F2 | 2 | PPTC | RXEF040 0,40 A hold / 0,80 A trip | Mauser 095-6016 |
| D3, D4 | 2 | Schottky | 1N5817 | Mauser 007-0384 |
| C1 | 1 | Condensador cerámico | 100 nF / 50 V | Mauser 004-5086 |
| C2 | 1 | Condensador electrolítico | 100 µF / 16 V | Mauser 004-0268 |
| J2 | 1 | Breakout USB-C | Mauser 011-4653 | Mauser 011-4653 |
| — | 1 kit | Headers macho | 2,54 mm | Mauser 096-9615 |
| — | 1 | Cable PS/2 | Mini-DIN 6 macho | Genérico |
| — | 1 | Adaptador OTG | USB-A hembra -> micro-USB B macho | Gembird A-OTG-AFBM-03 probado |

## Pines usados de la Raspberry Pi Pico

| Pin | Función |
|---:|---|
| 18 | GND |
| 19 | GP14 / CLOCK input |
| 20 | GP15 / CLOCK drive |
| 21 | GP16 / DATA drive |
| 22 | GP17 / DATA input |
| 23 | GND |
| 38 | GND |
| 40 | VBUS |

## PS/2

| Pin | Señal |
|---:|---|
| 1 | DATA |
| 2 | NC |
| 3 | GND |
| 4 | +5 V |
| 5 | CLK |
| 6 | NC |

En el cable concreto usado durante las pruebas:
- Rojo = DATA
- Amarillo = GND
- Negro = +5 V
- Azul = CLK

**Los colores no son estándar. Verificar siempre por continuidad.**

## Firmware

No se redistribuye firmware en este repositorio.

Usar el `ps2pico.uf2` original del proyecto de No0ne:
https://github.com/No0ne/ps2pico

## Gerbers

Los Gerbers v1.5.5 usados para fabricar el prototipo están en:

`Gerbers/PS2Pico_LilyGO_Gerbers_v1.5.5_DIY.zip`

## Documentación

- `Documentacion/MONTAJE_ES.md`
- `Documentacion/PINOUT_PS2.md`
- `Documentacion/TESTES_ES.md`
- `Documentacion/AUDITORIA_Y_NOTAS.md`
- `Documentacion/DIAGRAMA_FUNCIONAL.png`
- `Documentacion/BOM_v1.5.5.csv`
- `Documentacion/netlist_pads_v1.5.5.csv`
- `Documentacion/pico_selected_pins.csv`

## Notas de fabricación

Los Gerbers fueron generados mediante herramientas propias y se realizó una auditoría geométrica personalizada. Esto no debe confundirse con un DRC de KiCad o una verificación CAM industrial.

La v1.5.5 incluida aquí fue aceptada por PCBWay, fabricada físicamente, montada y probada.

## Créditos

Proyecto, montaje y pruebas:

**Filipe Silva**

Diseño y desarrollo realizados con asistencia técnica de:

**ChatGPT (OpenAI)**

Circuito base y firmware:

**No0ne / ps2pico**  
https://github.com/No0ne/ps2pico

Esta carrier mantiene el firmware original y amplía la parte hardware para su uso específico con LilyGO/FabGL VGA32.
