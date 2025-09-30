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

