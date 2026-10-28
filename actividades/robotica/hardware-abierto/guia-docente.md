# Hardware abierto: guía docente

Se trabaja **por parejas**: una placa, una protoboard, una lupa y un portátil por equipo. Es la misma dotación que las demás actividades con Arduino.

Arduino® es una marca de Arduino S.r.l. Esta actividad no está hecha ni respaldada por Arduino: solo enlaza sus documentos públicos.

## Preparación previa
Tiempo estimado: 20 minutos (más una sesión previa con TI la primera vez).

1. **Una semana antes (solo la primera vez):** pide a TI que instale en los portátiles el entorno de Arduino y, si las placas compatibles lo necesitan, el controlador USB (muchas usan el chip CH340). Si no hay placas o no se puede instalar nada, la prueba se hace en Wokwi desde el navegador, o en SimulIDE si el centro lo ha instalado (funciona sin conexión).
2. **Descarga el esquema oficial** de la placa UNO Rev3 desde su ficha (enlace en «Enlaces»). Tiene dos páginas: la 1 es el circuito y la 2 solo trae la nota de licencia. Imprime la página 1, a ser posible en A3, una por pareja. La página 2 la proyectas o copias su frase en la pizarra: «This project's hardware is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License».
3. **Prepara la ficha de detective** (una por alumno) con esta tabla:

| Pieza | Cómo se llama en el esquema | Qué veo en mi placa (inscripción, sitio) | ¿Igual o distinta? |
|---|---|---|---|
| Microcontrolador | | | |
| Regulador de 5 V | | | |
| LED «L» del pin 13 | | | |
| Pines | | | |

4. **Prueba tú el montaje antes.** Busca tú las cuatro piezas en una placa del aula con la lupa, monta el LED externo y sube el programa de prueba. Tardas 10 minutos y sabrás qué inscripciones tienen vuestras placas, que pueden variar entre lotes.
5. **El día antes:** kit por pareja en una bolsa: placa con cable USB, protoboard, 1 LED, 1 resistencia de 220 Ω, 3 cables y lupa. Guarda el programa de prueba en el escritorio de cada portátil.
6. **Antes de entrar:** comprueba que el vídeo se ve y que Wokwi abre en un portátil (plan B).

## Qué buscar en el esquema
Esto es lo que trae el esquema oficial de la UNO Rev3 (página 1). Las placas compatibles pueden usar piezas con otra referencia que hacen el mismo trabajo: **eso no es un error, es justo lo que permite un diseño abierto.**

- **Microcontrolador (el «cerebro»):** en el esquema pone `ATMEGA328P-PU`. En la placa es el chip más grande. Puede ser alargado con 28 patas (en zócalo) o pequeño y cuadrado soldado sobre la placa. Con la lupa se lee «ATMEGA328P» en su superficie.
- **Regulador de 5 V:** en el esquema es `U1`, con la referencia `NCP1117ST50T3G`, cerca de la entrada de alimentación (`PWRIN`, `VIN`). Convierte la tensión de entrada en 5 V estables. En la placa es una pieza negra de tres patas con una pestaña ancha, cerca del conector redondo. En muchas compatibles lleva otra referencia que también da 5 V.
- **LED «L» del pin 13:** en el esquema es un LED amarillo con la letra `L`. La señal del pin 13 (`L13`) no va directa al LED: pasa por un pequeño amplificador (`LMV358`) que lo enciende sin cargar el pin. En la placa es una lucecita pequeña con una «L» serigrafiada al lado. En algunas compatibles el LED va conectado de otra forma; si lo veis distinto, apuntadlo.
- **Pines:** en el esquema son los conectores `IOL` e `IOH` (pines digitales del 0 al 13), `AD` (A0 a A5) y `POWER` (5V, 3V3, GND, VIN). En la placa son las filas de agujeros negros de los bordes con sus números pintados.
- **Para el reto:** el segundo chip, `ATMEGA16U2-MU`, es el que habla con el ordenador por USB. Muchas compatibles usan otro chip para eso (a menudo CH340), y por eso hay que instalar su controlador.

## Guion
- **Min 0-5 · Enganche.** Proyecta el vídeo. Pregunta: «¿Se puede copiar una placa sin hacer trampa?». Recoge ideas sin corregir.
- **Min 5-15 · Explicación.**
  1. **La receta abierta y la secreta.** «Una receta secreta solo la puede cocinar quien la tiene. Una receta abierta la puede leer, cocinar, cambiar y compartir cualquiera, si dice de quién era.» Pregunta: «¿Qué receta mejora más deprisa con el tiempo?».
  2. **El esquema es la receta de la placa.** Enseña el esquema impreso. Cada dibujo es una pieza y cada línea, un cable. Pregunta: «¿Para qué querría alguien los planos de una placa?» (para aprender, repararla, fabricarla, mejorarla).
  3. **La licencia.** Proyecta la frase de la página 2. «CC BY-SA 4.0 dice dos cosas: BY, di quién lo hizo; SA, si lo cambias, compártelo con la misma licencia.» Por eso existen placas compatibles.
  4. **Trampa: abierto no es gratis.** «Las placas cuestan dinero y su diseño es abierto. Hay juegos gratis cuyo código nadie puede ver. Gratis habla del precio; abierto habla de lo que te dejan hacer.»
