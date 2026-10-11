<p align="center">
  <img src="assets/icon.svg" width="112" height="112" alt="Icono de GR4-XPanUnlock: un paisaje marino al atardecer en un visor abierto, luminoso dentro de una franja 65:24 entre dos líneas blancas y atenuado por encima y por debajo">
</p>

<h1 align="center">GR4-XPanUnlock</h1>

<p align="center">
  <strong>El encuadre panorámico XPan (65:24), dentro de tu RICOH GR IV.</strong>
</p>

<p align="center">
  <a href="README.md">English</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.zh-CN.md">简体中文</a> |
  <a href="README.zh-TW.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <a href="README.de.md">Deutsch</a> |
  <a href="README.fr.md">Français</a> |
  <strong>Español</strong>
</p>

GR4-XPanUnlock añade **XPan**, el encuadre panorámico 65:24 de las clásicas
cámaras panorámicas de 35 mm, a la GR IV como **quinta proporción**, junto a
3:2, 4:3, 1:1 y 16:9. Funciona como una proporción nativa: en la vista en
directo, en el enfoque, en el JPEG guardado, en Revisión instantánea, en
**Revelado RAW** y en **Recorte**.
Todo lo demás de tu cámara queda exactamente como estaba, y puedes volver al
firmware oficial en cualquier momento.

Este repositorio no contiene ningún firmware de RICOH. Tú mismo descargas el
firmware oficial de RICOH, y la herramienta incluida lo convierte en la versión
XPan, en tu propio ordenador.

