# ❄️ Snow — Asistente Personal

Plataforma modular de gestión personal con sincronización en OneDrive.

**URL:** https://immosortiz-cmd.github.io/snow/

## Módulos

| Módulo | Descripción | Ruta |
|---|---|---|
| 🏠 Hub | Dashboard central Snow | `/` |
| 💸 FinFlow | Gestión de finanzas personales | `/finflow/` |
| 🗄️ BackupMgr | Gestión de backups e imágenes de sistema | `/backupmgr/` |

## Estructura

```
snow/
├── index.html          ← Hub central
├── callback.html       ← OAuth compartido (OneDrive)
├── README.md
├── finflow/
│   └── index.html
└── backupmgr/
    └── index.html
```

## Configuración de Azure

1. Ir a [portal.azure.com](https://portal.azure.com) → Azure Active Directory → App registrations
2. Crear app → tipo **SPA**
3. Agregar permiso: `Files.ReadWrite`
4. Redirect URI: `https://immosortiz-cmd.github.io/snow/callback.html`
5. Copiar el **Client ID** y pegarlo en Snow Hub → Configuración

## Datos en OneDrive

- FinFlow: `/Apps/FinFlow/data.json`
- BackupMgr: `/Apps/BackupMgr/data.json`

El token OAuth es compartido entre todos los módulos — solo conectas una vez.
