# GoldenGate-x86-Research

Investigación documentada sobre si **macOS 27 “Golden Gate”** puede arrancar o ejecutar partes de su sistema en hardware **x86-64 no soportado**, usando como equipo de referencia un AMD Ryzen 7 5700G.

> Proyecto experimental e independiente. No está afiliado a Apple ni a OpenCore. No distribuye macOS ni imágenes del sistema.

## Objetivo

Determinar, con pruebas reproducibles, qué componentes de Golden Gate conservan compatibilidad con x86-64 y hasta qué etapa puede llegar el arranque en hardware no soportado. Separaremos los problemas de arquitectura/arranque de los controladores y la aceleración gráfica.

Documentaremos también los intentos fallidos. Un resultado negativo es útil si se anotan la configuración, los cambios y el error observado.

## Estado actual

- **Tahoe 26.3:** funciona actualmente en el equipo de referencia.
- **Tahoe 26.6:** funcionó anteriormente en ese mismo equipo.
- **Golden Gate 27:** todavía no se ha probado en el Ryzen.
- **Golden Gate 27.0 (build 26A428):** apareció en el listado de productos de `gibMacOS`; confirmar en la bitácora si la descarga terminó y registrar su hash antes de analizar archivos.
- **Tahoe 26.6 (build 25G72):** apareció en el mismo listado. La conversación previa indicó que se inició su descarga; el estado final está pendiente de confirmar.

Los detalles conocidos y lo que falta confirmar están en [docs/environment.md](docs/environment.md) y [docs/timeline.md](docs/timeline.md).

## Equipo de referencia

| Componente | Información conocida |
|---|---|
| CPU | AMD Ryzen 7 5700G |
| Gráficos | Radeon integrada del Ryzen 7 5700G |
| Memoria | 32 GB RAM |
| Sistema funcional actual | macOS Tahoe 26.3 |
| Sistema probado anteriormente | macOS Tahoe 26.6 |

Los datos desconocidos (placa, SMBIOS, configuración de OpenCore, almacenamiento y periféricos) se añadirán cuando se recopilen. No se publicarán números de serie ni identificadores privados.

## Plan de investigación

1. Registrar el entorno y conservar copias de seguridad; no experimentar sobre la instalación funcional.
2. Confirmar procedencia, versión/build y SHA-256 de cada descarga. Mantener los instaladores e imágenes localmente.
3. Inspeccionar y comparar componentes de Tahoe 26.3/26.6 y Golden Gate 27 (por ejemplo, arquitectura de binarios y presencia de componentes x86-64).
4. Formular una hipótesis verificable antes de cada cambio.
5. Hacer un experimento por vez, guardar el registro y documentar el resultado, incluidos los fallos.
6. Publicar métodos y hallazgos reproducibles, distinguiendo observaciones de hipótesis.

## Estructura

```text
README.md
.gitignore
docs/
  environment.md
  timeline.md
  findings.md
  experiments/
    TEMPLATE.md
```

## Privacidad y archivos grandes

Este repositorio guarda documentación, scripts pequeños y hashes. **No subir** imágenes RAW, DMG, PKG, instaladores, firmware ni otros archivos de macOS. Revisa `git status` antes de cada commit; `.gitignore` excluye formatos habituales, pero no sustituye esa revisión. No publiques datos personales, números de serie, UUID, tokens ni archivos EFI con identificadores privados.

## Cómo contribuir a la bitácora

- Añade los hechos nuevos a `docs/timeline.md`.
- Registra conclusiones verificables en `docs/findings.md`.
- Copia `docs/experiments/TEMPLATE.md` para cada prueba y usa nombres como `001-tahoe-26-6-baseline.md`.
- Marca claramente `Observación`, `Hipótesis` y `Conclusión`; no presentes una suposición como hecho.

## Licencia

Aún no se ha elegido una licencia. Hasta que se añada una, no se concede permiso general para reutilizar el contenido del repositorio.
