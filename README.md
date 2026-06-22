# Data (re)conciliation: Auditoria e Harmonização de Dados Municipais 🏙️

**Estágio Curricular | Câmara Municipal da Maia (D4Maia)** **Autor:** Rodrigo Mendes  
**Ano:** 2025/2026

## 📋 Sobre o Projeto
Este repositório contém as ferramentas desenvolvidas no âmbito do projeto **Data (re)conciliation**. O objetivo foi criar *pipelines* automáticas para auditar a qualidade dos dados geográficos municipais, cruzando a informação oficial da autarquia (WFS) com fontes externas como o **OpenStreetMap**, **Overture Maps** e **GTFS**.

O sistema deteta automaticamente inconsistências de localização e nomenclatura em infraestruturas críticas (Escolas, Transportes, Saúde, etc.), gerando relatórios de apoio à decisão.

## 🛠️ Tecnologias Utilizadas
* **Python** (Google Colab Environment)
* **GeoPandas & Shapely:** Análise e manipulação espacial.
* **DuckDB:** Processamento de *Big Data* (consulta direta a ficheiros Parquet no AWS S3).
* **Folium:** Geração de mapas interativos.
* **FuzzyWuzzy:** Algoritmos de *string matching* (Levenshtein) para reconciliação de nomes.
* **PDFPlumber:** Extração de dados de fontes não estruturadas.

## 📂 Estrutura das Pipelines
Foram desenvolvidos 6 notebooks principais para diferentes domínios:

| Pipeline | Fontes Cruzadas | Descrição |
| :--- | :--- | :--- |
| **01. Metro** | WFS, GTFS, OSM, Overture | Validação das estações de Metro do Porto na Maia. |
| **02. Autocarros** | WFS, GTFS (STCP), OSM | Auditoria de paragens de autocarro. |
| **03. Escolas** | WFS, GesEdu, OSM, Overture | Reconciliação semântica de nomes de escolas. |
| **04. Saúde** | WFS, OSM, Overture | Validação de Farmácias, USF e Hospitais. |
| **05. Social** | WFS, PDF (Guia), OSM | Digitalização e validação de IPSS e Lares. |
| **06. Hidrografia** | WFS, OSM | Verificação de linhas de água e ribeiras. |

*Nota: O PDF do "Guia de Recursos Sociais" utilizado na pipeline 05 pode ser consultado [neste link](https://bit.ly/grsmm25).*

## 🚀 Como Executar
Os notebooks foram desenhados para correr em **Google Colab**.
1. Abra um dos ficheiros `.ipynb` da pasta `notebooks/`.
2. Clique no botão "Open in Colab".
3. Configure os *Secrets* do Colab com as credenciais necessárias (se aplicável para envio de email).
4. Execute as células sequencialmente.

## 📊 Resultados
O sistema gera mapas interativos onde os conflitos são desenhados a vermelho/laranja e os *matches* a verde.

## 📄 Documentação
O Relatório Final de Estágio completo encontra-se na pasta `docs/`.

---
**Orientador:** Eng. Pedro Pimenta (CM Maia)  
**Regente:** Prof. Eduardo Marques (FCUP)
