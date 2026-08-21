# Banco de Dados — Aula 1: Introdução a Banco de Dados

## Histórico: Da Era dos Arquivos aos Modelos Iniciais

**Anos 1950–1960: Sistemas de Arquivos**
- Processamento baseado em **cartões perfurados** e **fitas magnéticas**
- Programas acessavam arquivos diretamente
- Alta **redundância**, **inconsistência** e ausência de padronização

**Anos 1960: Modelo Hierárquico**
- Surgimento do **IMS** (Information Management System) da IBM
- Dados em estrutura de **árvore** (pai-filho)
- Rigidez no acesso à informação

**Anos 1960: Modelo em Rede**
- Padronização pelo padrão **CODASYL** (Conference on Data Systems Languages)
- Registros conectados em **grafos** por ponteiros físicos complexos

## 1970: A Revolução do Modelo Relacional

**Edgar Frank Codd (IBM)**
- Em 1970, publicou o artigo divisor de águas: *"A Relational Model of Data for Large Shared Data Banks"* na revista da ACM (Association for Computing Machinery)

**Principais inovações de Codd:**
- Separação completa entre a **representação lógica** (tabelas/relações) e o **armazenamento físico**
- Base teórica em **Matemática** (Teoria dos Conjuntos e Lógica de Predicados)
- Eliminação da necessidade de navegar por ponteiros físicos

> "Os usuários devem ser protegidos de ter que conhecer a representação interna de dados em computadores." — Edgar Frank Codd (Prêmio Turing de 1981)

## 1980–2000: SQL, ACID e a Dominância do RDBMS

- **Linguagem SQL**: criada na IBM como System R (Structured English Query Language – SEQUEL) e padronizada pelo ANSI e ISO como **SQL** (Structured Query Language)
- **Garantia ACID**: formalização das propriedades **Atomicidade, Consistência, Isolamento, Durabilidade**, garantindo integridade absoluta em transações financeiras e de saúde
- **SGBDs Comerciais**: consolidação do mercado com **Oracle**, **IBM DB2**, **Microsoft SQL Server** e crescimento de alternativas open-source como **PostgreSQL** e **MySQL**

## Século XXI: NoSQL, Big Data e BDs Vetoriais para IA

**Anos 2000: A Era NoSQL e Big Data**
- Surgimento do movimento **NoSQL** (Not Only SQL) para tratar volume, velocidade e variedade da web
- Bancos Orientados a Documentos (**MongoDB**), Chave-Valor (**Redis**) e Grafos (**Neo4j**)

**Anos 2010: NewSQL & Data Lakes**
- Sistemas que combinam **escalabilidade horizontal** com garantias ACID relacionais (**CockroachDB**, **Google Spanner**)
- Repositórios para dados brutos (**Data Lakes**)

**Anos 2020+: Bancos de Dados Vetoriais para IA**
- Nascimento dos **BDs Vetoriais** (Pinecone, Milvus, Qdrant, PGVector) para **busca semântica** em LLMs e inteligência artificial generativa

---

## Introdução ao Banco de Dados

- Uma peça chave para o funcionamento de um sistema de informação são os **dados** ou **informações** manipuladas
- Apesar de poderem ser usados indistintamente, existe diferença entre **dado**, **informação** e **conhecimento** — uma escala de valor entre eles

## O que é Dado (Data)?

**Dado** é um conjunto de símbolos, valores brutos ou observações isoladas, desprovidos de contexto ou significado intrínseco.

**Exemplos didáticos na saúde:**
- O número bruto: **138**
- O valor numérico: **6.8**
- O texto isolado: **"Positivo"**
- A sequência de pixels de uma imagem sem laudo

> **No Banco de Dados:** o dado é o registro puro gravado em uma célula de uma tabela ou arquivo JSON, sem interpretação prévia.

## O que é Informação (Information)?

**Informação** é o dado dotado de **contexto**, unidade de medida, significado, origem e propósito inteligível.

**Transformando dados em informações clínicas:**
- 138 → **Pressão Arterial Sistólica de 138 mmHg** medida às 08h30
- 6.8 → **Glicemia em Jejum de 6,8 mmol/L**
- "Positivo" → **Resultado de RT-PCR para COVID-19** do paciente X

> **No Banco de Dados:** é o resultado de uma consulta SQL (**SELECT**) que correlaciona tabelas de Pacientes, Exames e Prescrições.

## O que é Banco de Dados (BD)?