- **Min 15-30 · Detectives del esquema.** Por parejas, con el USB **desconectado**: uno lee el esquema y otro busca con la lupa. Rellenan la ficha. A mitad cambian los roles. Pregunta en las mesas: «¿Qué inscripción lee tu lupa? ¿Coincide con el esquema?».
- **Min 30-45 · Prueba de las dos luces.** Montan el LED externo (tabla de «Montaje»), conectan el USB, abren el programa de prueba, eligen la placa «Arduino Uno» y el puerto, y pulsan «Subir». Cuentan cuántas veces se enciende el LED externo en 30 segundos con el cronómetro y lo comparan con otra pareja, con la placa oficial si la hay o con el mismo programa en Wokwi. Pregunta: «Si las placas son de fabricantes distintos, ¿por qué dan los mismos parpadeos?».
- **Min 45-52 · Debate en círculo.** Con el USB desconectado. Lanza estas preguntas, una cada dos minutos:
  1. «¿Qué ganamos todos si los diseños son abiertos?» (aprender, reparar, abaratar, inventar cosas nuevas sobre lo que ya existe).
  2. «Si cualquiera puede fabricar la placa, ¿por qué no puede ponerle el nombre Arduino?» Idea clave: el diseño es abierto, pero el nombre y el logo son una marca registrada. Una compatible puede decir «compatible con Arduino» en su descripción, pero no llamarse Arduino.
  3. «¿Sería justo vender una copia con el logo de Arduino?» (no: engaña al comprador y usa una marca ajena).
- **Min 52-60 · Cierre.** Desconectan el USB. Foto de la placa con el LED (¡sin caras!) al álbum, autoevaluación, un kudo a otra pareja. Recogen todo en la bolsa y cuentas las piezas. Explica el proyecto a casa.

## Montaje
Con el USB **desconectado**. El LED del pin 13 ya está en la placa; solo se añade uno externo en el pin 12.

| Desde | Pasa por | Hasta |
|---|---|---|
| Pin 12 de la placa | Resistencia de 220 Ω | Pata larga (ánodo) del LED |
| Pata corta (cátodo) del LED | Cable | Pin GND de la placa |

## Código de referencia
**Programa de prueba: las dos luces.** El LED «L» de la placa y el LED externo se turnan cada medio segundo.

```cpp
// Hardware abierto: prueba de las dos luces
// Funciona igual en la placa oficial, en una compatible y en el simulador.
const int LED_PLACA = 13;  // el LED «L» que ya viene en la placa
const int LED_FUERA = 12;  // nuestro LED en la protoboard

void setup() {
  pinMode(LED_PLACA, OUTPUT);
  pinMode(LED_FUERA, OUTPUT);
}

void loop() {
  digitalWrite(LED_PLACA, HIGH);  // se enciende el de la placa
  digitalWrite(LED_FUERA, LOW);
  delay(500);                     // medio segundo
  digitalWrite(LED_PLACA, LOW);
  digitalWrite(LED_FUERA, HIGH);  // se enciende el de fuera
  delay(500);
}
```

Cada vuelta de `loop()` dura un segundo, así que en 30 segundos el LED externo se enciende unas 30 veces en cualquier placa. En 6.º, pide que cambien los `500` por otro número y que predigan cuántos parpadeos habrá antes de medir.

## Plan B sin placas
- **Wokwi** (navegador, sin cuenta): proyecto nuevo de Arduino Uno, añade un LED y una resistencia con el botón «+», conéctalos al pin 12 y GND, y pega el código. Los detectives trabajan con el esquema impreso y una placa en la mesa del profe que va pasando por las mesas.
- **SimulIDE** (código abierto, sin conexión): solo si el centro lo ha instalado. Permite montar el mismo circuito con una placa Uno simulada y cargar el programa.
- Un detalle para el debate: Wokwi se usa gratis, pero «gratis» no dice nada de si su código es abierto; SimulIDE publica su código con licencia AGPLv3. Es otro ejemplo de que gratis y abierto son cosas distintas.

## Pregunta de cierre
«Una placa compatible cuesta menos, funciona igual y no se llama Arduino. ¿Ha hecho trampa su fabricante?». Busca la idea de que copiar un diseño abierto respetando la licencia es legítimo, y que lo que no se puede copiar es la marca.
