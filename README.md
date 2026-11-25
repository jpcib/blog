# blog

Código fuente de [blog.juancib.ar](https://blog.juancib.ar), hecho con Quarto.

- Cada post vive en `posts/<fecha>-<slug>/` y es autosuficiente: su `index.qmd`, sus helpers en `R/` y su caché de datos en `data/` (no se versiona).
- Los posts llegan ya terminados desde su repo de proyecto (el laboratorio). El commit del post cita el tag de origen.
- `freeze: auto`: el código corre solo en local; `_freeze/` sí se versiona.

## Publicar

```bash
quarto preview                  # revisar
quarto render                   # genera _freeze/ de los posts nuevos o cambiados
git add -A && git commit -m "post: <título>"
git tag -a <slug> -m "<título>"
git push origin main --follow-tags
quarto publish gh-pages
```