Um **Banco de Dados** é uma coleção organizada, estruturada e integrada de dados correlacionados, mantida eletronicamente para busca ágil, atualização e segurança.

**Exemplo didático na saúde:**
- Um **PEP (Prontuário Eletrônico do Paciente)** que armazena históricos de consultas, exames laboratoriais, diagnósticos **ICD-10** e prescrições médicas interligados por chaves lógicas

> Serve de alicerce para alimentar pipelines de **BI** (Business Intelligence) e algoritmos de **IA** (Inteligência Artificial).

## O que é Conhecimento (Knowledge)?

**Conhecimento** é a síntese e a compreensão profunda de múltiplas informações validadas através de padrões, raciocínio clínico ou modelos de Inteligência Artificial.

**Exemplo didático na saúde:**
- Ao cruzar a **Pressão Sistólica de 138 mmHg** com a **Glicemia de 6,8 mmol/L** e o histórico familiar, conclui-se que o paciente possui **Alto Risco para Síndrome Metabólica**

> **Na IA:** padrões probabilísticos extraídos via **Machine Learning** a partir de milhões de registros históricos de saúde.

---

## Sistema de Informação

- Em geral, para empresas, o conjunto de softwares e equipamentos é caracterizado como **sistema de informação**

> "Um Sistema de Informação (SI) pode ser definido tecnicamente como um conjunto de componentes inter-relacionados que coletam (ou recuperam), processam, armazenam e distribuem informações destinadas a apoiar a tomada de decisões, a coordenação e o controle de uma organização." (LANDON; LANDON, 2010, p. 12)

**Fluxo típico:**
- **Usuário** → **Sistema (cliente)** → consultas escritas em **SQL** → **Servidor de Banco de Dados**
- Servidor processa e retorna **resultados**
- O **Programa do SGBD** acessa as bases (Vendas, Financeiro, RH) armazenadas em **disco rígido**, estruturadas segundo o **Modelo Relacional** (Clientes, Vendas, Itens, Produtos)

## Dados, Informação e Conhecimento (síntese)

- **Dados** são os componentes básicos a partir dos quais a **informação** é criada
- **Informação** são dados inseridos em um **contexto**
- **Contexto** é a situação que está sendo analisada
- A partir da informação vem o **conhecimento**, que permite tomar decisões adequadas, trazendo **vantagem competitiva**

**Exemplo — o dado `101221` conforme o contexto:**
- Contexto **Hora** (hh:mm:ss) → Informação: 10:12:21
- Contexto **Data** (dd/mm/aa) → Informação: 10/Dez/2021
- Contexto **Data** (mm/dd/aa) → Informação: 12/Out/2021
- Contexto **RA ou Identificação** → Informação: 101221

**Exemplos de dados empresariais:**
- **Cadastro de Clientes**: CNPJ, razão social, endereço
- **Notas fiscais**: valor total, ICMS, data de emissão
- **Boleto de cobrança**: valor, data de pagamento, juros
- Dados sobre participação no mercado, concorrência, tendências de consumo, nível de emprego, etc.

> Esses dados, apresentados de maneira adequada a um contexto em que serão utilizados, são chamados **informação**.

---

## SGBD – Sistema de Gerenciador de Banco de Dados

- **SGBD** é um conjunto de software utilizado para o gerenciamento de uma base de dados, responsável por **controlar**, **acessar**, **organizar** e **proteger** as informações de uma aplicação
- Objetivo principal: gerenciar as bases de dados utilizadas por aplicações clientes, removendo essa responsabilidade das mesmas

**Arquitetura:**
- **Usuários** → **Programas de Aplicação/Consultas** → **SGBD Software** (software para processar consultas → software para acessar dados armazenados) → **Meta-Dados Armazenado** e **Base de Dados Armazenada**

### Vantagens e Desvantagens do SGBD

**Vantagens:**
- **Segurança** (restrição de acesso)
- Mecanismo de **backup**
- Garante a **consistência dos dados**
- Evita **redundância**
- Maior **flexibilidade** para mudanças
- Compartilhamento entre múltiplos usuários

**Desvantagens:**
- Elevado **custo** com os softwares
- Necessidade de **equipe altamente capacitada**
- Elevado **overhead**

### Principais SGBDs

- **Oracle**
- **Microsoft SQL Server**
- **IBM DB2**
- **Informix**
- **MySQL**
- **PostgreSQL**

---

## Classificação dos BD

