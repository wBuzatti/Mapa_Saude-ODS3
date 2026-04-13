# Requisitos e Modelagem

## 1. Requisitos Funcionais (RFs)

* **RF01:** O sistema deve permitir a visualização de Indicadores Chave de Desempenho (KPIs) gerais sobre a saúde da população na tela inicial.
* **RF02:** O sistema deve fornecer filtros interativos de dados por Região, Ano e Faixa Etária.
* **RF03:** O sistema deve gerar gráficos interativos (linhas e barras) que correlacionem índices de atividade física com os casos de doenças crônicas.
* **RF04:** O sistema deve permitir que o usuário exporte os dados filtrados em formato CSV para análise detalhada.

## 2. Requisitos Não Funcionais (RNF)

* **RNF01 (Tecnologia):** O backend de processamento de dados e a interface devem ser construídos utilizando a linguagem Python (ex: bibliotecas Pandas e Streamlit/Dash).
* **RNF02 (Usabilidade):** A interface do dashboard deve ser responsiva, adaptando-se a diferentes tamanhos de tela.
* **RNF03 (Desempenho):** A renderização dos gráficos não deve ultrapassar 3 segundos após a aplicação de um filtro pelo usuário.

## 3. Diagrama de Casos de Uso
Abaixo, o diagrama ilustrando a interação do ator principal com o sistema de Dashboard.

```mermaid
flowchart LR
    %% Atores
    User([Usuário / Pesquisador])

    %% Casos de Uso
    subgraph Dashboard [Sistema de Dashboard ODS 3]
        UC1(Visualizar KPIs de Saúde)
        UC2(Filtrar Dados por Região/Ano)
        UC3(Analisar Gráficos de Correlação)
        UC4(Exportar Base de Dados em CSV)
    end

    %% Relações
    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
