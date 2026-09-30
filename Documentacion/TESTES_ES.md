# Lista de comprobaciones eléctricas

Realizar con la Pico retirada y sin alimentación, salvo cuando se indique lo contrario.

## 1. Cortos principales

- GND <-> pin 40 (VBUS): no debe haber continuidad permanente.
- GND <-> VBUS del breakout USB-C: no debe haber continuidad permanente.
- GND <-> +5 V PS/2: no debe haber continuidad permanente.
- Un pitido breve que desaparece puede deberse a la carga de C2.

## 2. Masas de la Pico

Debe haber continuidad:
- GND <-> pin 18
- GND <-> pin 23
- GND <-> pin 38

No debe haber continuidad directa a GND:
- pins 19, 20, 21, 22, 40

## 3. Resistencias

Medición directa:
- R1 ~ 10 kΩ
- R3 ~ 10 kΩ
- R2 ~ 2,2 kΩ
- R4 ~ 2,2 kΩ

Rutas:
- CLK -> pin 19 ~ 10 kΩ
- DATA -> pin 22 ~ 10 kΩ
- pin 20 -> base Q1 ~ 2,2 kΩ
- pin 21 -> base Q2 ~ 2,2 kΩ

## 4. Continuidad de señales

- CLK <-> colector Q1
- DATA <-> colector Q2
- emisor Q1 <-> GND
- emisor Q2 <-> GND

## 5. D3 / D4 en modo diodo

Sentido directo:
- punta roja en ánodo / lado sin banda
- punta negra en cátodo / lado con banda

Unidad probada:
- D3: ~0,176 V
- D4: ~0,178 V

Sentido inverso:
- OL

Ruta completa USB-C AUX -> pin 40:
- ~0,172 V en modo diodo en la unidad probada.

## 6. Alimentación auxiliar real

Con Pico retirada:
- aplicar 5 V al USB-C AUX
- comprobar aproximadamente 5 V en VBUS del breakout
- comprobar alimentación después de F2
- comprobar VBUS en el pin 40 después de D4

Nota para una fuente USB-C ↔ USB-C: el breakout Mauser 011-4653 usado incorpora
dos resistencias Rd de 5,1 kΩ: CC1 -> GND y CC2 -> GND (marcado SMD `512`). La
carrier sólo conecta VBUS y GND al breakout; no se deben añadir resistencias Rd
externas. Si no aparecen 5 V en VBUS, comprobar la fuente, el cable y que el
breakout montado sea el 011-4653 con esas resistencias.



### Backfeed hacia PS/2

En circuito abierto puede medirse tensión fantasma en el pad +5 V PS/2 debido a la alta
impedancia del multímetro.

En la unidad probada, colocando temporalmente una resistencia de 2,2 kΩ entre +5 V PS/2 y GND,
esa tensión cayó a ~0 V. Esto confirmó que no existía una alimentación útil hacia atrás.

## 7. Tras instalar la Pico

Repetir como mínimo:
- GND <-> 18 / 23 / 38
- ausencia de corto permanente entre VBUS y GND
- tensión correcta en VBUS