Existem vários tipos de Banco de Dados:
- **Relacional**
- **Orientado a Objetos**
- **Hierárquico**
- **Network** (Rede)
- **Multimídia**
- **Geográfico**

### 1 – Modelo Relacional

- Dados organizados em **tabelas** (ex.: tabela `CLIENTE` com Cliente_id, Nome, Endereço, Cidade; tabela `PEDIDO` com Pedido_id, Cliente_id, Preço, Data), relacionadas por **chaves**

### 1 – Modelo Orientado a Objetos

- Estrutura hierárquica de classes (ex.: **Pessoa** → Empregado/Cliente → Secretária/Engenheiro → Civil/Eletrônico)
- Dados organizados em **tuplas** com **PK** (chave primária) para cada classe/objeto

### II – Modelo Hierárquico

- Estrutura em **árvore**, com relações do tipo pai-filho (ex.: Serviço → Atendimento e Departamento; Atendimento → Cliente)

### III – Modelo em Rede – Network

- Estrutura em **grafo**, permitindo múltiplas conexões entre registros (ex.: Cliente → Atendimento → Serviço → Departamento)

---

## BD Relacional

- O **modelo relacional** é um sistema para organizar e armazenar dados em **tabelas** formadas por linhas e colunas
- Criado em **1970** por **Edgar F. Codd**, usa a matemática para manter os dados organizados, seguros e fáceis de buscar
- Sistemas como **Oracle DB**, **MySQL**, **PostgreSQL** e **SQL Server** usam esse modelo

**Características:**
- Dados armazenados em **tabelas** (relações ou entidades) devidamente relacionadas e identificadas
- Cada tabela possui **linhas (tuplas)** e **colunas (atributos)**
- Toma como base o **Modelo Relacional** (ex.: entidades `CONTA`, `LOG`, `TRANSACAO`)

---

## Projeto de BD

Para a criação de um projeto de BD são necessários os seguintes passos:
- **Levantamento de Requisitos**
- **Projeto Conceitual**
- **Projeto Lógico**
- **Projeto Físico**

**Detalhamento das etapas:**
- **Requisitos**: baseado em entrevistas com o cliente, cria-se a documentação do projeto
- **Conceitual**: criação do modelo conceitual (voltado para o cliente)
- **Lógico**: criação do modelo lógico (mais técnico)
- **Físico**: criação dos scripts, modelo físico, estratégias de segurança e armazenamento

### Projeto Conceitual

- Representa entidades e relacionamentos com **cardinalidade** (ex.: Cliente **1:N** Compra via "Realiza"; Aluno **1:N** Matrícula via "Possui"; Professor **1:N** Aula via "Leciona")

### Projeto Lógico

- Detalha os **atributos** de cada entidade, com identificação de **chave primária** (ex.: `PROFESSOR` com `id_professor` (PK), `nome`, `cpf`; `AULA` com `id_aula` (PK), `data_aula`, `hora_aula`)

### Projeto Físico (MySQL)

- Define **tipos de dados**, tamanhos e chaves (ex.: `PROFESSOR` — `id_professor NUMBER(3)` **PK**, `nome VARCHAR2(30)`, `cpf NUMBER(11)`; `AULA` — `id_aula NUMBER(3)` **PK**, `id_turma`, `id_materia`, `id_professor` **FK**, `data_aula DATE`, `hora_aula DATE`)

**Exemplo em SQL-DDL:**
```sql
CREATE TABLE professor (
    idProfessor INT NOT NULL AUTO_INCREMENT,
    telefone VARCHAR(15) NOT NULL,
    nome VARCHAR(80) NOT NULL,
    PRIMARY KEY (idProfessor)
);

CREATE TABLE turma (
    idturma INT NOT NULL AUTO_INCREMENT,
    capacidade INT NOT NULL,
    idProfessor INT NOT NULL,
    PRIMARY KEY (idturma),
    FOREIGN KEY (idProfessor) REFERENCES professor(idProfessor)
);
```

### Tabela comparativa entre os modelos

| Característica | Conceitual | Lógico | Físico |
|---|---|---|---|
| Nome de Entidade | ✔ | ✔ | |
| Relacionamentos de Entidade | ✔ | ✔ | |
| Atributos | ✔ | ✔ | |
| Chave Primária | | ✔ | ✔ |
| Chave Estrangeira | | ✔ | ✔ |
| Nome das Tabelas | | | ✔ |
| Nome das Colunas | | | ✔ |
| Tipo das Colunas | | | ✔ |

---
