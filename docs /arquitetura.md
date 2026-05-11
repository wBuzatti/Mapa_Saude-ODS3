
# Projeto de Arquitetura de Software

Esta página descreve a arquitetura do Dashboard de Dados (ODS 3) utilizando o padrão C4 Model, detalhando as escolhas tecnológicas e a estrutura do sistema.

## 1. Escolhas de Tecnologias (i)

Para o desenvolvimento desta solução, optamos por uma stack focada em engenharia e análise de dados:

* **Linguagem Principal:** Python 3.10+
* **Processamento de Dados:** Biblioteca `pandas` para a criação de rotinas de ETL (Extração, Transformação e Carga), permitindo a higienização e cruzamento dos dados de saúde pública de forma otimizada.
* **Frontend / Interface:** `Streamlit`. Esta biblioteca permite a construção de interfaces web interativas diretamente em Python, ideal para dashboards analíticos.
* **Armazenamento:** Arquivos estáticos estruturados (`.csv` ou `.parquet`) atuando como base de dados analítica local, garantindo leveza e facilidade de leitura pelas rotinas do pandas.

## 2. Projeto Arquitetural (C4 Model) (ii)

Abaixo estão os diagramas representando os Níveis 1 (Contexto de Sistema) e 2 (Contêiner) da nossa aplicação.

### Nível 1: Diagrama de Contexto
Visão de alto nível de como o usuário interage com o sistema e de onde os dados vêm.

```mermaid
flowchart TD
    User(["Usuário\n(Cidadão / Pesquisador)"])
    System["Sistema de Dashboard ODS 3\n[Sistema de Software]"]
    ExtData["Bases de Dados Abertas\n(Ex: IBGE / DataSUS)\n[Sistema Externo]"]

    User -- "Visualiza KPIs, filtra dados e exporta análises" --> System
    System -- "Extrai dados brutos de saúde e demografia" --> ExtData
