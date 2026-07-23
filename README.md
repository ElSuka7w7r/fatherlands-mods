# Fartherlands (Packwiz)

Modpack cliente **Minecraft 1.21.1 Â· Fabric 0.19.2** para el servidor Fartherlands.

Los mods de CurseForge/Modrinth se bajan solos; en el repo solo van metadatos (`.pw.toml`), configs y mods custom pequeÃ±os.

## Requisitos (admin del pack)

1. [Go](https://go.dev/dl/) instalado  
2. Packwiz:

```powershell
go install github.com/packwiz/packwiz@latest
# Asegura que %USERPROFILE%\go\bin estÃ© en el PATH
```

## Estructura

| Ruta | QuÃ© es |
|------|--------|
| `pack.toml` | Nombre, MC, Fabric |
| `index.toml` | Ãndice + hashes (no editar a mano) |
| `mods/*.pw.toml` | De dÃ³nde bajar cada mod |
| `mods/aot-*.jar` | Mods custom (por ahora en el repo) |
| `config/` | Configs compartidas |
| `resourcepacks/` / `shaderpacks/` | Packs / metadatos de shaders |

## Comandos Ãºtiles

```powershell
cd C:\Users\Timon\fartherlands-pack

# Tras editar configs o jars locales:
packwiz refresh

# Actualizar todos los mods CF/MR:
packwiz update --all

# AÃ±adir un mod:
packwiz curseforge add slug-o-url -y
packwiz modrinth add slug-o-url -y

# Probar en local (URL para Prism):
packwiz serve
# â†’ http://127.0.0.1:8080/pack.toml
```

## Subir a GitHub (tÃº creas el repo)

```powershell
cd C:\Users\Timon\fartherlands-pack
git init
git add .
git commit -m "Initial Fartherlands packwiz pack"
git branch -M main
git remote add origin https://github.com/ElSuka7w7r/fatherlands-mods.git
git push -u origin main
```

URL pÃºblica del pack (ajusta user/repo):

```text
https://raw.githubusercontent.com/ElSuka7w7r/fatherlands-mods/main/pack.toml
```

Si el repo es **privado**, usa un token o hostea con otro HTTP; Prism necesita poder leer esa URL.

## Jugadores (Prism Launcher)

1. Instalar [Prism Launcher](https://prismlauncher.org/)  
2. Crear instancia â†’ Minecraft **1.21.1** + Fabric **0.19.2**  
3. Seguir: [packwiz-installer](https://packwiz.infra.link/tutorials/installing/packwiz-installer/)  
4. Pegar la URL de `pack.toml`  
5. Al abrir la instancia se sincronizan mods/configs  

## Mods custom â†’ GitHub Releases (recomendado despuÃ©s)

Ahora `aot-eat-fix` y `aot-opac-protect` van como JAR en `mods/` (pesan poco).

Cuando tengas Releases:

```powershell
# Ejemplo (cambia owner/repo/tag/asset):
packwiz url add "https://github.com/TU_USER/aot-eat-fix/releases/download/v1.1.5/aot-eat-fix-1.1.5.jar" -y
# o:
packwiz github add TU_USER/aot-eat-fix -y
```

Luego borra el `.jar` local del repo, actualiza `.gitignore` y `packwiz refresh`.

## Notas

- Packwiz **no** gestiona premium/no premium; eso lo hace el launcher y el servidor.  
- No subas `saves/`, mundos ni logs.  
- Tras cambiar algo del pack: `packwiz refresh` â†’ `git commit` â†’ `git push`.
