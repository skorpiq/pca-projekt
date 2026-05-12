# Analýza hlavných komponentov (PCA)

**Autor:** Artem Vara &nbsp;**Predmet:** Softvér na analýzu údajov R

Projekt skúma metódu redukcie dimenzionality **Principal Component Analysis (PCA)** na datasete automobilov `mtcars`. Ukazuje, ako je možné zredukovať 11-rozmerný priestor premenných na 2–4 hlavné komponenty, ktoré zachovávajú viac ako 85% celkovej variability dát. Matematicky vychádza zo spektrálneho rozkladu kovariančnej matice:

$$\mathbf{C}\,\mathbf{v}_i = \lambda_i\,\mathbf{v}_i, \qquad \text{PVE}_k = \frac{\lambda_k}{\sum_i \lambda_i}\times 100\%$$

**Link:** https://skorpiq.github.io/pca-projekt/

---

## Štruktúra projektu

```
.
├── pca_projekt.qmd          # technická správa (HTML + PDF)
├── pca_prezentacia.qmd      # prezentácia revealjs (10 slajdov)
├── pca_dashboard.qmd        # Quarto dashboard (interaktívny)
├── references.bib           # bibliografia
├── styles.css               # vlastné CSS pre prezentáciu
└── _quarto.yml              # konfigurácia projektu
```

---

## Obsah projektu

| Časť | Popis |
|---|---|
| 📄 **Technická správa** | Motivácia, matematické pozadie, kód v R, výsledky, záver |
| 📊 **Prezentácia** | 10 slajdov: od problému po interpretáciu komponentov |
| 📈 **Dashboard** | Interaktívny scree plot, biplót, tabuľka dát (plotly) |

---

## Kľúčové výsledky

- PC1 + PC2 vysvetľujú **~70%** celkovej variability datasetu
- Prvé 4 komponenty pokrývajú **>85%** variability
- PCA odhalila jasnú separáciu manuálnych a automatických vozidiel
- PC1 interpretujeme ako **„silu vozidla"** (hp, disp, cyl, wt)

---

## Lokálny build

```r
# 1. Inštalácia závislostí (raz)
install.packages(c("ggplot2", "ggfortify", "dplyr", "tidyr",
                   "plotly", "knitr", "kableExtra"))
```

```bash
# 2. Render celého projektu
quarto render pca_projekt.qmd
quarto render pca_prezentacia.qmd
quarto render pca_dashboard.qmd
```

Vygenerované HTML súbory je možné otvoriť priamo v prehliadači.

---

## Použité nástroje

| Nástroj | Verzia | Účel |
|---|---|---|
| R | ≥ 4.3 | výpočty a vizualizácia |
| Quarto | ≥ 1.4 | renderovanie dokumentov |
| ggplot2 | ≥ 3.4 | statická vizualizácia |
| plotly | ≥ 4.10 | interaktívne grafy |
| ggfortify | ≥ 0.4 | PCA biplót |

---

## Licencia

Tento projekt je dostupný pod [MIT licenciou](LICENSE).
