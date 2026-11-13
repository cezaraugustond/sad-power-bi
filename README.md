# Ferramenta de BI e Análise de Dados: Power BI


## 1. Contexto e O Problema Abordado
As organizações modernas enfrentam um volume crescente e diversificado de ameaças cibernéticas. O grande desafio dos gestores e Diretores de Segurança da Informação (CISOs) não é apenas detectar ataques, mas **saber onde alocar o orçamento de segurança de forma estratégica** para responder a uma pergunta central: *Quais tipos de ataques e setores empresariais causam os maiores prejuízos financeiros, exigindo intervenção imediata e priorização de recursos?*. 

## 2. Sobre os Dados Utilizados
O projeto utiliza a base **"Global Cybersecurity Threats (2015-2024)"**, obtida no Kaggle. 
* **Natureza:** Trata-se de um conjunto de dados sintético gerado para fins educacionais e analíticos, estruturado com base em relatórios reais e frameworks renomados (como *Verizon DBIR*, *ENISA* e *MITRE ATT&CK*).
* **Escopo:** A base rastreia incidentes cibernéticos globais, contemplando variáveis como tipo de ataque, setor alvo, prejuízo financeiro (em milhões de dólares), usuários afetados, tempo de resolução e mecanismos de defesa utilizados.

## 3. Aplicação das Ferramentas (Engenharia e Visualização)

O projeto foi desenvolvido em duas etapas principais, separando a engenharia de dados da visualização interativa:

### A. Preparação e Tratamento de Dados (Python / Jupyter Notebook)
No ambiente Jupyter, utilizando as bibliotecas `Pandas` e `Numpy`, o pipeline de dados envolveu:
* **Limpeza Inicial:** Remoção de espaços em branco e padronização das colunas de texto.
* **Tradução:** Tradução completa dos valores categóricos (tipos de ataque, setores alvo, países e vulnerabilidades) e dos nomes das colunas para o português, facilitando a interpretação.
* **Engenharia de Atributos (*Feature Engineering*):** Criação de colunas estratégicas para apoiar a tomada de decisão:
  * `Nível de Impacto`: Classificação dos incidentes baseada em quartis financeiros (*Crítico*, *Moderado*, *Baixo*).
  * `Custo por Usuário ($)`: Métrica de destruição de valor por pessoa afetada.
  * `Eficiência de Resolução`: Comparativo de tempo de resposta em relação à média geral.

### B. Modelagem e Visualização (Power BI)
O arquivo tratado foi importado para o Power BI Desktop, onde foram desenvolvidos:
* **Medidas DAX Avançadas:** Criação de métricas explícitas como Prejuízo Médio, Total de Incidentes e Contagem Dinâmica de Ataques Críticos (`CALCULATE`).
* **Cartões (KPIs):** Exibição em destaque do Prejuízo Financeiro Total, Total de Usuários Afetados, Incidentes Críticos e Média de Prejuízo.
* **Gráficos Analíticos:** 
  * Gráfico de Colunas/Barras: Identificação do "vilão" principal (ex: *DDos*) cruzando o tipo de ataque com o prejuízo financeiro.
  * Gráfico de Rosca: Mapeamento de quais setores empresariais (como TI e Bancário) sofrem maior impacto financeiro.
* **Filtros Interativos (*Slicers*):** Segmentação dinâmica por ano e país.

---

## 💡 4. Resultados Obtidos e Apoio à Tomada de Decisão

A análise dos dados no dashboard interativo revelou insights cruciais:
