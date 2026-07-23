# Mods custom

| Archivo | Notas |
|---------|--------|
| `mods/aot-eat-fix-1.1.5.jar` | VIP / eat fix Fartherlands |
| `mods/aot-opac-protect-1.3.1.jar` | Protección OpenPAC |

## Flujo cuando crees el repo de Releases

1. Sube el JAR a un Release (ej. tag `v1.1.5`).
2. En esta carpeta del pack:

```powershell
packwiz remove aot-eat-fix
packwiz github add TU_USER/REPO -y
# o packwiz url add URL_DIRECTA_DEL_JAR -y
packwiz refresh
```

3. Quita el jar de `mods/` del Git y haz push.