> [!WARNING]
> **No oficial, bajo tu propia responsabilidad.** No está hecho ni respaldado por RICOH IMAGING.
> Instalar un firmware modificado puede anular la garantía. Lee primero
> [Antes de empezar](#antes-de-empezar) y [Riesgos](#riesgos).

| Quieres | Ve a |
| --- | --- |
| Crear el firmware XPan e instalarlo | [Antes de empezar](#antes-de-empezar) |
| Pasar de 1.x a 2.0.0 | [Actualizar desde 1.x](#actualizar-desde-1x) |
| Volver al firmware de RICOH | [Volver al firmware oficial](#volver-al-firmware-oficial) |
| Saber qué contiene un archivo de firmware | [Comprobar un archivo de firmware](#comprobar-un-archivo-de-firmware) |

**Contenido:**
[Qué obtienes](#qué-obtienes) |
[Antes de empezar](#antes-de-empezar) |
[Crea tu firmware](#crea-tu-firmware) |
[Instálalo en la cámara](#instálalo-en-la-cámara) |
[Novedades de 2.0.0](#novedades-de-200) |
[Conviene saber](#conviene-saber) |
[Riesgos](#riesgos) |
[Cómo funciona](#cómo-funciona) |
[Estado de las pruebas](#estado-de-las-pruebas) |
[Para desarrolladores](#para-desarrolladores)

## Qué obtienes

<p align="center">
  <img src="assets/live-view.svg" width="720" alt="Vista en directo con XPan seleccionado: se ve todo el fotograma 3:2 de un paisaje marino al atardecer; por encima y por debajo de una amplia franja 65:24 está atenuado a la mitad, una fina línea blanca marca cada borde de la franja y el recuadro de enfoque está sobre un cabo dentro de la franja">
  <br>
  <sub>Vista en directo en XPan. Todo el fotograma sigue visible; lo que queda entre las líneas es la foto.</sub>
</p>

En el ajuste de formato de imagen (menú, ADJ y el atajo Fn/dial), **XPan
aparece después de 16:9**, con su propia etiqueta "XPan" (en todos los idiomas
del menú) y su propio icono. El atajo recorre 3:2 → 4:3 → 1:1 → 16:9 → XPan.

| Recorte / tamaño | Tamaño de imagen XPan |
| --- | --- |
| Fotograma completo (28 mm), L | 6192 × 2288 |
| Recorte de 35 mm (Recortar), o tamaño M | 4944 × 1824 |
| Recorte de 50 mm (Recortar), o tamaño S | 3504 × 1296 |
| Tamaño XS | 1920 × 712 |

- **La vista en directo** muestra todo el fotograma, como el visor abierto de una
  cámara telemétrica. Fuera del recorte, la escena se atenúa a la mitad, con una
  fina línea blanca en cada borde del recorte, para que veas lo que está a punto
  de entrar en la foto. Todo lo que queda entre las líneas es lo que contiene la
  foto. **16:9, 4:3 y 1:1** funcionan igual. Los iconos de estado quedan por
  encima de la zona atenuada. 3:2 no cambia.
- **El enfoque** se queda dentro de la foto: el recuadro de enfoque se puede
  colocar en cualquier punto dentro de los límites de enfoque de la cámara y del
  recorte, hasta las mismas líneas, pero nunca en la zona atenuada (con los
  botones o al tocar). AF área automática cubre toda la franja XPan.
- **Revisión instantánea** muestra la foto que acabas de hacer en su encuadre
  XPan.
- **Los archivos RAW (DNG)** conservan la imagen completa del sensor, exactamente
  como con las proporciones nativas. Su información de recorte marca el encuadre
  XPan, así que los programas de revelado RAW los abren en XPan, y aún puedes
  ampliar el recorte más adelante.
- **Revelado RAW** en la cámara: un RAW 3:2 se puede revelar a 3:2, 4:3, 1:1,
  16:9 o XPan; un RAW 16:9 o XPan, a 16:9 o XPan.
- **Recorte** (recortar JPEG en la propia cámara, en reproducción) ofrece
  encuadres XPan, de 6192 × 2288 a 1920 × 712, junto a los encuadres 16:9.
- La indicación del tamaño de imagen en el menú muestra el tamaño XPan.
- Las fotos en 3:2, 4:3, 1:1 y 16:9, la reproducción y la grabación de vídeo no
  cambian.

## Antes de empezar

- **Cámara:** RICOH GR IV (el modelo en color estándar). Otros modelos no son
  compatibles.
- **Tu cámara ya debe tener el firmware 1.11.** Comprueba la versión en el menú
  de configuración de la cámara.
  - Versión anterior: actualiza primero a la 1.11 de la forma normal, con el archivo oficial de RICOH.
  - Versión más reciente: **no uses esta herramienta.** Solo es compatible con la 1.11.
- **El archivo de firmware oficial.** En la página oficial de soporte de la GR IV
  de RICOH IMAGING, descarga la **versión de firmware 1.11**. Descomprímela si hace
  falta hasta tener el archivo **`fwdc248b.bin`**.
- **Una batería totalmente cargada.** Una actualización de firmware nunca debe
  quedarse sin alimentación.
- **Una tarjeta SD** que puedas formatear.
- **Un ordenador con Python 3.8 o posterior.** macOS y la mayoría de los sistemas
  Linux ya lo tienen; en Windows, instálalo desde python.org. No hace falta nada
  más.
- Apunta los ajustes personalizados (C1, C2, …) que no quieras tener que volver a configurar.

## Crea tu firmware

Abre un terminal en esta carpeta y ejecuta (usa la ruta donde guardaste el
archivo oficial):

```sh
python3 gr4_xpanunlock.py patch ~/Downloads/fwdc248b.bin
```

En Windows:

```bat
py gr4_xpanunlock.py patch C:\Users\you\Downloads\fwdc248b.bin
```

La herramienta comprueba primero que le has dado el archivo oficial 1.11
auténtico, después crea el firmware XPan y lo comprueba. Cuando todo está bien,
termina así:

```
wrote output/fwdc248b.bin  (SHA-256 aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0)
```

Si algo no está bien (por ejemplo, otra versión de firmware, un archivo ya
modificado o una descarga dañada), muestra `refused: …` y **no escribe nada**.

## Instálalo en la cámara

### 1. Cópialo a la tarjeta SD

1. **Formatea la tarjeta SD en la cámara.**
2. Copia **`output/fwdc248b.bin`** en la **raíz** de la tarjeta: no dentro de una
   carpeta, y con el nombre exactamente `fwdc248b.bin`.

### 2. Actualiza la cámara

1. Inserta la batería totalmente cargada y la tarjeta SD.
2. Inicia la actualización de firmware desde el menú de configuración de la cámara,
   como se describe en las instrucciones oficiales de RICOH para actualizar el firmware de la GR IV.
3. **La cámara muestra una actualización de la versión 1.11 a la versión 1.11.** Es
   lo esperado: el firmware XPan mantiene el número de versión. Confirma la actualización.

> [!CAUTION]
> **No apagues la cámara, no abras la tapa de la batería o de la tarjeta y no
> saques la tarjeta** hasta que la actualización haya terminado y la cámara se haya reiniciado.

### 3. A disparar

- Ajusta el formato de imagen a **XPan** (después de 16:9).
- La versión del firmware sigue mostrando **1.11**. Es normal.
- Borra `fwdc248b.bin` de la tarjeta (o formatéala) para que la actualización no
  se inicie de nuevo por error.

### Volver al firmware oficial

> [!IMPORTANT]
> **Primero ajusta el formato de imagen a cualquier opción distinta de XPan**,
> por ejemplo 3:2, y haz lo mismo en cada modo personalizado (C1, C2, …) que use
> XPan. El firmware oficial no tiene el ajuste XPan.

Después repite los pasos 1–2 con el `fwdc248b.bin` **oficial** de RICOH. La
cámara vuelve a mostrar **1.11 → 1.11**; confírmalo y tu cámara vuelve a su
estado original.

## Novedades de 2.0.0

- **Vuelve 16:9.** XPan es ahora una proporción adicional en lugar de un
  reemplazo, así que puedes disparar en 16:9 y en XPan con el mismo firmware.
- **Cada uno tiene su propio icono.** 16:9 vuelve a mostrar su icono original;
  XPan tiene su propio icono "XPan" en todos los lugares donde aparece.
- **Revelado RAW** ofrece XPan como opción propia, junto a 16:9.
- **Recorte** (recortar en reproducción) ofrece XPan como proporción propia,
  junto a 16:9.
- **Revisión instantánea** muestra una foto XPan en su encuadre XPan.
- Las fotos 16:9 antiguas de la tarjeta vuelven a reconocerse como 16:9.

### Actualizar desde 1.x

Crea el archivo 2.0.0 a partir del `fwdc248b.bin` **oficial** de RICOH,
exactamente como en [Crea tu firmware](#crea-tu-firmware), e instálalo de la
misma manera. No hace falta volver antes al firmware oficial. La herramienta
rechaza un archivo XPan 1.x como entrada, así que parte siempre del archivo de
RICOH.

Después de la actualización, una cámara que estaba ajustada a XPan en 1.x
muestra **16:9**, porque la 1.x ponía XPan en lugar de 16:9. Vuelve a
seleccionar **XPan** (también en C1, C2, … si lo guardaste ahí).

## Conviene saber

- **La cámara trata las fotos XPan como 16:9 en algunos sitios:**
  - Revelado RAW de un RAW XPan empieza en 16:9; selecciona XPan.
  - La edición en reproducción distinta de Recorte (por ejemplo, Redimensionar)
    no se ha probado específicamente con fotos XPan.
  - La medición de la exposición y del balance de blancos de una foto XPan
    abarca la zona 16:9 que la rodea. En la práctica, la diferencia es pequeña.
- **El enfoque MF y Snap** mantiene su zona de enfoque fija, que puede
  extenderse sobre la zona atenuada. Esto no afecta a dónde enfoca la cámara en
  esos modos.
- **El brillo de la vista en directo** se mide en todo el fotograma y no solo en
  el recorte, así que con un cielo muy luminoso u oscuro fuera de la franja, la
  exposición puede diferir un poco de lo que esperas.
- **Detección de rostro/ojos** no se ha probado específicamente en XPan.
- **GR4-MonoUnlock y GR4-XPanUnlock no se pueden instalar juntos.** Cada
  herramienta parte del firmware oficial, y esta herramienta rechaza un archivo
  de MonoUnlock.
- **Una actualización oficial de RICOH elimina XPan.** Reemplaza todo el
  firmware. Ajusta antes una proporción distinta de XPan (consulta
  [Volver](#volver-al-firmware-oficial)). Esta herramienta solo es compatible
  con la 1.11; no la uses con otra versión.
- **Solo para la GR IV estándar.** Nunca instales el archivo en otro modelo.
- **Antes de enviar la cámara al servicio técnico,** vuelve al firmware oficial.

### Comprobar un archivo de firmware

Antes de copiar cualquier archivo de firmware a una tarjeta:

```sh
python3 gr4_xpanunlock.py check path/to/fwdc248b.bin
```

Te dice si el archivo es el 1.11 oficial, la versión XPan creada por esta
herramienta (2.0.0, o una 1.x anterior) u otra cosa.

## Riesgos

- Tu cámara no puede distinguir un archivo de firmware bueno de uno dañado. Copia a
  tu tarjeta solo un archivo que haya escrito la herramienta (o que hayas confirmado con `check`).
- Si una actualización se interrumpe, o un archivo de firmware no puede arrancar, puede
  que la cámara ya no llegue a la función de actualización, y entonces necesitaría el
  servicio técnico de RICOH. No ocurrió en las pruebas, pero no se puede descartar.
- Volver al firmware oficial con XPan todavía seleccionado no se ha probado.
  Ajusta antes otra proporción.
- Los datos de calibración propios de tu cámara no se tocan.

## Cómo funciona

Los menús de la GR IV, el procesado de las fotos, la vista en directo, Revelado
RAW y Recorte están construidos en torno a cuatro proporciones. La herramienta
añade XPan como quinta, que la cámara trata como un pariente cercano de 16:9.
Allí donde se decide la forma de una foto (tamaño de imagen, recorte RAW, vista
previa, Revisión instantánea, límites de enfoque, marcas de la vista en directo,
encuadres de Recorte), XPan recibe sus propios valores, y las demás proporciones
quedan exactamente como estaban.

## Estado de las pruebas

| Qué | Estado |
| --- | --- |
| Actualización aceptada, la cámara arranca | probado en una GR IV 1.11 |
| Menú de cinco proporciones, etiqueta e icono XPan, 16:9 con su propio icono | probado en una GR IV 1.11 |
| Fotos 16:9 y XPan guardadas en sus propios tamaños, también después de cambiar entre ellas | probado en una GR IV 1.11 |
| Revisión instantánea en el encuadre XPan | probado en una GR IV 1.11 |
| Revelado RAW con XPan y 16:9 | probado en una GR IV 1.11 |
| Recorte (recortar en reproducción) con XPan y 16:9 | probado en una GR IV 1.11 |
| Vista en directo de fotograma abierto con marcas de recorte; iconos de estado legibles encima | probado en una GR IV 1.11 |
| Sin marcas en reproducción; vista en directo en 3:2 sin cambios | probado en una GR IV 1.11 |
| Enfoque limitado al recorte, hasta las líneas del borde | probado en una GR IV 1.11 |
| Pauta cuadrícula activada y desactivada con las marcas de recorte | aún no probado; por favor, comunica tus resultados |
| Los tamaños de los JPEG y DNG guardados coinciden con la tabla de arriba | comprobado sin la cámara; por favor, comunica tus resultados |
| Volver al 1.11 oficial restablece la cámara por completo | probado desde 1.x en una GR IV 1.11; desde 2.0.0 aún no probado |
| La herramienta reproduce exactamente el firmware probado | probado |

## Para desarrolladores

```
GR4-XPanUnlock/
├── README.md            this guide
├── README.*.md          this guide in Japanese, Chinese, Korean, German, French and Spanish
├── gr4_xpanunlock.py    the tool
└── assets/
    ├── icon.svg         project icon
    ├── icon-512.png     project icon, 512 × 512 PNG
    └── live-view.svg    the live-view picture in this guide
```

| Archivo | SHA-256 |
| --- | --- |
| `fwdc248b.bin` oficial de RICOH GR IV 1.11 | `a2f664dfca034059eb0fd6e18ab08684c326b4a034d85c164dad7e1ec9b5655f` |
| `fwdc248b.bin` XPan creado por esta herramienta (2.0.0) | `aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0` |
| `fwdc248b.bin` XPan creado por 1.1.0 (16:9 sustituido por XPan) | `4534d44297b69bb6d305bac2ad62fef98b0caf7a6558d6da36c049dbb88f80c8` |
| `fwdc248b.bin` XPan creado por 1.0.0 (16:9 sustituido, vista en directo con franjas negras) | `fa2c67d1b67e16675a0c75b98d58c519b803f049a00e40e34103e54ca9a6a6c7` |
