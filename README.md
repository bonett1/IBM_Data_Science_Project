# 🚀 SpaceX Falcon 9 — Análise Preditiva de Pousos

> Projeto final do **IBM Data Science Professional Certificate**  
> Previsão do sucesso de pousos do primeiro estágio para redução de custos via reutilização.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📋 Sobre o Projeto

O objetivo principal deste projeto é construir um modelo de Machine Learning capaz de **prever se o primeiro estágio do Falcon 9 pousará com sucesso**. A reutilização do booster reduz drasticamente o custo por lançamento, permitindo que concorrentes formulem propostas comerciais mais competitivas e mitiguem o risco de perdas milionárias ao identificar condições desfavoráveis de lançamento com antecedência.

---

## 🗂️ Estrutura do Pipeline

1. Coleta de Dados (API + Web Scraping)
2. Wrangling & Limpeza
3. Análise Exploratória (SQL + Visualização)
4. Análise Geoespacial (Folium)
5. Dashboard Interativo (Plotly Dash)
6. Modelagem Preditiva (Classification)

---

## 📦 Coleta de Dados

### REST API
- Chamada à API oficial da SpaceX (`v4/launches`)
- Decodificação via `pd.json_normalize()`
- Filtragem exclusiva de lançamentos do Falcon 9
- Tratamento de nulos e tipagem dos dados

### Web Scraping
- Requisição HTML da página de lançamentos do Falcon 9 (Wikipedia)
- Parsing com **BeautifulSoup**
- Mapeamento de cabeçalhos e linhas para dicionários → DataFrame estruturado

---

## 🔧 Wrangling

| Etapa | Descrição |
|---|---|
| Valores Nulos | Identificação com `.isnull()` |
| Imputação | Média aplicada em `PayloadMass` |
| Binary Mapping | `Classe`: 1 = Sucesso, 0 = Falha |
| Encoding | One-Hot Encoding em variáveis categóricas |

---

## 📊 Análise Exploratória

### SQL
- **CCAFS SLC-40** concentra o maior volume de operações
- Queries para massa total de carga e faixas críticas de peso
- Identificação do primeiro pouso bem-sucedido em solo

### Visualização (Python)
- Taxa de sucesso cresce com o número do voo (maturidade operacional)
- Órbitas **ES-L1, GEO, HEO e SSO** mantêm 100% de sucesso histórico
- Cargas pesadas operam majoritariamente em **KSC LC-39A**

---

## 🗺️ Análise Geoespacial

Usando **Folium Maps** para visualizar os locais de lançamento:

- Posicionamento costeiro estratégico para queda segura de detritos
- Proximidade < 1km de ferrovias e rodovias para transporte de boosters
- Distância segura de centros urbanos densamente populosos

---

## 📈 Dashboard Interativo

Construído com **Plotly Dash**:

- **KSC LC-39A** apresenta a melhor razão de sucesso por lançamento
- Faixa de carga ideal: **0–5.000 kg** com maior concentração de pousos seguros

---

## 🤖 Modelagem Preditiva

Todos os modelos foram otimizados via **GridSearchCV**.

| Modelo | Acurácia (Test Set) |
|---|---|
| Logistic Regression | 83.3% |
| SVM | 83.3% |
| Decision Tree | **83.3%** ⭐ |
| KNN | 83.3% |

> ✅ **Modelo recomendado:** Decision Tree — maior interpretabilidade para apresentações executivas.

---

## 🔑 Principais Conclusões

- **Local estratégico:** KSC LC-39A oferece a maior taxa de sucesso para pousos
- **Curva de aprendizado:** A taxa de acertos cresce com o número de voos, validando a engenharia iterativa da SpaceX
- **Alta previsibilidade:** Os modelos atingem **83,3% de acurácia** de forma consistente

---

## 🛠️ Tecnologias Utilizadas

- `Python` · `Pandas` · `NumPy` · `Scikit-learn`
- `BeautifulSoup` · `Requests`
- `Folium` · `Plotly Dash` · `Matplotlib` · `Seaborn`
- `SQL` (via Jupyter + SQLite/DB2)

---

## 👤 Autor

**Pedro Bonetti**  
[![GitHub](https://img.shields.io/badge/GitHub-bonett1-black?logo=github)](https://github.com/bonett1)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-pedro--bonetti-blue?logo=linkedin)](https://linkedin.com/in/pedro-bonetti)

---

*Projeto desenvolvido como Capstone do IBM Data Science Professional Certificate.*
