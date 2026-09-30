# Notas de auditoría y fabricación — v1.5.5

- Placa: 98 x 56 mm, 2 capas.
- Gerbers generados mediante herramientas propias, no mediante un proyecto KiCad nativo.
- Se realizó una auditoría geométrica personalizada de pads, drills, clearances y plano de masa.
- Esta auditoría NO equivale a KiCad DRC ni a una aprobación CAM industrial.
- Los Gerbers v1.5.5 incluidos fueron aceptados por PCBWay y se fabricaron físicamente.
- El prototipo fabricado fue montado y probado funcionalmente.

## Cambio respecto a la documentación antigua

Durante el diseño, J2 se planteó inicialmente alrededor de un Adafruit ADA4090.
La unidad que finalmente se montó y probó utiliza **Mauser 011-4653**.

La carrier sólo necesita dos puntos de alimentación a 2,54 mm:
- GND
- VBUS

El breakout Mauser 011-4653 incorpora dos resistencias Rd de 5,1 kΩ, entre
CC1/GND y CC2/GND (marcado SMD `512`). Esas resistencias pertenecen al breakout,
no a la carrier; no deben añadirse resistencias Rd externas.

Por ello, la documentación de esta release describe el componente realmente utilizado y no el
ADA4090.

## Nota sobre F1/F2

La serigrafía de la PCB dice 0.5A.
La unidad probada monta RXEF040:
- 0,40 A hold
- 0,80 A trip
