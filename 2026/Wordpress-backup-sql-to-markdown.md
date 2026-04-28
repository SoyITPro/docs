# WordPress SQL to Hugo Ultimate Migrator



Migrador avanzado para convertir un backup `.sql` de WordPress a una estructura completamente funcional para Hugo Static Site Generator, incluyendo:

- ✅ Conversión de posts a Markdown
- ✅ Recuperación de categorías
- ✅ Recuperación de tags
- ✅ Recuperación de autores
- ✅ Reconstrucción de imágenes embebidas dentro del contenido
- ✅ Recuperación de Featured Images (thumbnails destacadas)
- ✅ Copia automática de la carpeta uploads a static/uploads
- ✅ Front Matter profesional compatible con Hugo
- ✅ Limpieza de HTML innecesario de WordPress

---

# ¿Qué problema resuelve?

Si tienes un blog de WordPress antiguo y solamente conservas:

- el backup de base de datos `.sql`
- y la carpeta `wp-content/uploads`

este script te permite reconstruir prácticamente todo el blog para migrarlo a:

- Hugo
- GitHub Pages
- Netlify
- Cloudflare Pages
- cualquier hosting estático

sin necesidad de volver a instalar WordPress.

---

# Estructura esperada de archivos

Debes tener una carpeta de trabajo similar a esta:

```text
wordpress-recovery/
│
├── jgaitpro_wpblog.sql
├── wordpress_sql_to_hugo_ultimate.py
└── uploads/
    ├── 2015/
    ├── 2016/
    ├── 2017/
    └── ...
```

### Requisitos
1. Instalar Python 3 en Windows/Linux/Mac

Descargar Python desde:

https://www.python.org/downloads/

Durante la instalación en Windows recuerda marcar: Add Python to PATH

2. Instalar dependencias necesarias

Abrir CMD / PowerShell / Terminal y ejecutar:
``` powershell
py -m pip install markdownify beautifulsoup4
```
o en Linux/Mac:
``` bash
python3 -m pip install markdownify beautifulsoup4
```

#### ¿Cómo ejecutar el script?
Ubícate dentro de la carpeta wordpress-recovery y ejecuta:

- En Windows
``` powershell
python wordpress_sql_to_hugo_ultimate.py
```
- En Linux / Mac
``` bash
python3 wordpress_sql_to_hugo_ultimate.py
```

#### ¿Qué genera el script?

Al finalizar tendrás esta estructura:
``` text
wordpress-recovery/
│
├── content/
│   └── posts/
│       ├── articulo-1.md
│       ├── articulo-2.md
│       └── ...
│
└── static/
    └── uploads/
        ├── 2015/
        ├── 2016/
        └── ...
```

### ¿Qué contiene cada archivo Markdown?

Cada post se exporta con Front Matter profesional para Hugo:

---
``` text
title: "Nombre del artículo"
date: 2018-07-15 10:22:00
slug: nombre-del-articulo
author: "admin"
featured_image: "/uploads/2018/07/imagen-destacada.jpg"
categories:
  - Windows Server
  - Active Directory
tags:
  - DNS
  - GPO

  ```
---

## Referencias

- **Script original**: [wordpress_sql_to_hugo.py](https://github.com/SoyITPro/scripts/blob/main/miscellany/wordpress_sql_to_hugo.py)


