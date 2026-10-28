# Progreso · 27 de octubre de 2026

## Implementado

- Importación y conservación de ZIP en la biblioteca del gestor.
- Integración con el original de Google Play 2.3.1 (100).
- Acceso AM al selector nativo de cliente, disponible también en la selección de personaje antes de entrar en partida.
- Selección de pack de servidor desde los ajustes del mundo.
- Registro de perfiles y selecciones entre sesiones; validaciones de identidad al abrir mundos.
- Carga temprana de Functional Medal en cliente, superficie y cuevas.
- Diagnóstico exportable y recuperación de arranques que no llegan a confirmar la preparación.

## Pruebas realizadas

| Entorno | Versión del gestor | Resultado observado |
| --- | --- | --- |
| Z60 / NX721J · Android 15 | alpha39 | Partida con Perspective, Ather Slots y Functional Medal. Los dos modmain de cliente y el runtime confirmaron LOADED. Medal cargó 463 prefabs con cero fallos declarados y cero dependencias ausentes en roles 0, 2 y 3. |
| S23 Ultra · Android 16 | alpha36 | Entrada con ocho mods de cliente y nueve de servidor, superficie y cuevas generadas, sin pantalla Lua de incompatibilidad en la prueba conjunta. |
| Laboratorio · Android 15 | Entregas anteriores | Pruebas acotadas de guardado y reentrada con el perfil de Functional Medal y Perspective. No equivalen a validar todos los packs en todos los teléfonos. |

En Z60, el sistema terminaba el gestor en segundo plano. Tras cambiar su política de batería a **Permitir**, el gestor permaneció activo y se completó la carga conjunta. También se corrigió la consulta del estado de congelación de procesos para la versión concreta de Nubia analizada; no demuestra soporte para todas las ROM de Nubia.

## Lo que falta

- Repetir el pack de 17 mods con alpha39 en ambos teléfonos.
- Revisar las funciones y controles de cada mod; la prueba actual confirma entrada, no compatibilidad completa.
- Resolver los avisos de texturas de Perspective.
- Mejorar la fiabilidad del arranque en Samsung: hubo intentos recuperados por terminación de Binder durante la congelación del proceso.
- Validar descenso, ascenso y reentrada con cuevas en teléfonos.
- Validar multijugador LAN entre dos teléfonos y los perfiles de invitados para packs de varios mods.
- Ampliar pruebas de persistencia, recuperación de mundos cuya creación se interrumpió y sesiones largas.
- Ampliar dispositivos, versiones de Android y versiones del juego.

El objetivo es elegir mods desde el propio juego, conservarlos por mundo y entrar de forma natural, sin consola ni comandos. Esta entrega es una **alpha para testers**.

## Próxima evolución

[Roadmap de interfaz, compatibilidad y rendimiento](ROADMAP.md): lista de diez tareas con casillas de progreso, ocho etapas y 49 criterios verificables. Plan publicado el 28 de octubre de 2026; implementación de este alcance pendiente. No modifica el estado de las pruebas de alpha39 descritas arriba.
