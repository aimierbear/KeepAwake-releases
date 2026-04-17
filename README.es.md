# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

Una app para la barra de menús de macOS que controla el comportamiento de suspensión del MacBook con dos interruptores independientes: mantiene tu Mac despierto con la tapa cerrada y bloquea la suspensión por inactividad mientras trabajas.

> 📦 **Este repositorio solo distribuye el `.dmg` firmado y notarizado. El código fuente se encuentra en un repositorio privado.**

## ⬇️ Descarga

Última versión → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Cada `.dmg` está firmado con el Developer ID `C3SNXE45AV (Xiaoneng Wu)` y notarizado por Apple. El Gatekeeper de macOS lo acepta sin mostrar el diálogo de confirmación "descargado de internet".

## 🧰 Requisitos del sistema

- macOS 14 Sonoma o superior
- Apple Silicon o Intel

## ✨ Características

- **Despierto con tapa cerrada** — mantiene el Mac funcionando incluso con la tapa cerrada (requiere autorización de administrador la primera vez)
- **Evita suspensión por inactividad** — suprime la suspensión por inactividad mientras KeepAwake está en ejecución (IOKit assertion)
- **Temporizador de apagado automático** — 30 min / 1 / 2 / 4 / 8 horas
- **Inicio automático al iniciar sesión, recordar último estado, restablecer interruptores al salir**
- **Seguro ante fallos** — si la app se cierra inesperadamente, el helper restablece `disablesleep` a 0 después de 60 s
- **15 idiomas** — sigue el idioma del sistema macOS

## 📥 Instalación

1. Descarga `KeepAwake-0.2.0.dmg` desde la [última versión](../../releases/latest)
2. Haz doble clic en el DMG para montarlo y arrastra **KeepAwake.app** a `/Applications`
3. Inicia desde Launchpad o Aplicaciones
4. La primera vez que actives "Despierto con tapa cerrada", macOS pedirá permiso para añadir un elemento en segundo plano → haz clic en **Permitir**

## 🔐 Firma y notarización

- Developer ID: `Xiaoneng Wu (C3SNXE45AV)`
- Servicio de notarización de Apple: ✅ Aceptado
- Ticket sellado (funciona sin conexión, Gatekeeper puede verificarlo sin red)

## ⚠️ Riesgo de sobrecalentamiento con tapa cerrada — léelo

**La principal salida de calor del MacBook está bajo el teclado.** Cuando la tapa está cerrada y el portátil descansa plano sobre una superficie, el flujo de aire se restringe. Ejecutar cargas pesadas en este estado (exportación de vídeo, compilación, entrenamiento de ML, inferencia de IA prolongada, juegos) puede provocar:

- Thermal throttling de CPU/GPU → tu tarea en realidad se vuelve *más lenta*
- Envejecimiento acelerado de la batería por altas temperaturas prolongadas
- En casos extremos, apagado térmico o daño al hardware

**Uso seguro:**

- ✅ Apto para tareas **ligeras** en segundo plano — sincronización de archivos, descargas, mantener SSH / escritorio remoto, recepción AirPlay
- ⚠️ Para cargas **pesadas** con la tapa cerrada, eleva el portátil o usa un soporte con ventilación. **Nunca** lo coloques sobre una cama, manta, sofá, o dentro de una mochila.
- ❌ No combines "tapa cerrada + carga pesada + rejillas bloqueadas"

`Evita suspensión por inactividad` también anula el ahorro de batería. Actívalo solo cuando lo necesites, desactívalo cuando termines.

**KeepAwake no monitoriza temperatura ni carga. La gestión del riesgo depende de ti.**

## 🔒 Sobre el código fuente

El repositorio fuente es privado. Este repositorio solo existe para distribuir el DMG firmado y notarizado. Si necesitas acceso al código para auditoría o contribución, contacta con el autor.

## Licencia

Uso personal.
