# 📊 Dashboard de Experiência Urbana – Customer Experience (CX)

Este projeto apresenta uma análise estratégica da experiência do cliente em zonas urbanas, utilizando dados operacionais simulados. A solução combina modelagem no Databricks e visualizações no Power BI para identificar pontos de atrito, zonas críticas e oportunidades de melhoria.

---

## 🎯 Objetivo

Avaliar a jornada do cliente em diferentes regiões urbanas com base em dados reais, indo além do NPS tradicional. A proposta é identificar falhas sistêmicas, antecipar insatisfações e apoiar decisões operacionais com foco em experiência.

---

## 🧩 Métricas Utilizadas

### 🟢 Nota Final
Indicador composto que resume a experiência geral do cliente em cada zona. Calculado a partir de quatro fatores operacionais:
- Tempo médio de viagem  
- Tarifa média  
- Índice de frustração  
- Proporção de corridas caras  
Escala de 0 a 10, sendo 10 a melhor experiência possível.

---

### ⚪ Gap de Experiência
Diferença entre a nota máxima (10) e a nota final média. Representa o quanto falta para atingir a excelência.  
**Fórmula:** `Gap = 10 - NotaFinal`

---

### 🧮 Score de Atrito Médio
Métrica agregada que resume os principais fatores de atrito na jornada. Quanto maior o valor, maior o impacto negativo na experiência.  
**Usos:** termômetro geral da operação, comparação entre zonas, priorização de ações.

---

### 🔴 Zonas Críticas
Total de zonas com nota final abaixo de 6. Representam áreas com alto risco de insatisfação e devem ser monitoradas com prioridade.

---

### 📍 Área Crítica em Destaque
Identifica o ZIP code com o maior score de atrito. Indica a região mais comprometida em termos operacionais e de percepção negativa.

---

## 📈 Visuais no Power BI

O dashboard foi dividido em duas páginas:

### Página 1 – Visão Geral
- Gauge de Experiência  
- Gráfico de Rosca com Gap  
- Mapa por ZIP code  
- Cartões com indicadores principais  
- Tooltip explicativo para cada métrica

### Página 2 – Zonas Críticas
- Score de Atrito Médio  
- Quantidade de Zonas Críticas  
- Área Crítica em Destaque  
- Gráfico de Dispersão (Atrito vs Frustração)  
- Mapa com todas as zonas marcadas

---

## 🧠 Recomendações

- Priorizar zonas com nota < 6 e score de atrito elevado  
- Investigar causas sistêmicas como rotas ineficientes, precificação agressiva ou tempo excessivo de deslocamento  
- Usar o scatter plot para identificar zonas fora da curva  
- Monitorar o gap de experiência como meta de melhoria contínua

---

## 🗂️ Arquivos do Repositório

- `notebooks/cx_insights_demo.ipynb` → notebook Databricks com modelagem e análises  
- `dashboards/cx_experience_dashboard.pbix` → arquivo do Power BI com visualizações  
- `docs/resumo_executivo.md` → explicações das métricas e insights estratégicos  
- `dashboards/*.png` → capturas de tela dos gráficos e visuais (opcional)

---

## 👩‍💻 Autora

Débora – projeto desenvolvido como parte de avaliação para vaga em Customer Experience (CX)

