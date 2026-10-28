# Ather Mods · DST Pocket para Android

Un gestor para importar tus mods y elegirlos desde los menús nativos de **Don't Starve Together: Pocket Edition**, usando el juego original de Google Play.

Estamos buscando testers. La versión actual es **0.10.1-alpha39**: ya conseguimos entrar en partida con mods de cliente y servidor. Queremos comprobar cómo se comporta en más teléfonos.

## Descargas

- **[Descargar Ather Mods 0.10.1-alpha39 APK](https://github.com/AtherXyz/AtherMods-Community/releases/download/v0.10.1-alpha39/AtherMods-0.10.1-alpha39.apk)**
- [Descargar mods individualmente](MODS.md)
- [Versión, archivos y notas de entrega](https://github.com/AtherXyz/AtherMods-Community/releases/tag/v0.10.1-alpha39)
- [Instalación y primera prueba](TESTERS.md)
- [Progreso y límites actuales](PROGRESO.md)
- **[Roadmap medible: interfaz, compatibilidad y rendimiento](ROADMAP.md)**
- [Cuadro general y votos 👍](https://github.com/AtherXyz/AtherMods-Community/issues/9)
- [Reportar un error](https://github.com/AtherXyz/AtherMods-Community/issues/new?template=error.yml)

## Qué necesitamos para probar

El juego original **Google Play 2.3.1 (100)** (`com.playdigious.dst`), Shizuku activo y autorizado para Ather Mods, y tus ZIP de mods. La integración está preparada para esa versión concreta del juego. Las pruebas actuales son de Android 15 y 16; otros dispositivos y versiones siguen pendientes.

En Ather Mods importas los ZIP y pulsas **Abrir juego con mods**. Dentro del juego, **AM** abre el selector de mods de cliente. Los mods de servidor se eligen en **Mods**, desde los ajustes del mundo, antes de abrirlo.

## Lo que ya pasó

- Z60 / NX721J, Android 15, alpha39: Perspective + Ather Slots + Functional Medal cargados en la misma partida.
- S23 Ultra, Android 16, alpha36: entrada en un mundo con 17 mods, ocho de cliente y nueve de servidor.
- Menús nativos, selecciones guardadas y carga sin escribir comandos.
- Superficie y cuevas cargaron sus perfiles en las pruebas indicadas. El recorrido entre ambas sigue pendiente.

**Esto confirma la entrada en partida.** Todavía estamos comprobando las funciones de cada mod, la estabilidad prolongada y el multijugador entre teléfonos. En Samsung hubo arranques intermitentes y Perspective conserva avisos de texturas. Consulta [los detalles](PROGRESO.md).

En Nubia, configura **Ather Mods → Uso de batería → Optimización de la batería → Ejecución en segundo plano → Permitir**. Fue necesario para que el sistema mantuviera el gestor activo durante la carga.

Este repositorio reúne las entregas, instrucciones y seguimiento para testers. El juego se obtiene por separado en [Google Play](https://play.google.com/store/apps/details?id=com.playdigious.dst). Ather Mods es un proyecto independiente de Klei y Playdigious. Los créditos de los mods se conservan en sus ZIP y en [el catálogo](MODS.md).
