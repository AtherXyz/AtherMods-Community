# Probar Ather Mods

## Preparación

1. Instala el juego original de Google Play 2.3.1 (100) y ábrelo normalmente. Completa su verificación de cuenta.
2. Instala la APK enlazada en el README. Si actualizas Ather Mods, hazlo sobre la instalación existente para conservar la biblioteca.
3. Inicia [Shizuku](https://shizuku.rikka.app/) y autoriza Ather Mods.
4. Permite que Ather Mods siga ejecutándose en segundo plano. En Nubia, cambia su opción de batería de Automático a Permitir.
5. Descarga los ZIP que quieras probar desde [Mods](MODS.md) e impórtalos con **Importar ZIP**. Conserva el ZIP sin descomprimir.

## Primera partida

1. Guarda y sal de cualquier partida abierta antes de iniciar la sesión desde el gestor.
2. Pulsa **Abrir juego con mods** y confirma que ya has guardado y salido. El gestor reinicia el juego para preparar la sesión.
3. En el menú del juego, pulsa **AM**, selecciona tus mods de cliente y guarda la selección.
4. Para probar mods de servidor, importa la versión de Functional Medal de este catálogo. Es la base requerida por el pack de servidor actual.
5. Crea un mundo nuevo de prueba, selecciona **Local Only** y abre **Mods** en sus ajustes. Activa y guarda el pack de servidor antes de generar el mundo.
6. En esta alpha, los mods de servidor importados forman un pack: se activa completo o se deja desactivado. No se pueden alternar libremente todos por separado. Los mods de cliente se eligen desde AM.
7. Entra en partida y comprueba el HUD, los controles y las funciones que uses. Deja Shizuku y Ather Mods activos.

Usa primero un mundo nuevo de prueba. Una partida que ya guardó contenido de un mod necesita conservar su perfil al volver a abrirse. La sesión del gestor dura hasta dos horas; la biblioteca y las selecciones se conservan entre sesiones.

## Si algo falla

Vuelve al gestor y pulsa **Exportar registro de diagnóstico**. Abre un [reporte](https://github.com/AtherXyz/AtherMods-Community/issues/new?template=error.yml) con modelo del teléfono, versión de Android, versión del gestor, mods activos y pasos para reproducirlo. Revisa el TXT antes de adjuntarlo: el filtrado automático no sustituye esa revisión. Evita incluir datos de tu cuenta o partidas personales.

- **AM no aparece o los clientes quedan esperando:** comprueba que Shizuku y Ather Mods siguen activos; revisa las restricciones de batería del teléfono.
- **E_INVALID_TOKEN:** el servidor rechazó la sesión de cuenta. Sal de forma normal y vuelve a abrir el juego para renovar su autenticación.
- **Pending modded creation / identity recovery:** conserva esa partida y adjunta el diagnóstico. No borres sus archivos ni la cargues a la fuerza sin su perfil.
- **Arranque recuperado o FAILED_RECOVERED:** exporta el diagnóstico. Es un resultado de recuperación, no una confirmación de carga de mods.

La prueba conjunta de 17 mods se hizo con alpha36 en S23 Ultra. Alpha39 incorpora ajustes del arranque del Z60; aún no hemos repetido ese pack completo en ambos teléfonos con alpha39.
