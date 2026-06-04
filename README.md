# Global Solution — Modelagem Linear para Aprendizagem de Máquina
**FIAP · Ciência da Computação · Turmas 1CC · 2025**

---

## Descrição da Solução

Este projeto realiza análise estatística descritiva sobre dados reais de **telemetria de satélites**, com foco em identificar padrões operacionais e comportamentos anômalos em segmentos de sinal captados por sensores embarcados.

O objetivo é transformar dados brutos de telemetria em informações úteis para suporte à tomada de decisão em operações de sistemas espaciais — alinhado ao contexto da nova economia espacial.

---

## Base de Dados

| Item | Detalhe |
|------|---------|
| **Nome** | Satellite Telemetry Data — Anomaly Prediction |
| **Fonte** | [Kaggle](https://www.kaggle.com/) |
| **Formato** | CSV |
| **Amostra** | 100 registros (random_state=100) |

### Variáveis analisadas
- `mean` — Média aritmética dos valores do segmento de sinal **(quantitativa contínua)**
- `n_peaks` — Número de picos detectados no segmento **(quantitativa discreta)**

---

## Estrutura do Repositório

```
├── dataset.csv                  # Base de dados original
├── GS_MLAM.ipynb                # Notebook com todo o código Python
├── Relatorio_GS_MLAM.pdf        # Relatório estatístico final
└── README.md                    # Este arquivo
```

---

## O que foi desenvolvido

### 01. Justificativa da Base de Dados
Dataset real de telemetria espacial com variáveis contínuas e discretas, adequado para análise estatística descritiva e modelagem preditiva.

### 02. Tabelas de Distribuição de Frequências
- Variável contínua (`mean`): agrupada em 8 classes com frequência absoluta e relativa
- Variável discreta (`n_peaks`): frequência por valor com acumulada

### 03. Gráficos Estatísticos
- Histograma da distribuição de `mean` (8 bins)
- Gráfico de barras da frequência de `n_peaks`

### 04. Análise Univariada — Estatística Descritiva
Para cada variável: média, mediana, moda, máximo, mínimo, amplitude, variância, desvio padrão e quartis (Q1, Q2, Q3).

### 05. Relatório Técnico
Interpretação crítica dos resultados com identificação de padrões, limiares de alerta e recomendações para uso em modelos de Machine Learning.

---

## Como Executar

1. Faça o upload do `dataset.csv` no Google Colab em `/content/dataset.csv`
2. Abra o arquivo `GS_MLAM.ipynb` no Google Colab
3. Execute todas as células em sequência (**Runtime → Run all**)

---

## Principais Resultados

| Variável | Média | Mediana | Moda | Desvio Padrão |
|----------|-------|---------|------|---------------|
| `mean`   | 0.1437 | ~0.0000046 | ~0.0000046 | 0.2323 |
| `n_peaks`| 1.40 | 1.0 | 1 | 0.8288 |

**Insight principal:** 75% dos segmentos possuem `mean` abaixo de 0.23 e 93% apresentam no máximo 2 picos — valores acima desses limiares são candidatos a anomalias.

---

*FIAP · Global Solution 2025*
