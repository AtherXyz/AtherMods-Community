# Roadmap · Ather DST

**Propósito:** jugar DST Pocket con mods, con mejor estabilidad de FPS, menor consumo de memoria, interoperabilidad entre mods y una interfaz nativa clara y estética. Mantener el juego original y su autenticación.

**Estado al 28 de octubre de 2026:** roadmap preparado y publicado. Implementación de este nuevo alcance pendiente. **0/8 etapas cerradas · 0/49 criterios aprobados.** Estas cifras no descuentan las funciones que ya existen en Ather Mods: miden los nuevos objetivos de este plan.

**[Abrir cuadro general y seguimiento de etapas](https://github.com/AtherXyz/AtherMods-Community/issues/9)** · [Datos del cuadro](roadmap.json) · [Descargas actuales](README.md#descargas)

## Cuadro de progreso medible

| Etapa | Resultado que se busca | Criterios aprobados | Depende de | Estado | 👍 |
| --- | --- | --- | --- | --- | --- |
| [M1](https://github.com/AtherXyz/AtherMods-Community/issues/1) | Base de medición y arranque fiable | 0/6 | — | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/1) |
| [M2](https://github.com/AtherXyz/AtherMods-Community/issues/2) | Filtrado e identidades de mods frente a escritorio | 0/6 | M1 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/2) |
| [M3](https://github.com/AtherXyz/AtherMods-Community/issues/3) | Comunicación e interoperabilidad entre mods | 0/6 | M2 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/3) |
| [M4](https://github.com/AtherXyz/AtherMods-Community/issues/4) | Optimización de CPU, tareas Lua y HUD | 0/6 | M1, M3 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/4) |
| [M5](https://github.com/AtherXyz/AtherMods-Community/issues/5) | Perfil de RAM reducida y calidad gráfica | 0/6 | M1 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/5) |
| [M6](https://github.com/AtherXyz/AtherMods-Community/issues/6) | Alone de escritorio y persistencia individual | 0/6 | M2, M3 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/6) |
| [M7](https://github.com/AtherXyz/AtherMods-Community/issues/7) | Menú nativo protagonista y diseño móvil | 0/6 | M2, M3 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/7) |
| [M8](https://github.com/AtherXyz/AtherMods-Community/issues/8) | Regresión, entrega y pruebas de comunidad | 0/7 | M4, M5, M6, M7 | Planificado | [0 · votar](https://github.com/AtherXyz/AtherMods-Community/issues/8) |

Cada enlace abre una issue con la lista verificable. Los 👍 son reacciones reales: el número de esta tabla es una fotografía de la fecha indicada; el recuento actual se consulta en cada issue. Las casillas de la issue general permiten seguir las etapas cerradas. Los votos orientan el interés de la comunidad; las dependencias técnicas y la conservación de partidas condicionan el orden.

## Medidas de éxito

| Medida | Referencia actual | Objetivo inicial | Cómo se comprobará |
| --- | --- | --- | --- |
| p95 de tiempo de fotograma | Sin medir con un protocolo común | Al menos 20% menor en el escenario limitado por CPU | Tres repeticiones por variante, mismo mundo/pack/cámara y recorrido |
| Memoria PSS pico del proceso del juego | Sin medir con un protocolo común | Al menos 15% menor | Mismo mundo y pack; anotar cambios gráficos y memoria GPU por separado si es accesible |
| Arranque | Fallo Samsung/freezer pendiente de validación de candidata | 10/10 arranques de proceso por teléfono sin cierre ni recuperación inesperada | Registro de versión, resultado y diagnóstico |
| Persistencia con Alone | Steam y port móvil comparados; integración nueva pendiente | 5 ciclos de reentrada en superficie, 5 en cuevas y 5 viajes completos | Comparar día/reloj, inventario, construcciones, mapa y ubicación |
| Sesión ligera | Pendiente | 30 minutos y 3 reentradas sin cierre ni crecimiento sostenido atribuible al cambio | Muestreo de memoria y estado térmico con protocolo documentado |
| Interfaz | AM y selector nativo existentes | Recorrido principal completo sin consola en S23 Ultra y Z60 | Capturas, prueba táctil, retorno tras salir y confirmación física de Ather |

**Los porcentajes son objetivos propuestos, no ganancias obtenidas ni garantías.** M1 fija la referencia; si los resultados cambian la viabilidad, se documentará la propuesta de ajuste antes de cambiar la meta. La memoria PSS no equivale a memoria Lua ni a toda la memoria gráfica. Un pico debe compararse con la misma duración y frecuencia de muestreo. No se promete todavía un mínimo de 4 o 6 GB: harán falta dispositivos de esas clases para comprobarlo.

## Punto de partida verificado

- La descarga pública sigue siendo alpha39: entrada con tres mods en Z60. La prueba conjunta de 17 mods en S23 Ultra corresponde a alpha36.
- El código local tiene una candidata alpha42 para mitigar un fallo de arranque Samsung. Sus comprobaciones automáticas no confirman aún la solución en el teléfono. Este roadmap no publica esa candidata ni cambia la entrega vigente.
- Ya existe ordenamiento de cliente por prioridad y selector con widgets nativos. La comparación estática encontró funciones de dependencias bloqueadas en el selector y criterios distintos para api_version_dst/api_version entre Java y Lua.
- El gestor usa identidades internas para los ZIP y resolución de módulos; falta comprobar interoperabilidad completa cuando un mod depende de otro o comparte módulos.
- Steam instalado declara Alone 1.2.44; la adaptación móvil analizada deriva de 1.2.40 y añade cambios extensos. La nueva integración debe coordinar guardados y arranque con el gestor.
- Cave RAM Unlock elimina una restricción de acceso a cuevas; no reduce la memoria que necesitan.

## Alcance de las etapas

### [M1 · Base de medición y arranque fiable](https://github.com/AtherXyz/AtherMods-Community/issues/1)

- Identificar APK, versión del juego, dispositivo, Android y hashes del pack usado en cada prueba.
- Resolver o aislar el fallo de arranque Samsung/freezer antes de medir rendimiento; registrar 10 arranques de proceso por teléfono, sin cierres ni recuperaciones inesperadas.
- Medir tres repeticiones por escenario: original, pack de referencia y pack con el cambio propuesto; conservar mundo, recorrido, cámara y ajustes.
- Registrar FPS, tiempo de fotograma p50/p95/p99, memoria PSS y pico cuando estén disponibles; declarar el método y cualquier dato inaccesible.
- Comparar al inicio y tras 20 minutos, anotando estado térmico, batería/carga y condiciones para detectar degradación sostenida.
- Publicar una tabla de referencia anonimizada con cifras reales y un criterio reproducible de comparación.

### [M2 · Filtrado e identidades de mods frente a escritorio](https://github.com/AtherXyz/AtherMods-Community/issues/2)

- Unificar la interpretación de api_version_dst/api_version entre clasificación Java, catálogo y runtime de cliente.
- Resolver coherentemente metadatos condicionales y mostrar por qué un mod se admite, queda pendiente o se rechaza.
- Reconocer mod_dependencies y mostrar dependencias ausentes, ciclos y versiones cuando exista información suficiente.
- Conservar una correspondencia entre identidad original del mod y la identidad interna del gestor, sin sustituir silenciosamente versiones.
- Comprobar prioridad y desempate de carga frente al contrato de escritorio; conservar el orden que ya funciona.
- Probar dependencias presentes/ausentes, nombres duplicados, reimportación y configuración sin ejecutar modmain durante el descubrimiento.

### [M3 · Comunicación e interoperabilidad entre mods](https://github.com/AtherXyz/AtherMods-Community/issues/3)

- Probar eventos, hooks y API compartidas mediante un par de mods de prueba propios con resultados verificables.
- Comprobar require/modimport entre módulos de distintos propietarios y detectar colisiones sin elegir archivos arbitrarios.
- Verificar consultas de identidad y disponibilidad de otro mod, con alias explícitos para las identidades importadas.
- Verificar registro de RPC nativo cliente/servidor donde proceda, manteniendo separadas las instancias y los perfiles.
- Probar AtherKeybinds con un atajo de otro mod y la convivencia de Slots, Perspective y Medal; distinguir evento Lua de acción nativa.
- Mostrar incompatibilidades y dependencias antes de entrar, conservando datos de selección y diagnóstico por mod.

### [M4 · Optimización de CPU, tareas Lua y HUD](https://github.com/AtherXyz/AtherMods-Community/issues/4)

- Identificar los tres mayores costes medidos del escenario de referencia y separar CPU de GPU antes de modificar.
- Comparar indicadores de salud y números flotantes por separado; documentar funciones equivalentes y alternativas del perfil ligero.
- Reducir búsquedas globales o su frecuencia solo donde la medición lo justifique; comprobar eventos y respuesta de controles.
- Comprobar retirada de tareas, listeners y widgets propios al salir/reentrar para evitar acumulación.
- Comparar original y optimizado en tres repeticiones; objetivo inicial: reducir al menos un 20% el p95 del tiempo de fotograma en el escenario limitado por CPU.
- Validar que el cambio conserva mecánicas y guardados, y cuantificar el coste del propio diagnóstico.

### [M5 · Perfil de RAM reducida y calidad gráfica](https://github.com/AtherXyz/AtherMods-Community/issues/5)

- Inventariar recursos de mayor coste y empezar por texturas de mods; conservar atlas, transparencias y avisos de autoría.
- Preparar una variante ligera reversible sin modificar el ZIP original ni confundir menor tamaño comprimido con menor memoria en ejecución.
- Comprobar carga sin texturas ausentes, formatos inválidos ni iconos/textos ilegibles.
- Medir PSS y pico con el mismo mundo/pack/cámara: objetivo inicial de al menos un 15% menos memoria PSS pico del proceso; separar memoria gráfica si el dispositivo la expone.
- Investigar resolución interna y reescalado por una ruta verificada del motor. Si no existe acceso compatible, registrar NO VIABLE en esta fase y conservar la opción desactivada.
- Completar 30 minutos y tres reentradas sin cierres ni crecimiento sostenido atribuible al cambio; registrar además el comportamiento térmico.

### [M6 · Alone de escritorio y persistencia individual](https://github.com/AtherXyz/AtherMods-Community/issues/6)

- Fijar versión y hashes de la base Steam 1.2.44 analizada y de los adaptadores Android necesarios; comparar cambios de guardado antes de combinarlos.
- Verificar que el modo de un solo mundo se activa únicamente en partidas individuales y coordina el arranque con el gestor.
- Confirmar la escritura antes de finalizar Guardar y salir, incluyendo la identidad de instantánea de mundo y personaje.
- Completar cinco ciclos de guardar/salir/cerrar proceso/reabrir en superficie y cinco en cuevas sin pérdida de progreso.
- Completar cinco viajes de ida y vuelta, comprobando inventario, construcciones de prueba, mapa explorado, ubicación y reloj del mundo.
- Probar recuperación de interrupciones sobre copias de prueba y conversión de formato cuando esté soportada; bloquear estados ambiguos sin cargar una instantánea antigua silenciosamente.

### [M7 · Menú nativo protagonista y diseño móvil](https://github.com/AtherXyz/AtherMods-Community/issues/7)

- Presentar una maqueta con acceso Mods/AM nativo y jerarquía clara de Biblioteca, Cliente, Mundo y Rendimiento.
- Obtener validación visual de Ather de esa maqueta antes de integrar su diseño.
- Mostrar estados distintos: importado, seleccionado, preparado, cargado y fallo; cada acción debe producir su estado real.
- Reordenar acciones principales, adaptar zonas seguras y escala en S23 Ultra y Z60, con marcos decorativos encima de iconos donde corresponda y hitboxes verificadas.
- Probar abrir/cerrar/configurar desde menú principal, selección de mundo y lobby, y comprobar el retorno del botón tras salir de partida.
- Conservar selección/configuración entre sesiones y mantener un recorrido normal sin consola ni comandos manuales.

### [M8 · Regresión, entrega y pruebas de comunidad](https://github.com/AtherXyz/AtherMods-Community/issues/8)

- Comparar el gestor previo y la candidata con los mismos mods y datos de prueba, sin sustituir versiones públicas anteriores.
- Completar la matriz de escenarios y arranques en S23 Ultra y Z60; separar pruebas automáticas, nativas observadas y confirmación física de Ather.
- Validar actualización conservando biblioteca/perfiles y comprobar recuperación de operaciones interrumpidas.
- Comprobar LAN entre dos móviles en modo multijugador normal; Alone individual queda fuera de ese modo.
- Publicar resultados medidos, cambios de calidad, funciones desactivadas, errores conocidos y casos no comprobados.
- Entregar APK/ZIP versionados, hashes y descargas directas con instrucciones para testers; reservar cualquier componente no validado como experimental.
- Mantener un formulario de feedback y trazabilidad entre cada resultado, issue y entrega.

## Arquitectura propuesta

- **Gestor:** imports, identidades, dependencias, perfiles, publicación del despliegue y diagnóstico.
- **Puente de arranque:** integración con los menús nativos y coordinación del ciclo de cliente, servidor y mundos.
- **Mod de interfaz/rendimiento:** ajustes reversibles de HUD y calidad; integración de herramientas Ather cuando proceda.
- **Modo Alone:** ruta individual separada, basada en la comparación con Steam y adaptada a los contratos móviles de guardado. Multijugador conserva su propia ruta.

## Herramientas y límites de investigación

- **REA:** inventario y comparación de artefactos del juego. La inspección estática no acredita ejecución ni ganancia de FPS.
- **Fuente Lua y pruebas de contrato:** comparación del cargador/selector nativo con el gestor, dependencias, hooks y persistencia.
- **ADB y Perfetto:** capturas de sistema, tiempos y memoria, según permisos y datos disponibles en cada teléfono. [Documentación de Perfetto](https://perfetto.dev/docs/).
- **Análisis GPU:** se evaluará una herramienta compatible con el dispositivo y la compilación si la medición apunta a GPU; no se presupone acceso a todos los contadores del original de Google Play.
- **Muestreo Lua acotado:** localizar tareas costosas sin mantener una instrumentación pesada durante el uso normal.

Mundos, ZIP originales, entregas públicas anteriores y perfiles de usuario se conservan. Las pruebas usan mundos nuevos o copias controladas. Reescalado, reducción de recursos nativos y apoyo a dispositivos con menos RAM quedan sujetos a viabilidad; no se ofrecerán como funcionales por añadir un botón.

## Estados y evidencia

- **PLANIFICADO:** alcance y criterios descritos.
- **EN ANÁLISIS:** hipótesis o mediciones en curso.
- **IMPLEMENTADO:** cambio de código realizado, sin asumir validación.
- **PASS AUTOMÁTICO:** pruebas de código aprobadas.
- **PASS NATIVO:** comportamiento observado en el juego, con entorno y evidencia.
- **PASS FÍSICO:** comprobación realizada por Ather en el teléfono.
- **BLOQUEADO / NO VIABLE / PARCIAL:** motivo y alcance publicados.

Una etapa se marca cerrada solo cuando sus criterios aplicables tienen evidencia y sus límites quedan documentados. No se suman compilaciones o votos como si fueran mejoras de rendimiento. La tabla y roadmap.json se actualizarán al cerrar entregas o incorporar evidencia; no hay automatización periódica configurada.

## Próximo paso

**M1: fijar la candidata y el pack de referencia, comprobar el arranque Samsung y medir.** La autorización de esta fase cubre el roadmap; el trabajo de implementación se inicia en la siguiente fase con Ather.
