---
title: PolyField & Track Display — Manual
description: Ayuda y manual de usuario de PolyField & Track Display — software de visualización y presentación de resultados para los sistemas de foto-finish FinishLynx y TimeTronics.
lang: es
permalink: /es/
---

# PolyField & Track Display

Un software de visualización y presentación de resultados para los sistemas de foto-finish FinishLynx y TimeTronics. Funciona en Windows y Mac como una aplicación de escritorio vinculada a su carpeta de resultados de foto-finish.

[Descargar desde polyfield.co.uk](https://www.polyfield.co.uk)

* Contenido
{:toc}

## Descripción general

PolyField & Track Display convierte sus resultados de FinishLynx o TimeTronics en pantallas en directo por todo su recinto. Una sola instancia de escritorio vigila su carpeta de resultados y sirve una interfaz web que cualquier dispositivo de la red puede abrir — marcadores, un quiosco de autoservicio para atletas, un panel de velocidades y mucho más.

El software mantiene al **operador al mando**: los resultados solo aparecen una vez guardados, garantizando una validación positiva antes de mostrarlos. Se admiten guardados múltiples — así puede mostrar pronto a los atletas de fondo, o revelar una carrera una vez asignadas las marcas de los tres primeros.

## Cómo funciona

- Ejecuta **una sola instancia** de la aplicación de escritorio en un ordenador conectado a su carpeta de resultados de foto-finish.
- La aplicación crea una interfaz web en el **puerto 3000**. Cualquier dispositivo de la misma red la abre en un navegador — sin necesidad de instalar nada en las pantallas.
- Cada pantalla se registra a sí misma y se le puede asignar un diseño para mostrar. El número de pantallas solo está limitado por su red y el ordenador anfitrión.
- El operador controla lo que aparece — resultados, superposiciones (texto, salvapantallas, cuenta atrás, récords, vista de línea) o un diseño personalizado completo.

## Primeros pasos

### 1. Definir la carpeta de resultados

Es la carpeta donde FinishLynx o TimeTronics guarda los resultados (LIF, etc.). Haga clic en el botón rojo de la esquina superior derecha, **«Seleccionar carpeta de resultados»**. Podrá cambiarla más tarde con **«Cambiar carpeta»**.

![Defina la carpeta de resultados o modifique la ruta en la esquina superior derecha:]({{ '/assets/desktop.png' | relative_url }})

Una vez definida, la interfaz web se crea y la dirección de acceso se muestra en la parte superior de la aplicación de escritorio (p. ej. `http://display.local:3000` o `http://<su-IP>:3000`).

### 2. Abrir una pantalla

En cada dispositivo de pantalla, abra un navegador y vaya a la dirección indicada, luego `/display`. Cada pantalla que se conecta recibe un número automáticamente. Consulte [Conexión de pantallas](#connecting-screens) para el atajo por código QR.

> **Consejo** — deje la aplicación de escritorio en su pantalla de inicio y controle las pantallas desde ahí, o desde un segundo dispositivo a través de la interfaz web. Así mantiene el control de las superposiciones mientras los resultados fluyen automáticamente.

## El panel de control de escritorio

El panel de control es el puesto del operador. En la parte superior se define la carpeta de resultados y se ve la dirección de conexión. Los controles principales se agrupan en una fila de botones compacta (que pasa a una segunda fila en ventanas estrechas):

| Control | Qué hace |
|---|---|
| **Texto y salvapantallas** | Escribir un mensaje para mostrar en todas las pantallas, o vincular una imagen. Ideal para mensajes de patrocinadores, «reunión suspendida», etc. |
| **Salvapantallas** | Mostrar una **imagen** vinculada o un **diseño guardado** en el área del salvapantallas. Si ya hay una fuente definida, una pulsación lo activa/desactiva; el botón ⚙ vuelve a abrir las opciones. |
| **Vista de línea** | Enviar la última imagen de foto-finish a las pantallas. Atenuado hasta que aparezcan imágenes JPG de foto-finish en la carpeta de resultados. |
| **Reloj** | Mostrar el reloj en marcha a pantalla completa en las pantallas con un widget de reloj. |
| **Probar / Podio / Selección manual** | Aparecen cuando un diseño usa momentos: reproducir una tarjeta de ejemplo en todas las pantallas, mostrar el podio del resultado actual o enviar un récord elegido. Véase [Momentos](#moments). |
| **Cuenta atrás** | Cuenta atrás hasta una hora objetivo. Introduzca la hora e Iniciar; se oculta a cero. |
| **Constructor de diseños** | Abrir el diseñador de diseños (véase más abajo). |
| **Explorar LIF** | Volver a mostrar cualquier resultado anterior de la carpeta supervisada. Su primera opción, **En blanco**, borra el resultado de todas las pantallas. |

## Superposiciones

Las superposiciones son lo que se muestra **encima** (o en lugar) de los resultados: texto, salvapantallas, vista de línea, reloj, récords y cuenta atrás. Tres puntos importantes sobre su funcionamiento:

- **Puede activar varias a la vez.** Por ejemplo un fondo de salvapantallas con una cuenta atrás y un banner de texto encima. Activar una ya no desactiva las demás.
- **Los widgets deciden qué se muestra y dónde.** Cada pantalla solo muestra las superposiciones que contiene su diseño asignado — así, distintas pantallas pueden mostrar distintas combinaciones desde un solo escritorio.
- **Un nuevo resultado las borra todas** y devuelve cada pantalla a los resultados — de modo que los resultados en directo siempre tienen prioridad.

### Salvapantallas (imagen o diseño)

Elija **Imagen** (una imagen vinculada — paneles de patrocinadores, avisos) o **Diseño** (cualquier diseño guardado mostrado como toma total del área del salvapantallas). Seleccione la fuente y pulse **Mostrar**. Una vez definida una fuente, el botón Salvapantallas la activa directamente.

### Cuenta atrás

Cuenta atrás hasta una **hora objetivo**, leída del reloj propio de cada pantalla. Introduzca la hora (p. ej. 15:40) e Iniciar. En el Constructor de diseños puede definir el rótulo (por defecto «Next Event In:»), si se muestran los segundos, y el texto, la fuente y el color. Se oculta a cero y cede el paso a los nuevos resultados y a otras superposiciones.

### Récords

Los récords ahora se muestran como [momentos](#moments). Marque el récord de un atleta en el campo User 3 de FinishLynx (p. ej. `PB` o `W50 WR`) y cada pantalla que usa momentos mostrará una tarjeta de récord al guardarse el resultado. Para un récord que FinishLynx no marcó, pulse **Selección manual** en la ventana principal: 1. elija la carrera, 2. elija la marca, 3. elija o escriba el tipo de récord.

![Selección manual de récords:](assets/records.png)

### Vista de línea

Envía la última imagen de foto-finish a las pantallas con un widget de vista de línea. El control Rotación (s) define cada cuánto alterna la foto con el resultado.

## Tamaño del texto y modos de rotación

El tamaño del texto de resultados por defecto se ajusta con los botones **+** y **−** (los widgets de diseño tienen su propio Tamaño del texto en el Constructor de diseños).

El modo de rotación determina cómo se muestran los resultados con más de 8 competidores:

| Modo | Comportamiento |
|---|---|
| **Desplazar** | Las 3 primeras filas quedan fijas; las filas 4+ se desplazan por los demás competidores. |
| **Página** | Pagina: 1–8, luego 9–16, etc. en la rotación. |
| **Desplazar todo** | Las 8 filas se desplazan por los competidores sin posiciones fijas. |

La velocidad de rotación de atletas por defecto es de **5 segundos**.

## Explorar y restaurar

**Explorar LIF** lista los resultados anteriores de la carpeta supervisada para volver a mostrar cualquiera de ellos — útil para sesiones fotográficas o para volver a mostrar una serie anterior. Abrir un archivo antiguo en FinishLynx *no* altera la pantalla en directo; solo un cambio real de un resultado lo promueve.

**En blanco**, al principio de la lista, borra el resultado de todas las pantallas y vuelve a *Esperando resultados*. El siguiente resultado guardado se muestra con normalidad.

## Conexión de pantallas {#connecting-screens}

Abra `http://<dirección>:3000/display` en cada pantalla; se le asigna un número automáticamente. La página **Códigos QR de pantallas** (desde el panel Pantallas, o `/screens-overview`) muestra un código escaneable para cada página de pantalla, para dirigir rápidamente un teléfono, una tableta o el navegador de un televisor a la página correcta.

En el panel **Pantallas** asigna un diseño guardado a cada pantalla de forma independiente y elimina las pantallas que ya no están activas. El escritorio también tiene una vista previa de marcador integrada que refleja una pantalla real cuando le asigna un diseño.

Las pantallas se recargan solas cuando la aplicación se reinicia y conservan su número y su diseño. Para comprobar un diseño en las pantallas reales, use **Vista previa → En las pantallas** en el Constructor de diseños.

## El Constructor de diseños

Abra el Constructor de diseños para crear diseños a partir de widgets. Cada diseño tiene una forma de lienzo y un tema.

- **Empiece** con una plantilla, o arrastre widgets de la lista de la izquierda al lienzo.
- **Seleccione un widget** para editarlo en el panel **Widget** de la derecha. Lo esencial va primero; el resto está en **Más ajustes**. El panel **Lienzo** reúne los ajustes del diseño: nombre, tema, forma, **Mostrar en pantallas** y **Momentos**.
- **El texto de un widget** se arrastra directamente en el lienzo con el widget seleccionado. Los elementos se alinean entre sí y pueden alinearse a la izquierda, al centro o a la derecha.
- **Deshaga** con ⌘/Ctrl+Z y pulse **?** para ver todos los atajos. Los paneles laterales se pliegan para dar más espacio al lienzo.
- **Mostrar en pantallas** — marque las pantallas donde debe aparecer el diseño.
- **Vista previa** — **En el navegador** muestra el diseño aquí con datos de ejemplo o en directo. **En las pantallas** lo muestra en todas las pantallas conectadas hasta que lo detenga; después cada pantalla vuelve a su diseño.

![El Constructor de diseños — la paleta de widgets a la izquierda, el lienzo del diseño en el centro y el panel de propiedades (con el navegador de widgets) a la derecha]({{ '/assets/Layout-Builder.png' | relative_url }})

## Momentos {#moments}

Los momentos son tarjetas breves que se muestran en las pantallas al guardarse un resultado. Actívelos por diseño: **Lienzo → Momentos → Usar momentos en este diseño**.

- **Tras una carrera, mostrar** — el **Ganador** (con la diferencia) o el **Podio**. En carreras para, el podio se ordena por puntuación RAZA.
- **Foto-finish en llegadas ajustadas** — se muestra primero cuando los dos primeros están a menos de 0,05 s (ajustable), con la imagen de llegada si FinishLynx guardó una para esa carrera.
- **Récords del resultado** — cada atleta marcado en el campo User 3 de FinishLynx tiene su tarjeta. El récord del ganador va en su propia tarjeta.
- **Solo finales** — activado por defecto: las tarjetas solo se muestran en pruebas cuyo nombre contiene «Final». Los récords se muestran en cualquier ronda.
- **Mostrar sobre** — toda la pantalla, o un solo widget.

Cada tarjeta se muestra una sola vez por carrera, al guardarse el resultado — nunca al recargar una página ni al volver a mostrar un resultado antiguo. En la ventana principal, **Probar** reproduce una tarjeta de ejemplo en todas las pantallas que usan momentos, y **Podio** muestra los tres primeros del resultado actual, para ceremonias.

### Cortinilla entre resultados

Cuando llega el resultado de otra prueba, primero pasa una cortinilla de 2 segundos con el logo de PolyField y después los resultados entran fila a fila. Está activa en todos los diseños. Elija **La cortinilla muestra** para usar uno de sus diseños (un panel de patrocinadores, por ejemplo), o desmarque **Cortinilla entre resultados**.

## Resultados en pantalla

- **Entrada fila a fila** — un resultado nuevo entra fila a fila, ganador primero. Un resultado corregido desliza las filas a su nuevo puesto. Desmarque **Animar las filas cuando llegan o cambian los resultados** en el widget para desactivarlo.
- **Texto que cabe** — los nombres y títulos largos se reducen en lugar de cortarse.
- **Carreras para** — cuando el archivo de la prueba da a los atletas una clase WPA, la tabla añade las columnas **Clase** y **RAZA**, manteniendo el orden de llegada.
- **Sin nombres** — algunas carreras solo tienen dorsales; las filas y tarjetas muestran entonces el dorsal.
- **Temas** — resultados, tableros de concursos y relojes siguen el tema del diseño.

## Referencia de widgets

| Widget | Muestra |
|---|---|
| Tabla de resultados | El resultado actual, con columnas, rotación y tamaño de texto configurables. |
| Multi-resultado | Una cuadrícula de varios resultados (2×2 / 3×2), el más reciente o en rotación. |
| Lista de salida | La lista de salida de la prueba actual. |
| Reloj en marcha / Tiempo detenido | Reloj en directo o congelado. |
| Nombre de prueba / Viento | Nombre y viento de la prueba actual o del resultado. |
| Texto personalizado / Logo / Hora del día | Texto estático, una imagen/logo, o la hora. |
| Concursos PolyField (Field Results / Recent Results / Lanzamientos / Jump Ruler / Vertical Jumps) | Pantallas de concursos en directo alimentadas por PolyField Server, agrupadas en **PolyField Server**. Véase [Lanzamientos](#throws-display), [Saltos horizontales](#horizontal-jump-displays) y [Saltos verticales](#vertical-jump-displays). |
| Superposiciones Texto / Salvapantallas / Vista de línea / Reloj | El banner de texto, la imagen/diseño del salvapantallas, la foto-finish y el reloj a pantalla completa (se muestran cuando el operador activa la superposición correspondiente). |
| Superposición de Cuenta atrás | Cuenta atrás hasta una hora objetivo con un rótulo editable. |

## Puntos de pruebas combinadas

Para una competición de pruebas combinadas, la tabla de resultados puede mostrar una columna adicional **Combined Event** (prueba combinada) que puntúa cada marca de pista según las **tablas oficiales 2026 UKA/ESAA de pruebas combinadas**.

![Un resultado de 80mH U14B con la columna de puntos de prueba combinada — puntos por atleta y sin puntuación para DNF/DQ](assets/combined-events.png)

- **Añadir la columna** — en el Constructor de diseños, seleccione un widget **Tabla de resultados** o **Multi-resultado** y añada la columna **Combined Event** (Propiedades → Columnas). Marque **Añadir «pts» a la columna de puntos de pruebas combinadas** para mostrar `617 pts` en lugar de `617`.
- **Automático por prueba y sexo** — la tabla se elige a partir del nombre de la prueba (p. ej. `80mH (76.2) U14B`), cubriendo todas las categorías — de U13 a U20, Senior y Máster — sin configuración por atleta.
- **Solo pista** — se puntúan las vallas y las carreras lisas; los concursos, los relevos y cualquier prueba sin tabla correspondiente quedan en blanco.
- **No finalizados** — los atletas DNS no se muestran; DNF y DQ no muestran puntuación.

El tiempo usado para la búsqueda es el valor mostrado (ya redondeado a la precisión del cronometraje), por lo que los puntos coinciden exactamente con las tablas oficiales.

## Pantallas de saltos horizontales {#horizontal-jump-displays}

Estos widgets muestran datos de concursos en directo de **PolyField Server** en la misma red. Añádalos desde el grupo **PolyField Server** del Constructor de diseños. Configure la dirección del servidor una sola vez en la ventana principal, en **PolyField Server**; todos los widgets de concursos la usan.

### Jump Ruler (PolyField)

Una regla junto al foso para **salto de longitud y triple salto** — ideal para una tira LED larga y estrecha junto a la pista de impulso (p. ej. 500 mm × 4–6 m). Dibuja una escala de distancias con marcas de metro / 50 cm / 10 cm, señala los tres mejores saltos y muestra los datos del saltador actual.

![El Jump Ruler en el Constructor de diseños — la escala anclada al foso con el saltador actual, el saltador anterior, las chinchetas del top 3 y la media de la competición](assets/jump-ruler.png)

- **Sigue la prueba en curso.** Por defecto, la regla muestra la prueba de saltos horizontales en curso y pasa sola a la siguiente. Para reglas en zonas distintas, marque las pruebas de cada una. Las reglas nuevas colocan su texto en una banda sobre los marcadores.
- **Tabla de batida.** La escala está anclada al foso: introduzca el **inicio de la regla** para salto de longitud y para cada tabla del triple salto (**7 / 9 / 11 / 13 m**, con 2 decimales, p. ej. `11.02`). La tabla activa del atleta (del flujo) determina el inicio usado, para que las marcas caigan siempre en el lugar correcto.
- **Chinchetas del top 3.** Las tres mejores marcas se muestran como chinchetas de alturas decrecientes (1.ª la más alta, luego 2.ª y 3.ª), con la 1.ª siempre delante. Una marca fuera del rango visible aparece como **flecha** en el borde apuntando en su dirección.
- **Chincheta de media.** Una chincheta **Avg** opcional traza la media de la competición.
- **Panel del atleta.** Coloque cada elemento arrastrándolo — **atleta actual**, marca y viento actuales, **atleta anterior** con su marca y viento, tabla actual y mejor marca de la competición — y ajuste para cada uno el **rótulo, el color, el tamaño** y la visibilidad. Dispóngalos como banner superior o panel lateral.
- **Sentido de carrera.** Elija **izquierda → derecha** o **derecha → izquierda** para que la escala coincida con el sentido de impulso de los atletas hacia el foso.
- **El flujo:** se selecciona un atleta → se muestra como *actual* (sin marca); se mide su salto → aparecen su *marca y viento*; se selecciona el siguiente atleta → pasa a ser *actual* y el anterior pasa a *anterior*.

### Field Results & Recent Results (PolyField)

**Field Results (PolyField)** — un tablero de clasificación en directo de concursos (puesto, atleta, club, prueba, marca, mejor), con el líder resaltado y los nulos en rojo.

![Field Results (PolyField) — clasificación en directo de concursos con el líder resaltado](assets/field-results.png)

**Recent Results (PolyField)** — las tres últimas marcas de concursos (nombre, prueba, ronda y marca, con viento para los saltos horizontales).

![Recent Results (PolyField) — las tres últimas marcas de concursos](assets/recent-results.png)

## Pantalla de lanzamientos {#throws-display}

**Lanzamientos** muestra un concurso de peso, disco, martillo o jabalina desde PolyField Server, con cada caída marcada en el sector y arcos de distancia. Como los demás tableros de concursos, sigue por defecto la prueba en curso.

- Los lanzamientos del atleta actual, numerados por ronda; las caídas de los demás como mapa de calor; la mejor marca del concurso como estrella dorada.
- El último lanzamiento aparece en cuanto se mide. Si toma el liderato, primero pasa un rótulo **NUEVA MEJOR MARCA**.
- Atleta, club, ronda, marca, posición, mejor marca y *marca para liderar* son textos que se colocan libremente.
- **Panel LED pequeño** agranda los marcadores y quita el detalle fino para pantallas LED de baja resolución. El sector ocupa una zona que usted dimensiona, sin tocar nunca el texto.
- Necesita la versión de PolyField Server que envía las coordenadas de caída rotadas.

## Pantallas de saltos verticales {#vertical-jump-displays}

**Vertical Jumps** muestra un concurso de **salto de altura o con pértiga**. Como los demás tableros de concursos, sigue por defecto la prueba en curso; marque pruebas para vincular un tablero a su zona. Está en el grupo **PolyField Server** y tiene dos estilos.

### Avanzado — tablero de clasificación

Una barra horizontal, con la altura actual, divide la pantalla como un tablero de clasificación.

![Vertical Jumps (PolyField), estilo avanzado — la barra con la altura actual, los atletas que han superado arriba con un punto verde y el atleta eliminado en una fila roja](assets/vertical-jumps.jpg)

- Los atletas que aún deben superar se sitúan **debajo** de la barra. Cuando uno **supera**, pasa **arriba** con un **punto verde**; un **fallo** muestra un **punto rojo** y permanece debajo; un atleta **eliminado** tiene una **fila roja**.
- Cuando **cambia la altura**, la barra aparece con una animación, todos los atletas vuelven debajo y los eliminados desaparecen. Los atletas que **pasan** la altura no se muestran.
- La posición vertical de la barra sigue la proporción entre superados y no superados; si hay más atletas que filas, la lista **rota** para mostrarlos a todos.
- Los datos se alinean en columnas (puesto · nombre · intentos · marcador) para mantenerse ordenados sea cual sea la longitud de los nombres.

### Simplificado — tarjeta de estado actual

Una sola tarjeta que muestra al atleta en acción: la altura actual, su nombre, sus intentos a esa altura y su serie completa.

![Vertical Jumps (PolyField), estilo simplificado — la altura actual, el atleta y los intentos](assets/vertical-jumps-simple.jpg)

Cada elemento — nombre de la prueba, altura, atleta, intentos, serie, y opcionalmente puesto / mejor / dorsal — se **coloca arrastrando** con su propia **leyenda, color, tamaño** y visibilidad, como el panel del Jump Ruler.

### Opciones comunes

- **Sin altura definida.** Antes de anunciarse una altura (mostraría `0,00 m`), el widget muestra el **nombre de la prueba y un logotipo de patrocinador** en su lugar.
- **Logotipo de patrocinador.** Opcional — se muestra en esa tarjeta de espera y (en modo avanzado) bajo la barra durante el cambio de altura.
- **Configurable** — filas, tamaño de texto y fuente, colores (barra, superado, fallo, eliminado, acento) y la duración de aparición de la barra.

## Temas, dorsales y abreviaturas de clubes

Los **temas** definen los colores por defecto de todas las pantallas; puede crearlos, duplicarlos y editarlos. Los **dorsales** se pueden mostrar u ocultar en la vista de resultados. Las **abreviaturas de clubes** se gestionan de forma centralizada (edite la lista de clubes) y se aplican en todas partes — añada un club nuevo o sustituya una abreviatura integrada, y los cambios llegan a todas las pantallas en unos segundos.

## Vistas web

Las vistas web se acceden mejor a través de la interfaz web, usando los datos de acceso de la parte superior de la aplicación de escritorio. Páginas clave:

| Página | URL |
|---|---|
| Marcador (diseño activado) | `/scoreboard` |
| Pantalla de visualización | `/display` |
| Vista multi-resultado | `/results` |
| Quiosco de atleta | `/athlete` |
| Panel de velocidades | `/speed` |
| Reloj en marcha | `/clock` |
| Clasificaciones RAZA | `/raza` |
| Códigos QR de pantallas | `/screens-overview` |

### Vista multi-resultado

Muestra los resultados en una matriz 2×2 o 3×2. Configúrela para mostrar los últimos resultados o rotar por todos los resultados disponibles; adapte el tamaño del texto; y use el modo de pantalla completa para ocultar la barra de herramientas (cualquier movimiento del ratón la hace reaparecer). Los resultados se paginan, con la página actual indicada arriba. El icono de búsqueda abre el quiosco de atleta.

![Vista multi-resultado — una cuadrícula 2×2 de resultados con la barra de herramientas abajo]({{ '/assets/multi-result.png' | relative_url }})

### Quiosco de atleta (autoservicio)

Abra `<DIRECCIÓN-IP>:3000/athlete`. Un atleta busca por nombre o número de dorsal; al hacer clic en un nombre se muestran todas sus marcas en la carpeta de resultados actual. Al hacer clic en una tarjeta de resultado se muestra a pantalla completa para sesiones fotográficas. **Restablecer** borra la búsqueda; el botón atrás vuelve al campo de búsqueda.

![El quiosco de autoservicio para atletas — búsqueda por nombre o número de dorsal]({{ '/assets/athlete-kiosk.png' | relative_url }})

## Configuración de FinishLynx y TimeTronics {#finishlynx-setup}

- **Scripts de marcador** — use los scripts suministrados `polyfield.lss`, `polyfield-wind.lss` y `polyfield-backup.lss` para que FinishLynx envíe el reloj en marcha, el viento, las listas de salida y los resultados a PolyField & Track Display. Consulte **[Configuración de los marcadores](#scoreboard-setup)** más abajo para configurar cada salida.
- **Récords** — marque el récord de un atleta en el campo **User 3** de FinishLynx (p. ej. `PB` o `W50 WR`). Los códigos de récord se amplían a títulos completos a partir de la lista de clubes.
- **Vista de línea** — exporte sus imágenes de foto-finish (JPG) a la carpeta de resultados supervisada; el botón Vista de línea se activa en cuanto aparecen.
- **Resultados** — guarde su LIF con normalidad; PolyField solo muestra los resultados guardados.

### Configuración de los marcadores (FinishLynx) {#scoreboard-setup}

PolyField & Track Display recibe el reloj en marcha, las listas de salida, los resultados en directo y el viento por una única transmisión UDP en el **puerto 5001**. FinishLynx los envía a través de sus salidas de **Scoreboard** (**Options → Scoreboard**). Configure las salidas siguientes — cada una es un marcador de **Red (UDP)** dirigido al ordenador que ejecuta PolyField & Track Display.

**Ajustes comunes a todas las salidas:**

| Ajuste | Valor |
|---|---|
| Serial Port | Network (UDP) |
| Port | `5001` |
| IP Address | la IP del ordenador que ejecuta PolyField & Track Display |
| Code Set | Single Byte |
| Results | Auto · Paging activado |

#### 1. Salida principal — `polyfield.lss`

La transmisión principal: reloj en marcha, listas de salida y resultados en directo.

![Ajustes del marcador de FinishLynx para la salida principal de PolyField & Track Display](assets/scoreboard-main.png)

- **Script:** `polyfield.lss` · **Name:** PolyField & Track Display
- **Running Time:** Normal
- **Running Time → Options:** *Send results if armed* ✓
- **Auto Break:** *Finish* ✓ (con *if capturing* ✓)
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓ (deje *Affiliation abbreviation* desactivado — PolyField & Track Display expande los nombres de los clubes desde su propia lista de clubes)

#### 2. Salida de viento — `polyfield-wind.lss`

Una salida dedicada a las lecturas de viento.

![Ajustes del marcador de FinishLynx para la salida de viento](assets/scoreboard-wind.png)

- **Script:** `polyfield-wind.lss` · **Name:** PolyField & Track Display Wind
- **Running Time:** **Raw** — el viento se dispara en cada corte de célula; el modo Raw transmite cada lectura tal cual (PolyField & Track Display ignora los valores «no data»)
- **Running Time → Options:** *Send results if armed* desactivado
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Affiliation abbreviation* ✓ · *Track live results* ✓

#### 3. Salida de respaldo — `polyfield-backup.lss` (recomendado)

Una segunda copia independiente de la **lista de salida** para mayor fiabilidad. FinishLynx envía cada lista de salida solo una vez al cargar la prueba, por lo que un único paquete UDP perdido puede dejar una pantalla en blanco. Esta salida de respaldo envía una lista de salida idéntica desde un marcador distinto: si se pierde un paquete, el otro llega igualmente. Diríjala al **mismo** ordenador PolyField & Track Display.

![Ajustes del marcador de FinishLynx para la salida de respaldo de la lista de salida](assets/scoreboard-backup.png)

- **Script:** `polyfield-backup.lss` · **Name:** PolyField & Track Display Backup
- **Running Time:** Normal
- **Running Time → Options:** *Send results if armed* ✓
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓

> Las tres salidas pueden funcionar a la vez y enviar a la misma IP y puerto — PolyField & Track Display las distingue por su contenido.

## Retransmisión con OBS {#webcasting}

Use PolyField & Track Display como capa gráfica transparente sobre una emisión de vídeo en OBS.

1. Cree un diseño para la emisión — la plantilla **Rótulo para retransmisión** es un buen punto de partida. Mantenga los widgets en los bordes de la imagen.
2. En OBS añada una fuente **Navegador**, 1920 × 1080, con la dirección `http://<dirección>:3000/display/<número>?transparent=1`.
3. En el Constructor de diseños, marque esa pantalla en **Mostrar en pantallas** de su diseño de emisión.

Todo lo que no es un widget es transparente, y los widgets aún sin datos permanecen ocultos. Desmarque **Cortinilla entre resultados** en el diseño de emisión para que la cortinilla no tape la cámara.

> **Emitir sin usar los datos de la red de resultados** — si su red de resultados funciona con una SIM 4G, conecte el ordenador de OBS a ambas redes y no asigne puerta de enlace predeterminada al adaptador de la red de resultados. La emisión saldrá entonces por la otra conexión.

## Red

- La aplicación sirve en el **puerto 3000** y se anuncia como `display.local`, así que las pantallas pueden usar `http://display.local:3000` sin conocer la IP. Las pantallas configuradas con el antiguo `track.local` siguen funcionando.
- Configure la dirección de **PolyField Server** una sola vez en la ventana principal; todos los widgets de concursos la usan.
- En ordenadores con más de una tarjeta de red (habitual en Windows), elija el adaptador de red correcto en el panel de conexión para que se anuncie la dirección correcta.
- Todos los dispositivos deben estar en la misma red que el ordenador anfitrión.

## Resolución de problemas

| Síntoma | Comprobar |
|---|---|
| El botón Vista de línea está atenuado | Aún no hay imágenes JPG de foto-finish en la carpeta supervisada — compruebe la ruta de exportación de imágenes de FinishLynx. |
| No aparece ninguna tarjeta de momento | El diseño debe tener los momentos activados. Con **Solo finales**, el nombre de la prueba debe contener «Final». Cada carrera se muestra una vez por pantalla: guardar de nuevo el mismo archivo no la repite. |
| Una pantalla muestra «esperando diseño» | Asigne un diseño a esa pantalla en el panel Pantallas. |
| Reapareció un resultado antiguo | Abrir un archivo en FinishLynx ya no lo promueve; solo lo hace un cambio real. Use Explorar LIF para volver a mostrar resultados anteriores de forma intencionada. |
| Las pantallas no se conectan | Confirme la misma red, el puerto 3000 accesible y (PC con varias tarjetas) el adaptador de red correcto seleccionado. |

## Descarga y soporte

Descargue la última versión desde [www.polyfield.co.uk](https://www.polyfield.co.uk) o desde la [página de versiones](https://github.com/KingstonPolyAC/PolyField-and-Track-Display/releases). Soporte: [support@polyfield.co.uk](mailto:support@polyfield.co.uk).
