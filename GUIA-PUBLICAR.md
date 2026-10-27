# Cómo publicar tu CV en internet (GitHub + Vercel)

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El contenido de la página (textos, secciones). Los navegadores abren siempre `index.html` primero. |
| `styles.css` | El diseño: colores, tamaños, cómo se ve en celular. |
| `img/foto.png` | Tu foto. |
| `cv-celina-guerra.pdf` | El CV en PDF para el botón "Descargar CV". |

**Verla en tu computadora:** doble clic en `index.html`; se abre en el navegador.
**Cambiar un texto:** abre `index.html` con el Bloc de notas (o VS Code), cambia el texto, guarda y recarga el navegador (F5).

---

## Paso 1 — Instalar Git

Git es el programa que guarda versiones de tus archivos y los sube a GitHub.

1. Descárgalo de https://git-scm.com/download/win e instálalo (deja todas las opciones por defecto).
2. **Cierra y vuelve a abrir** la terminal (PowerShell).
3. Comprueba que funciona:
   ```
   git --version
   ```
4. Dile a Git quién eres (solo se hace una vez):
   ```
   git config --global user.name "Celina Guerra"
   git config --global user.email "estherguerra570@gmail.com"
   ```

## Paso 2 — Crear una cuenta en GitHub

GitHub es un sitio donde se guarda el código en la nube.

1. Entra a https://github.com/signup y crea tu cuenta (usa tu correo).
2. Arriba a la derecha pulsa **+** → **New repository**.
3. Nombre: `cv-celina` · Márcalo como **Public** · **NO** marques "Add a README".
4. Pulsa **Create repository**. Deja esa página abierta: te muestra la dirección de tu repositorio, algo como
   `https://github.com/TU-USUARIO/cv-celina.git`

## Paso 3 — Subir los archivos a GitHub

En PowerShell, dentro de la carpeta del proyecto:

```
cd "D:\CELINA PAGINAS WEB"
git init                      # convierte la carpeta en un repositorio
git add .                     # prepara todos los archivos
git commit -m "Mi CV web"     # guarda una "foto" de los archivos
git branch -M main            # nombra la rama principal "main"
git remote add origin https://github.com/TU-USUARIO/cv-celina.git
git push -u origin main       # sube todo a GitHub
```

La primera vez se abrirá una ventana para iniciar sesión en GitHub: acéptala.
Recarga la página del repositorio en GitHub y verás tus archivos.

## Paso 4 — Publicar con Vercel

Vercel toma lo que está en GitHub y lo convierte en una página web con dirección propia. Es gratis.

1. Entra a https://vercel.com/signup → **Continue with GitHub**.
2. Pulsa **Add New…** → **Project**.
3. Busca `cv-celina` en la lista y pulsa **Import**.
4. En "Framework Preset" debe decir **Other** (no hace falta configurar nada más).
5. Pulsa **Deploy**. En unos segundos te da una dirección como
   `https://cv-celina.vercel.app` ✅

Para cambiar el nombre de la dirección: en Vercel, tu proyecto → **Settings** → **Domains**.

## Paso 5 — Actualizar el CV más adelante

Cada vez que cambies algo:

```
cd "D:\CELINA PAGINAS WEB"
git add .
git commit -m "Actualizo experiencia"
git push
```

Vercel detecta el cambio solo y actualiza la página en menos de un minuto.

---

## Ojo con la privacidad

La página será pública: cualquiera podrá ver tu teléfono, correo y distrito.
Es normal en un CV, pero si prefieres, puedes borrar el teléfono de `index.html` y dejar solo el correo y WhatsApp.
