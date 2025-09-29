# 📊 Dashboard de Experiência Urbana – Customer Experience (CX)

Este projeto apresenta uma análise estratégica da experiência do cliente em zonas urbanas, utilizando dados operacionais simulados. A solução combina modelagem no Databricks e visualizações no Power BI para identificar pontos de atrito, zonas críticas e oportunidades de melhoria.

---

## 📦 Dataset Utilizado
As análises foram realizadas com base no conjunto de dados público samples.nyctaxi.trips, disponível na plataforma Databricks Community Edition. Este dataset contém registros reais de corridas de táxi na cidade de Nova York, incluindo:

Horário de embarque e desembarque

Distância percorrida

Valor da tarifa

Localização de origem e destino (ZIP code)

Embora o contexto seja urbano e simulado, os dados foram utilizados como analogia para mapear padrões de atrito e oportunidades de melhoria na jornada do cliente — com foco em Customer Experience (CX).

---

## 🎯 Objetivo

Avaliar a jornada do cliente em diferentes regiões urbanas com base em dados reais, indo além do NPS tradicional. A proposta é identificar falhas sistêmicas, antecipar insatisfações e apoiar decisões operacionais com foco em experiência.

---

## 💡 Justificativa da Solução em Power BI

Sabemos que as equipes técnicas já utilizam os dashboards do Databricks no dia a dia para análises operacionais. No entanto, este projeto propõe uma camada adicional de visualização voltada para **gestores e líderes de negócio**, com foco em **Customer Experience (CX)**.

A criação do dashboard em Power BI tem como objetivo tornar os indicadores que impactam o **NPS** e o **relacionamento com clientes** mais acessíveis, intuitivos e acionáveis para quem toma decisões estratégicas.

---

## 🧭 Proposta de Integração com o Dashboard Diário

Sugerimos que o **gauge de NPS** seja incorporado ao dashboard de acompanhamento diário de desempenho e metas, com a opção de abrir o relatório completo de CX, caso o usuário deseje aprofundar a análise.

Essa abordagem permite:

- ✅ Evitar sobrecarga de informações no relatório diário
- ✅ Manter o NPS visível como indicador de alerta
- ✅ Facilitar ações rápidas em caso de variações significativas na nota

---

## 🤝 Engajamento e Cultura de CX

Como forma de incentivar o comprometimento de todas as áreas com a experiência do cliente, sugerimos que o NPS tenha **peso na nota geral de desempenho da filial** (ou unidade equivalente). Isso reforça a importância do tema e estimula uma cultura orientada ao cliente em todos os níveis da operação.


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

### 🕒 Tempo Médio de Espera
Tempo médio que o cliente aguarda até iniciar a corrida. Quanto menor, melhor a percepção de agilidade.

---

### 💰 Tarifa por Minuto
Valor médio pago por minuto de corrida. Indica se o cliente sente que está pagando um preço justo pelo tempo.

---

### 😠 Índice de Frustração
Indicador composto que simula a sensação de ‘não valeu a pena’. Combina tempo, tarifa e distância para medir atrito.

---

### 📈 Proporção de Corridas Caras
Percentual de corridas com tarifa acima da média. Alta recorrência pode gerar insatisfação mesmo em trajetos curtos.

---

### 🧮 Score de Atrito Médio
Métrica agregada que resume os principais fatores de atrito na jornada. Quanto maior o valor, maior o impacto negativo na experiência.  
**Usos:** termômetro geral da operação, comparação entre zonas, priorização de ações.

---

### 🔴 Áreas em Alerta
Total de áreas com nota final abaixo de 6. Representam áreas com alto risco de insatisfação e devem ser monitoradas com prioridade.

---

### 📍 Área Crítica em Destaque
Identifica o ZIP code com o maior score de atrito. Indica a região mais comprometida em termos operacionais e de percepção negativa.

---

### ⚪ Gap de Experiência
Diferença entre a nota máxima (10) e a nota final média. Representa o quanto falta para atingir a excelência.  
**Fórmula:** `Gap = 10 - NotaFinal`

---

### 🔴 Zonas Críticas
Total de zonas com nota final abaixo de 6. Representam áreas com alto risco de insatisfação e devem ser monitoradas com prioridade.

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

## 🔗 Acesso ao Dashboard

O dashboard completo pode ser acessado [neste link](https://app.powerbi.com/view?r=eyJrIjoiZDFjZDVmZmMtYmZkZS00MGZlLTg2Y2ItZjFlYzBkOTYxNjBkIiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9))  
*É necessário ter permissão ou login corporativo para visualizar.*

---


## 🧠 Recomendações

- Priorizar zonas com nota < 6 e score de atrito elevado  
- Investigar causas sistêmicas como rotas ineficientes, precificação agressiva ou tempo excessivo de deslocamento  
- Usar o scatter plot para identificar zonas fora da curva  
- Monitorar o gap de experiência como meta de melhoria contínua

---

## 🗂️ Arquivos do Repositório

- `notebooks/cx_insights_demo.ipynb` → notebook Databricks com modelagem e análises  
- `dashboards/cx_insights` → snapshots dos dashboards do Databicks  
- `docs/resumo_executivo.md` → explicações das métricas e insights estratégicos  
- `powerBI/CX_TaxisNYC.pbix` → arquivo do Power BI

---


