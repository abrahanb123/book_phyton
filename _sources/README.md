# Análisis Exploratorio Bivariado – Diabetes (Jupyter Book)

Este repositorio contiene el notebook `notebooks/eda_bivariado_diabetes2.ipynb` convertido en un **Jupyter Book**, listo para publicarse como sitio web en GitHub Pages.

## Estructura

```
.
├── _config.yml              # Configuración del libro
├── _toc.yml                 # Tabla de contenidos
├── notebooks/
│   └── eda_bivariado_diabetes2.ipynb
├── requirements.txt         # Dependencia para construir el libro
└── .github/workflows/
    └── deploy.yml           # Publica automáticamente en GitHub Pages
```

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio en GitHub (o usa uno existente) y sube el contenido de esta carpeta a la rama `main`:

   ```bash
   git init
   git add .
   git commit -m "Jupyter Book: EDA bivariado diabetes"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
   git push -u origin main
   ```

2. En `_config.yml`, actualiza la línea `repository: url:` con la URL real de tu repositorio.

3. En GitHub, ve a **Settings → Pages** y selecciona como fuente la rama **gh-pages** (se crea automáticamente la primera vez que corre el workflow, carpeta `/ (root)`).

4. El workflow `.github/workflows/deploy.yml` se ejecuta automáticamente en cada `push` a `main`: construye el libro con Jupyter Book y publica el HTML resultante en la rama `gh-pages`.

5. Tras unos minutos, tu libro estará disponible en:
   `https://TU_USUARIO.github.io/TU_REPO/`

## Construir el libro localmente (opcional)

```bash
pip install "jupyter-book<2"
jupyter-book build .
```

El HTML generado quedará en `_build/html/index.html`, que puedes abrir directamente en el navegador para previsualizar.

## Notas

- El notebook se incluye con sus salidas (gráficos) ya guardadas, por lo que `execute_notebooks` está configurado como `"off"` en `_config.yml`: el libro **no** vuelve a ejecutar el notebook durante el build (no necesita el archivo `diabetes.csv` original).
- Si en algún momento quieres que el libro se ejecute y regenere los gráficos automáticamente, cambia `execute_notebooks: "off"` a `"auto"` en `_config.yml` y añade el dataset al repositorio junto con las dependencias necesarias (pandas, numpy, matplotlib, seaborn, scipy) en `requirements.txt`.
