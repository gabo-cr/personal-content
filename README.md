# Contenidos personales

Repositorio de contenido estático independiente de `terminal-framework`. Los documentos se escriben en Markdown y se sirven mediante HTTP para que el framework pueda consultarlos.

## Organización

```text
config/
  site.json                     Identidad, bienvenida y tema
  commands.json                 Comandos personalizados
  content.json                  Colecciones y documentos
content/
  about.md                      Presentación
  contact.md                    Contacto
  engineering/
    intro.md                    Introducción a ingeniería
    first-solution.md           Primera solución
  writing/
    intro.md                    Introducción a escritura
    first-text.md               Primer texto
.nojekyll                       Desactiva Jekyll en GitHub Pages
```

Los textos marcados como **provisionales** y el nombre «Tu nombre» deben sustituirse por información real antes de publicarlos como contenido definitivo.

Los tres JSON respetan los esquemas Zod implementados en `terminal-framework`. Las rutas Markdown son relativas a la raíz publicada, sin `/` inicial. La colección `literature` utiliza los archivos de `content/writing/`. Los listados siguen el orden de los arrays declarados en la configuración.

## Publicación

Publica la raíz del repositorio en un alojamiento estático que sirva los archivos por HTTP, conservando las rutas `content/` y `config/`. Por ejemplo, en GitHub Pages selecciona la rama que contiene estos archivos y la carpeta raíz (`/`) como origen de publicación; `.nojekyll` evita el procesamiento con Jekyll.

Configura `VITE_CONTENT_BASE_URL` en el framework con la URL HTTPS de la raíz publicada. No se requiere compilación, instalación de dependencias ni backend en este repositorio.
