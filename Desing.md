\# Nina To The Rescue — Landing Page  
\#\#\# Design Doc

| | |  
|---|---|  
| \*\*Estado\*\* | Implementado — en revisión |  
| \*\*Autor(es)\*\* | Equipo de diseño, Nina To The Rescue |  
| \*\*Revisores\*\* | Dirección de Nina To The Rescue |  
| \*\*Última actualización\*\* | 27 de agosto de 2026 |  
| \*\*Artefacto\*\* | \`Nina To The Rescue Landing.dc.html\` |

\---

\# Parte I — Tokens

\#\# 1.1 Color

Cuatro colores, sin excepciones. Ningún gradiente.

| Token | Hex | Uso |  
|---|---|---|  
| \`--ink\` | \`\#171512\` | Texto, bordes (2.5px), sombras duras, footer |  
| \`--orange\` | \`\#E1560E\` | Marca, CTA primario, sección Donate, acentos |  
| \`--cream\` | \`\#FBF3E7\` | Fondo base, texto sobre fondos oscuros |  
| \`--deep\` | \`\#14453A\` | Verde profundo: banda de cita, sombras duras alternas |

\*\*Excepción documentada:\*\* la sección \*Our Work\* usa \`\#123252\` (azul profundo) como fondo, para separar visualmente la campaña del resto del sitio. Es el único valor fuera de los cuatro tokens y está expuesto como tweak editable.

Opacidades permitidas sobre tinta: \`.78\` y \`.80\` para párrafos secundarios, \`.62\` para pies de texto sobre fondo oscuro.

\#\# 1.2 Tipografía

| Rol | Familia | Peso | Aplicación |  
|---|---|---|---|  
| Display | \*\*Ultra\*\* | 400 | H1, H2, citas, botones grandes |  
| Texto | \*\*Nunito Sans\*\* | 400 / 600 / 700 / 900 | Párrafos, nav, etiquetas, bocadillos |

| Estilo | Especificación |  
|---|---|  
| H1 | Ultra 400, \`clamp(34px, 4.9vw, 62px)\`, line-height 1.03, tracking −1px |  
| H2 | Ultra 400, \`clamp(26px, 3.3vw, 44px)\`, line-height 1.10, tracking −.6px |  
| Cita | Ultra 400, \`clamp(22px, 2.7vw, 36px)\`, line-height 1.28 |  
| Cuerpo | Nunito Sans 500/600, 17–17.5px, line-height 1.55–1.62 |  
| Eyebrow | Nunito Sans 900, 11.5px, tracking 2px, mayúsculas |  
| Nav | Nunito Sans 700, 15px |  
| Bocadillo | Nunito Sans 900, 15px (satélite) / 19px (principal) |

\#\# 1.3 Forma y profundidad

| Token | Valor |  
|---|---|  
| Borde | \`2.5px solid var(--ink)\` en todo contenedor |  
| Sombra | Dura y desplazada: \`Npx Npx 0 \<color\>\` — nunca difusa |  
| Sombra botón | \`4–6px\` · \*\*Tarjeta\*\* \`8–12px\` |  
| Radio píldora | \`999px\` (botones, etiquetas, nav) |  
| Radio tarjeta | \`22–32px\` |  
| Radio foto | \`50%\` (círculos) · \`28px\` (rectangulares) |

\#\# 1.4 Espacio y grilla

| Token | Valor |  
|---|---|  
| Ancho máximo | \`1240px\` (\`1080px\` en la banda de cita) |  
| Padding lateral | \`28px\` |  
| Padding vertical de sección | \`clamp(56px, 7vw, 104px)\` |  
| Gap de grilla | \`clamp(24px, 4vw, 60px)\` |  
| Columna mínima | \`300–340px\` antes de colapsar |

Sin breakpoints fijos: \`auto-fit\` \+ \`minmax()\` colapsan las grillas y \`clamp()\` escala la tipografía.

\#\# 1.5 Movimiento

| Patrón | Especificación |  
|---|---|  
| Reveal al scroll | Fade \+ 26px de subida, 700ms \`cubic-bezier(.2,.7,.2,1)\`, escalonado 70ms |  
| Nav comprimido | Padding 14px → 8px \+ sombra, a partir de 24px de scroll |  
| Nav activo | El enlace de la sección visible se pinta naranja |  
| Flotación de círculos | \`orbFloat\` 6–9s, delays negativos desfasados |  
| Parallax del hero | 0.05× la velocidad del scroll |  
| Hover de círculo | Desplazamiento 8–11px \+ escala 1.05, 450ms |  
| Bocadillo cómic | Pop de opacidad \+ escala .9 → 1, 280ms \`cubic-bezier(.2,1.4,.4,1)\` |  
| Hover de botón | Se levanta 2px, la sombra dura crece 2px |  
| Hover de partner | La tarjeta se eleva y gana sombra verde |

Todo el movimiento se apaga con el tweak \`motion\`.

\---

\# Parte II — Do's & Don'ts

\#\#\# Color

✅ Usar naranja solo donde se quiere una acción o un acento de marca.  
✅ Alternar fondos crema y bloques saturados para marcar el ritmo de las secciones.  
✅ Alternar el color de las sombras duras (naranja / verde) para dar variedad sin color nuevo.  
❌ No agregar un quinto color, ni tintes intermedios de la paleta.  
❌ No usar gradientes, ni siquiera sutiles.  
❌ No poner naranja sobre verde ni verde sobre naranja: no pasan contraste.  
❌ No pintar de naranja bloques grandes de texto largo.

\#\#\# Tipografía

✅ Ultra solo en títulos, citas y botones grandes.  
✅ Limitar los párrafos a 30–44 caracteres de ancho (\`max-width\` en \`ch\`).  
✅ Mantener el cuerpo en 17px o más.  
❌ No usar Ultra en párrafos ni en textos menores a 16px: es ilegible.  
❌ No poner Ultra en cursiva ni forzar pesos que la familia no tiene.  
❌ No introducir una tercera familia tipográfica.

\#\#\# Forma

✅ Todo contenedor lleva borde de tinta de 2.5px.  
✅ Sombra dura desplazada, siempre en la misma dirección (abajo-derecha).  
❌ No usar sombras difusas, blur ni transparencias decorativas.  
❌ No mezclar grosores de borde en la misma vista.  
❌ No dejar tarjetas sin borde "para aligerar": rompe el lenguaje.

\#\#\# Fotografía

✅ Animales reales, en su contexto, con la mirada visible.  
✅ Recorte circular para retratos; rectangular para escenas de trabajo.  
✅ Logos de aliados con fondo transparente y \`fit: contain\`.  
❌ No usar stock genérico ni fotos de animales que no atendió la organización.  
❌ No poner texto encima de una fotografía sin bloque de color de por medio.  
❌ No estirar ni deformar un logo para llenar su tarjeta.

\#\#\# Movimiento

✅ El movimiento acompaña, nunca anuncia: desplazamientos cortos, curvas suaves.  
✅ Desincronizar duraciones para que nada lata al mismo tiempo.  
✅ Cada animación debe seguir funcionando si el usuario la apaga.  
❌ No animar nada que el usuario no pueda alcanzar o interrumpir.  
❌ No usar rebotes largos, giros completos ni parpadeos.  
❌ No animar propiedades que no sean \`transform\` u \`opacity\`.

\#\#\# Contenido

✅ Frases cortas y concretas: qué se hace, dónde, para quién.  
✅ Conectar cada cifra con lo que financia.  
❌ No usar emojis: no son parte de la identidad.  
❌ No rellenar secciones con texto o datos de adorno.  
❌ No agregar elementos ornamentales sin función: si un círculo está, lleva una foto.

\---

\# Parte III — Contexto y decisiones

\#\# 3.1 Contexto

Nina To The Rescue es una organización sin fines de lucro en El Salvador dedicada a proveer atención veterinaria a animales en situación de calle y a familias que no pueden costear una clínica. Su primera campaña mayor, \*"Dr. Jeff por el Bienestar Animal"\*, necesita un punto de aterrizaje público que explique quiénes son, qué hacen y cómo donar.

No existía sitio previo ni sistema de diseño propio. Este documento registra el sistema creado y las decisiones tomadas al construir la landing page.

\#\# 3.2 Objetivos

\- Comunicar la misión con claridad en menos de 10 segundos de lectura.  
\- Llevar al usuario a \*\*Donar\*\* desde cualquier punto del scroll.  
\- Presentar la campaña Dr. Jeff como prueba concreta de impacto.  
\- Verse profesional pero cálido: una ONG seria, no corporativa.  
\- Que la organización pueda reemplazar fotos y textos sin tocar código.

\#\#\# No-objetivos

\- Procesamiento de pagos dentro del sitio (el botón enlaza a plataforma externa, pendiente de definir).  
\- Sistema multi-página, blog o CMS.  
\- Versión en español del contenido (v1 es solo inglés).  
\- Ilustración personalizada o iconografía dibujada.

\#\# 3.3 Resumen de la solución

Una página única de scroll continuo con seis bloques:

\`\`\`  
Nav (sticky)  
  └─ Hero — constelación de fotos circulares \+ CTA  
  └─ Cita — banda de color, declaración de misión  
  └─ About Us — foto \+ texto \+ tarjeta de datos  
  └─ Our Work — campaña Dr. Jeff (bloque de color propio)  
  └─ Partners — grilla de logos  
  └─ Donate — CTA final \+ retrato de Nina  
Footer  
\`\`\`

El ritmo alterna fondos crema y bloques de color saturado, de modo que cada sección se lee como una unidad distinta sin necesidad de separadores decorativos.

\#\# 3.4 Diseño por sección

\*\*Nav.\*\* Sticky, fondo crema, borde inferior de tinta. Avatar circular de la marca \+ nombre y tagline. Cuatro enlaces con estado activo, más botón Donate con sombra dura.

\*\*Hero — constelación de círculos.\*\* Diseño rehecho (v2); reemplazó al perro del logo por fotografías reales. Cinco círculos de tamaños distintos en composición asimétrica: uno grande al centro (52% del contenedor, perro) y cuatro satélites (23–27%: dos perros, dos gatos). Cada uno flota con su propia duración, de modo que el conjunto nunca se sincroniza. Al hover, el círculo se desplaza en su dirección propia y aparece un bocadillo de cómic con "Woof\!" o "Meow\!" según la especie. Las sombras duras alternan naranja y verde. Columna izquierda: etiqueta \*Non-profit · El Salvador\*, H1 "Humans saving animals.", párrafo de misión y dos CTAs.

\*\*Banda de cita.\*\* Fondo verde profundo, una sola frase en Ultra sobre esterilización como solución de raíz. Funciona como respiro entre hero y contenido.

\*\*About Us.\*\* Grilla de dos columnas: fotografía vertical 4:5 con sombra naranja, y texto con una tarjeta de datos anidada. Explica el alcance del trabajo: cirugía, vacunación y tratamiento gratuitos o de bajo costo.

\*\*Our Work.\*\* Bloque azul profundo. Encabezado sobre la primera misión, tarjeta naranja grande con la campaña y su fotografía, y bajo ella el bloque de Dr. Jeff Young: retrato cuadrado \+ descripción de la colaboración.

\*\*Partners.\*\* Encabezado a dos columnas (título \+ invitación a sumarse) y grilla responsiva de cuatro tarjetas para logos, cada una con hover elevado.

\*\*Donate.\*\* Fondo naranja completo. Título, párrafo que conecta la donación con la campaña, y dos vías: \*Donate now\* (botón tinta) y \*Donate in kind\* (contorno, abre correo). A la derecha, el retrato de Nina en círculo con la misma flotación y bocadillo "Woof\!" del hero, cerrando el sitio con el mismo gesto con que abre.

\*\*Footer.\*\* Fondo tinta, marca en avatar circular, tagline y datos de contacto.

\#\# 3.5 Contenido editable

Las fotografías se cargan arrastrándolas sobre las zonas marcadas; quedan guardadas en el navegador. Todo el texto es editable directamente sobre el diseño.

| Zona | Contenido esperado |  
|---|---|  
| \`nina-hero-1\` … \`nina-hero-5\` | Perro grande, perro, gato, gato, perro |  
| \`nina-about\` | Equipo atendiendo animales (vertical 4:5) |  
| \`nina-campaign\` | Jornada de esterilización |  
| \`nina-drjeff\` | Retrato de Dr. Jeff Young (cuadrado) |  
| \`nina-partner-1\` … \`-4\` | Logos de aliados (fondo transparente) |

\#\# 3.6 Tweaks expuestos

| Tweak | Efecto |  
|---|---|  
| \`deepTone\` | Cambia el verde profundo en todo el sitio |  
| \`motion\` | Apaga reveals, flotación y parallax |

\#\# 3.7 Alternativas consideradas

\*\*Hero con una sola fotografía grande.\*\* Descartado: obliga a elegir entre perro o gato y no transmite el volumen de animales atendidos.

\*\*Hero con la ilustración del logo.\*\* Fue la v1. Se reemplazó porque la ilustración compite con la marca del nav y no muestra animales reales.

\*\*Negro puro para Our Work.\*\* Se probó y resultaba fúnebre en una página sobre salvar vidas. El azul profundo mantiene el contraste sin el peso.

\*\*Paleta de cinco o más colores.\*\* Descartado por decisión explícita: cuatro colores mantienen la identidad reconocible y evitan que el naranja pierda fuerza como señal de acción.

\#\# 3.8 Consideraciones transversales

\*\*Accesibilidad.\*\* Texto de cuerpo desde 17px; contraste de tinta sobre crema y crema sobre tinta/verde/azul por encima de AA. Áreas táctiles de botón sobre 44px. Pendiente: respetar \`prefers-reduced-motion\` de forma automática (hoy es un tweak manual) y verificar el contraste del texto sobre naranja en la sección Donate.

\*\*Rendimiento.\*\* Página única, sin dependencias externas más allá de las fuentes de Google. El movimiento usa solo \`transform\` y \`opacity\`.

\#\# 3.9 Pendientes

\- Confirmar la dirección de correo \`hello@ninatotherescue.org\`.  
\- Validar los textos de About, Partners y Donate con la organización.  
\- Definir la plataforma de donación a la que enlaza \*Donate now\*.  
\- Cargar las fotografías reales y los logos de aliados.  
\- Decidir si se necesita versión en español.

