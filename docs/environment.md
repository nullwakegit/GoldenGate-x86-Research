# Entorno de referencia

## Equipo

| Campo | Dato |
|---|---|
| CPU | AMD Ryzen 7 5700G |
| GPU | Radeon integrada en el Ryzen 7 5700G |
| RAM | 32 GB |
| Placa base / BIOS | Pendiente de recopilar |
| SMBIOS | Pendiente; no publicar números de serie |
| OpenCore y configuración | Pendiente de recopilar |
| Almacenamiento | Pendiente de recopilar |

## Sistemas macOS

| Sistema | Build | Estado en este equipo | Procedencia / notas |
|---|---|---|---|
| Tahoe 26.3 | Pendiente | Funciona actualmente | Instalación existente; registrar build exacto cuando se consulte |
| Tahoe 26.6 | 25G72 | Funcionó anteriormente | Producto 140-71750 listado por `gibMacOS`; descarga final por confirmar |
| Tahoe 26.6.2 | 25G83 | No consta probado | Producto 140-93587 listado por `gibMacOS` |
| Golden Gate 27.0 | 26A428 | No probado | Producto 142-15488 listado por `gibMacOS`; descarga final por confirmar |

El listado mostrado por `gibMacOS` también incluía Tahoe 26.7 (25G229). No consta que se haya descargado o probado; no forma parte todavía de la línea base.

## Registro de cada imagen

Cuando se confirme una descarga, completar una ficha como esta (sin subir el archivo):

```text
Producto/build:
ID de catálogo o URL de fuente:
Fecha de descarga (UTC):
Nombre y tamaño local:
SHA-256:
Estado de verificación:
Ubicación local (opcional; no publicar rutas privadas):
```

Calcular el hash localmente, por ejemplo en macOS/Linux con `shasum -a 256 archivo` o en Windows PowerShell con `Get-FileHash archivo -Algorithm SHA256`. No compartir enlaces privados ni datos de cuenta.
