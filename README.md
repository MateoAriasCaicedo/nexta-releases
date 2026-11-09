# Nexta â€” descargas

Repositorio **espejo** de Nexta: aquÃ­ se publican los instaladores y distribuibles.
El cÃ³digo fuente vive en un repositorio privado; este repositorio no contiene cÃ³digo.

## Canales

| Etiqueta | Artefactos | Para quiÃ©n |
| --- | --- | --- |
| `app-vX.Y.Z` | `Nexta-App-X.Y.Z.apk` (Android), `Nexta-POS_X.Y.Z_x64-setup.exe` (Windows), su firma `.sig` y `SHA256SUMS.txt` | Clientes y equipos de caja |
| `agent-X.Y.Z` | `NextaVenueAgent-X.Y.Z.exe` y `SHA256SUMS.txt` | InstalaciÃ³n del equipo local (servidor offline) del local |

- **Apps**: [Ãºltimas versiones](https://github.com/MateoAriasCaicedo/nexta-releases/releases?q=app-v)
- **Venue agent**: [Ãºltimas versiones](https://github.com/MateoAriasCaicedo/nexta-releases/releases?q=agent-)

## Actualizaciones automÃ¡ticas

Las apps **no** se actualizan desde este repositorio: Nexta POS y Nexta App leen sus manifiestos
del bucket pÃºblico `app-releases` de Supabase. Este repo es el canal de **descarga manual** y el
respaldo de los binarios.

## Verificar una descarga (Windows)

```powershell
Get-FileHash .\NextaVenueAgent-X.Y.Z.exe -Algorithm SHA256
Get-Content .\SHA256SUMS.txt
```

El valor debe coincidir con la lÃ­nea correspondiente de `SHA256SUMS.txt` (formato `sha256sum`).

## Notas

- `NextaVenueAgent` instala el hub local del local: incluye el backend compilado y las migraciones.
  EstÃ¡ destinado a soporte e instalaciÃ³n; no lo redistribuyas fuera de los canales de Nexta.
- Los instaladores de Windows no siempre estÃ¡n firmados: SmartScreen puede pedir
  "MÃ¡s informaciÃ³n â†’ Ejecutar de todos modos".
- La versiÃ³n publicada en cada canal es la Ãºnica soportada.

---

Publicado automÃ¡ticamente por la CI de Nexta. Este archivo se mantiene en el repositorio de origen.
