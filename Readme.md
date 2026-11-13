# calculadora-fatiga

Código de apoyo del artículo *Verification of an Open-Source Python Ecosystem for Mechanical Fatigue Analysis Against Analytical and Finite-Element Solutions Under Combined Bending–Torsion Loading* (Results in Engineering).

Caso de estudio: eje escalonado de acero estructural (Sut = 460 MPa, Sy = 250 MPa; D = 50 mm, d = 30 mm, r = 3 mm) bajo flexión y torsión combinadas.

## Contenido

| Archivo | Descripción |
|---|---|
| `notebook/P1-carga_var_amp_cte.ipynb` | P1: amplitud constante, en fase. Factores de seguridad (Goodman, Soderberg, ASME, Gerber, Langer). |
| `notebook/P2-cargas_amp_var_propor_fase.ipynb` | P2: amplitud variable, en fase. Rainflow ASTM E1049 y daño de Palmgren–Miner. |
| `notebook/P3-amp_var_no_prop_desfase.ipynb` | P3: amplitud variable, fuera de fase. Plano crítico de Findley con rainflow por plano. |
| `app.py` | Calculadora web (Streamlit) del caso P1. |
| `requirements.txt` | Dependencias. |

## Cómo ejecutar

**En Google Colab:** abra el cuaderno desde GitHub (Archivo → Abrir cuaderno → GitHub) y ejecute las celdas. En P2 y P3 ejecute antes `!pip install rainflow`.

**Calculadora local:**
```
pip install -r requirements.txt
streamlit run app.py
```

## Resultados esperados (con las entradas por defecto)

| Caso | Resultado |
|---|---|
| P1 | σ′a = 58,01 MPa; σ′m = 43,08 MPa; n Goodman = 2,006; esfuerzo estático en la muesca = 103,65 MPa |
| P2 | 7948 bloques (conteo estricto); 6610 bloques (historia cerrada) |
| P3 | plano crítico θ = 162°; daño por bloque 5,2×10⁻⁵; vida ≈ 19 200 bloques |

## Librerías
NumPy, Matplotlib, [rainflow](https://github.com/iamlikeme/rainflow) (conteo ASTM E1049-85), Streamlit.

## Licencia
MIT (ver `LICENSE`).

## Cita
Acosta, R. (2026). calculadora-fatiga [software]. https://github.com/ricostata/calculadora-fatiga
