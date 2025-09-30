# CX Radar – Mapeando Experiências Urbanas
### Além do NPS: Inteligência de Reclamações
## Objetivo
Avaliar a experiência do cliente em serviços urbanos usando corridas de táxi como analogia. A proposta é ir além do NPS, criando métricas operacionais que revelam atritos reais na jornada e diferenciam falhas humanas de falhas sistêmicas.

## Metodologia
 - Dados: samples.nyctaxi.trips (Databricks Community Edition)

 - Preparação: limpeza, criação de métricas derivadas, agrupamento por zona

    Indicadores:

      - Tempo médio de viagem (30%)

      - Tarifa média (30%)

      - Índice de frustração (30%)

      - Proporção de corridas caras (10%)

      - Nota final: escala 0–10, zonas < 6 = críticas

## Achados
  - 11430 → frustração média 219.65 (crítico)

  - 11368 → 100% das corridas acima da média global

  - 10305 → nota final 5.66 (alerta vermelho)

  - 11106 → nota final 8.11, mas com frustração elevada

## Dashboard

### 1. Capa
![Capa](https://github.com/user-attachments/assets/d8f5b5a9-e516-4bdb-a59b-7cb8163f0586)

### 2. Radar de Experiência Urbana
![Radar](https://github.com/user-attachments/assets/19b549ba-0ead-414d-b515-24facb8bd065)

### 3. Análises da Experiência Urbana
![Análises](https://github.com/user-attachments/assets/e7634ec7-250d-416d-b263-07927000302e)

## Dashboard no Power BI

O dashboard completo pode ser acessado [neste link](https://app.powerbi.com/view?r=eyJrIjoiZDFjZDVmZmMtYmZkZS00MGZlLTg2Y2ItZjFlYzBkOTYxNjBkIiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9)  
*É necessário ter permissão ou login corporativo para visualizar.*

## Acesso ao Dashboard no Databricks

O dashboard original foi desenvolvido no ambiente Databricks, utilizando o notebook `cx_insights_demo`.  
Ele está disponível [neste link](https://dbc-2f7c928f-6564.cloud.databricks.com/editor/notebooks/2346340275943328?o=1637696810741543) 

> ⚠️ O acesso está liberado para todos os usuários internos do workspace. Usuários externos não conseguirão visualizar o conteúdo diretamente. Para fins de avaliação pública, recomendamos consultar o notebook exportado (`.ipynb`) e os snapshots incluídos neste repositório.

## Recomendações
  - Monitorar zonas < 6

  - Investigar causas sistêmicas (rotas, precificação, tempos)

  - Usar o gap de experiência como meta de melhoria contínua

# CX Radar: Mapeando Experiências Urbanas
## Além do NPS: Inteligência de Reclamações

### Entendimento do Negócio
Este projeto propõe uma abordagem analítica para compreender a experiência do cliente em serviços urbanos, usando dados públicos de corridas de táxi como analogia. A ideia é ir além do NPS e dos dashboards genéricos, explorando métricas operacionais que revelam atritos na jornada do usuário. O objetivo é classificar zonas urbanas como “filiais” e diferenciar falhas humanas de falhas sistêmicas, promovendo uma avaliação mais justa e estratégica da performance local.

### Entendimento dos Dados
Utilizamos o dataset samples.nyctaxi.trips, disponível na Databricks Community Edition. Ele contém registros de corridas de táxi em Nova York, com informações como:

- Horário de embarque e desembarque
- Distância percorrida
- Valor da tarifa
- Localização de origem e destino

###  Preparação dos Dados
- Filtragem de registros inválidos (corridas com distância zero ou tempo negativo)
- Criação de métricas derivadas: tempo médio, tarifa média, índice de frustração
- Agrupamento por zonas de origem (pickup_zip)
- Normalização dos indicadores para escala de 0 a 10

###  Modelagem
Simulação de nota de experiência por zona com base em 4 indicadores:
- Tempo médio de viagem
- Tarifa média
- Índice de frustração (tempo × tarifa ÷ distância)
- Proporção de corridas com tarifa acima da média
- Ponderação dos indicadores: 30% tempo, 30% tarifa, 30% frustração, 10% recorrência

###  Avaliação
- Zonas com nota < 6 foram classificadas como críticas
- Identificação de padrões operacionais que geram insatisfação
- Comparação entre zonas para priorização de melhorias
  #### Achados Relevantes
    - Zona 11430 → frustração média 219.65 (crítico)
    - Zona 11368 → 100% das corridas acima da média global
    - Zona 10305 → nota final 5.66 (alerta vermelho)
    - Zona 11106 → nota final 8.11, mas com frustração elevada

###  Implantação
- Criação da view resultado_final com todos os indicadores consolidados
- Exportação para Power BI via CSV

  #### Simulação de dashboard corporativo com:
  - Indicador principal (gauge ou rosca)
  - Aba “Zonas em Alerta”
  - Tabela com filtros e insights
  - Slide executivo com recomendações

###  Instruções de Uso
- Clone o repositório
- Acesse o notebook cx_insights_demo no Databricks
- Execute as células SQL para gerar os indicadores
- Baixe o CSV final para visualização no Power BI
- Explore o dashboard e identifique zonas críticas

###  Estrutura de Pastas
Código
📦 **cx-radar**  
├── 📁 **data**  
│   └── `nyctaxi_sample.csv`  
├── 📁 **notebooks**  
│   └── `cx_insights_demo.ipynb`  
├── 📁 **dashboards**  
│   └── `cx_taxi_insights.pbix`  
├── 📁 **docs**  
│   └── `metodologia_crispdm.md`  
└── `README.md`

---

## Acesso ao Dashboard no Databricks

O dashboard original foi desenvolvido no ambiente Databricks, utilizando o notebook `cx_insights_demo`.  
Ele está disponível [neste link](https://dbc-2f7c928f-6564.cloud.databricks.com/editor/notebooks/2346340275943328?o=1637696810741543) 

> ⚠️ O acesso está liberado para todos os usuários internos do workspace. Usuários externos não conseguirão visualizar o conteúdo diretamente. Para fins de avaliação pública, recomendamos consultar o notebook exportado (`.ipynb`) e os snapshots incluídos neste repositório.


---

##  Métricas Utilizadas

###  Nota Final
Indicador composto que resume a experiência geral do cliente em cada zona. Calculado a partir de quatro fatores operacionais:
- Tempo médio de viagem  
- Tarifa média  
- Índice de frustração  
- Proporção de corridas caras  
Escala de 0 a 10, sendo 10 a melhor experiência possível.

---

###  Tempo Médio de Espera
Tempo médio que o cliente aguarda até iniciar a corrida. Quanto menor, melhor a percepção de agilidade.

---

###  Tarifa por Minuto
Valor médio pago por minuto de corrida. Indica se o cliente sente que está pagando um preço justo pelo tempo.

---

###  Índice de Frustração
Indicador composto que simula a sensação de ‘não valeu a pena’. Combina tempo, tarifa e distância para medir atrito.

---

###  Proporção de Corridas Caras
Percentual de corridas com tarifa acima da média. Alta recorrência pode gerar insatisfação mesmo em trajetos curtos.

---

###  Score de Atrito Médio
Métrica agregada que resume os principais fatores de atrito na jornada. Quanto maior o valor, maior o impacto negativo na experiência.  
**Usos:** termômetro geral da operação, comparação entre zonas, priorização de ações.

---

###  Áreas em Alerta
Total de áreas com nota final abaixo de 6. Representam áreas com alto risco de insatisfação e devem ser monitoradas com prioridade.

---

###  Área Crítica em Destaque
Identifica o ZIP code com o maior score de atrito. Indica a região mais comprometida em termos operacionais e de percepção negativa.

---

###  Gap de Experiência
Diferença entre a nota máxima (10) e a nota final média. Representa o quanto falta para atingir a excelência.  
**Fórmula:** `Gap = 10 - NotaFinal`

---


##  Visuais no Power BI

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

##  Acesso ao Dashboard no Power BI

O dashboard completo pode ser acessado [neste link](https://app.powerbi.com/view?r=eyJrIjoiZDFjZDVmZmMtYmZkZS00MGZlLTg2Y2ItZjFlYzBkOTYxNjBkIiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9)  
*É necessário ter permissão ou login corporativo para visualizar.*

---

##  Exemplos de Visualizações

### 1. Capa
![Capa](https://github.com/user-attachments/assets/d8f5b5a9-e516-4bdb-a59b-7cb8163f0586)

### 2. Radar de Experiência Urbana
![Radar](https://github.com/user-attachments/assets/19b549ba-0ead-414d-b515-24facb8bd065)

### 3. Análises da Experiência Urbana
![Análises](https://github.com/user-attachments/assets/e7634ec7-250d-416d-b263-07927000302e)




##  Recomendações

- Priorizar zonas com nota < 6 e score de atrito elevado  
- Investigar causas sistêmicas como rotas ineficientes, precificação agressiva ou tempo excessivo de deslocamento  
- Usar o scatter plot para identificar zonas fora da curva  
- Monitorar o gap de experiência como meta de melhoria contínua
### Essas recomendações visam transformar dados operacionais em ações concretas de melhoria contínua, fortalecendo a cultura de CX e a tomada de decisão orientada por evidências.

---

##  Arquivos do Repositório

- `notebooks/cx_insights_demo.ipynb` → notebook Databricks com modelagem e análises  
- `dashboards/cx_insights` → snapshots dos dashboards do Databicks  
- `docs/resumo_executivo.md` → explicações das métricas e insights estratégicos  
- `powerBI/CX_TaxisNYC.pbix` → arquivo do Power BI

---


