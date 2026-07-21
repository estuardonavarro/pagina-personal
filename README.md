# Tu página personal

Sitio estático (HTML/CSS puro, sin frameworks, sin paso de build). Se puede hospedar
gratis de forma indefinida — el único costo recurrente que tendrás es la renovación
de tu dominio, que ya pagas aparte.

## Antes de publicar

1. Abre `index.html` y reemplaza los textos marcados como ejemplo: apellido, correo,
   LinkedIn, GitHub, y las tarjetas de "Proyectos".
2. Revisa `blog/primer-post.html`: bórralo o conviértelo en tu primera entrada real.
3. Para agregar entradas nuevas al blog: copia `blog/primer-post.html`, edítalo, y
   enlázalo desde `blog/index.html`.

## Opción recomendada: GitHub Pages (gratis, sin límite de tiempo)

1. Crea una cuenta en [github.com](https://github.com) si no tienes una.
2. Crea un repositorio público (puede llamarse como quieras, p. ej. `pagina-personal`).
3. Sube estos archivos al repositorio (arrastrándolos en la interfaz web de GitHub,
   o con `git push` si prefieres la terminal).
4. En el repositorio: **Settings → Pages → Source**: selecciona la rama `main` y
   la carpeta `/ (root)`. Guarda.
5. GitHub te dará una URL tipo `https://tu-usuario.github.io/pagina-personal/`.
   Verifica que todo se vea bien ahí antes de conectar tu dominio.

### Conectar tu dominio propio

1. En el repositorio, crea un archivo llamado `CNAME` (sin extensión) en la raíz,
   con una sola línea: tu dominio, por ejemplo:
   ```
   javier.gt
   ```
2. En el panel de tu proveedor de dominio (donde lo compraste), agrega estos
   registros DNS:
   - Cuatro registros **A** en la raíz (`@`) apuntando a:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Un registro **CNAME** para `www` apuntando a `tu-usuario.github.io`.
3. Espera la propagación (minutos a algunas horas).
4. Vuelve a Settings → Pages y activa **Enforce HTTPS** una vez que el dominio
   quede verificado — así el certificado SSL también es gratis.

## Alternativa: Cloudflare Pages (también gratis, CDN algo más rápido)

1. Crea cuenta en [pages.cloudflare.com](https://pages.cloudflare.com).
2. Conecta el mismo repositorio de GitHub.
3. Build command: déjalo vacío (no hay build). Output directory: `/` (raíz).
4. En "Custom domains", agrega tu dominio y sigue las instrucciones de DNS que
   te muestre Cloudflare (si tu dominio ya usa Cloudflare como DNS, es casi
   automático).

## Costo

- Hosting: **Q0** — tanto GitHub Pages como Cloudflare Pages son gratuitos sin
  límite de tiempo para un sitio de este tamaño y tráfico.
- Certificado SSL (candado/https): **Q0**, incluido en ambos.
- Lo único que ya pagas por separado: la renovación anual de tu dominio.

## Mantenimiento

No hay base de datos ni servidor que administrar. Para actualizar el sitio,
edita los archivos HTML y vuelve a subirlos (push) — no hay build ni despliegue
manual, GitHub/Cloudflare lo republican solos en cuanto detectan el cambio.
