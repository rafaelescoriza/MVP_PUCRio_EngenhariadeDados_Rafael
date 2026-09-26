# MVP - Engenharia de Dados | PUC-Rio

Este repositório contém o MVP desenvolvido para a disciplina de Engenharia de Dados da Pós-Graduação em Ciência de Dados e Analytics da PUC-Rio. O projeto consiste na construção de um pipeline de dados completo na plataforma **Databricks**, seguindo a arquitetura em camadas (medallion architecture): **Bronze → Silver → Gold**, com governança via **Unity Catalog**.

> **O relatório completo do projeto**, com todo o contexto de negócio, as decisões de modelagem, as evidências em screenshots e a autoavaliação, está no arquivo **`00_MVP_Engenhariadedados_RafaelEscoriza.pdf`**, disponível nesta mesma pasta do repositório. Este README serve como um guia rápido de navegação pelo projeto e pelos notebooks.

---

Os **notebooks** estão disponíveis neste repositório para consulta e reprodução do pipeline, contendo o código SQL utilizado em cada etapa da construção das camadas Bronze, Silver e Gold.

---

## Sobre o projeto

O objetivo do MVP é construir um pipeline de dados de ponta a ponta a partir de um dataset sobre sucesso de carreira de estudantes (CSV), demonstrando na prática:

- Ingestão e carga de dados brutos;
- Modelagem de dados em camadas;
- Processo de ETL (Extração, Transformação e Carga);
- Tratamento e garantia de qualidade de dados;
- Análise de dados para responder a perguntas de negócio.

Todo o desenvolvimento foi realizado no Databricks, com o código versionado e disponibilizado publicamente neste repositório GitHub.

---

## Engenharia do pipeline

O pipeline segue o modelo **medalhão**, organizado em três camadas dentro do Unity Catalog:

### Bronze
Camada de dados brutos, com a ingestão do dataset original sem transformações, preservando a fonte tal como recebida.

###  Silver
Camada responsável por toda a qualidade dos dados, dividida em duas etapas:

- **`silver_v00`** — renomeação e tradução das colunas para o português;
A `silver_v01` é a fonte única e limpa utilizada para alimentar a camada Gold.

### Gold
Camada de consumo analítico, mantendo a granularidade original das linhas, enriquecida com colunas derivadas (como faixas salariais). As perguntas de negócio do projeto são respondidas por meio de consultas (`SELECT`) individuais sobre a Gold, com os resultados evidenciados via screenshots no relatório em PDF.
- **`gold_v00`** — filtragem, remoção de duplicidades, tratamento de nulos e valores em branco, remoção de registros inválidos e seleção das colunas relevantes.
---



##  Onde encontrar cada parte do projeto

| O que você procura | Onde encontrar |
|---|---|
| Contexto de negócio, modelagem, qualidade de dados, análises e autoavaliação | `00_MVP_Engenhariadedados_RafaelEscoriza.pdf` |
| Código-fonte do pipeline (Bronze, Silver, Gold) | Pasta `notebooks/` |
| Visão geral e estrutura do projeto | Este `README.md` |

---

## ✍️ Autor

**Rafael Escoriza**
Projeto desenvolvido como MVP da disciplina de Engenharia de Dados — PUC-Rio.
