# Fartherlands Mods (Launcher)

Repo de sync para el **Fartherlands Launcher**.

- `version.json` en `main` → el launcher compara la versión
- `modpack.zip` en **GitHub Releases** → mods + config + resourcepacks + shaderpacks

## Jugadores

Usa el launcher. No hace falta tocar este repo.

## Publicar una actualización

Desde la instancia CurseForge actualizada:

```powershell
cd C:\Users\Timon\curseforge\minecraft\Instances\Fartherlands\launcher
.\tools\build_modpack_zip.ps1 -Version 1.0.2 -SourceInstance "C:\Users\Timon\curseforge\minecraft\Instances\Fartherlands (1)"
```

1. Copia `dist\version.json` aquí, commit y push a `main`
2. Crea Release con tag `v1.0.2` y adjunta `dist\modpack.zip`

El launcher detecta la versión mayor, descarga el ZIP y reemplaza las carpetas del juego.
