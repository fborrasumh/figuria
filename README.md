# FigurIA

**Figuras matplotlib listas para publicar.** Aplicación web de un solo fichero que
convierte datos en bruto en una figura científica: cinco agentes planifican, escriben,
ejecutan y critican el script de matplotlib hasta que la lámina está lista.

App: https://fborrasumh.github.io/figuria/

## Cómo funciona

| Agente | Función |
|---|---|
| Retriever | Detecta la familia de gráfico y activa la guía de estilo del destino editorial |
| Planner | Fija el mensaje, los ejes, las series, la incertidumbre y lo que se omite |
| Stylist | Traduce las normas de la revista en `figsize`, paleta y `rcParams` |
| Visualizer | Escribe el script matplotlib con los datos incrustados literalmente |
| Critic | Mira la figura renderizada y puntúa fidelidad, concisión, legibilidad y estética |

El script se ejecuta **de verdad** en el navegador con matplotlib vía Pyodide
(numpy, matplotlib, pandas), así que el crítico juzga la imagen real y no una
descripción. Si el código falla, se repara automáticamente con el traceback; si la
crítica pide cambios, se revisa y se vuelve a renderizar, conservando la versión con
mejor puntuación.

## Uso

Abre la app, pega tu clave de OpenAI (se guarda solo en tu navegador, en `localStorage`),
pega los datos, describe la figura y lanza el pipeline. Salidas: PNG, script `.py`
autónomo y traza JSON completa del proceso.

Estilos de destino disponibles: NeurIPS/ICML, Nature/Science, IEEE a doble columna,
revista biomédica y diapositiva.

## Método

El diseño del pipeline se inspira en **PaperBanana** (Zhu et al., arXiv:2601.23265),
en concreto en su rama de gráficos estadísticos generados por código, que es donde el
trabajo original observa mayor fidelidad numérica frente a la generación de imagen.

## Autoría

Fernando Borrás Rocher — Universidad Miguel Hernández de Elche
ORCID [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

Licencia MIT. Parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).
