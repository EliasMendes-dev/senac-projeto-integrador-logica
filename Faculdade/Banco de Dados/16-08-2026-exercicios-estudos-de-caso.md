## Estudo de caso 1 
Uma instituição bancária deseja controlar o movimento de suas contas-corrente. A instituição possui 
agências espalhadas por várias cidades, e o seu cadastro contém informações sobre o código, nome, 
e endereço onde a agência fica localizada.  
No cadastro de clientes, deve-se manter informações sobre nome, CPF e endereço de cada cliente. 
As informações sobre contas-corrente são identificadas por um número, e devem fornecer o saldo 
atualizado das mesmas. 

### Entidades

| Entidade | PK | Atributos | FKs |
|:---|:---|:---|:---|
| `Agencias` | `codigo` | `nome`, `endereco` | — |
| `Clientes` | `cpf` | `nome`, `endereco` | — |
| `Conta_correntes` | `numero` | `saldo` | `codigo_agencia_fk`, `cpf_cliente` |

### Relacionamentos

- `Agencias` **1:N** `Conta_correntes`
- `Clientes` **1:N** `Conta_correntes`

---

```sql
CREATE DATABASE IF NOT EXISTS instituicao_bancaria;
USE instituicao_bancaria;

CREATE TABLE IF NOT EXISTS Agencias (
    codigo INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(200) NOT NULL
);

CREATE TABLE IF NOT EXISTS Clientes (
    nome VARCHAR(100) NOT NULL, 
    cpf VARCHAR(11) PRIMARY KEY,
    endereco VARCHAR(200) NOT NULL
);

CREATE TABLE IF NOT EXISTS Conta_correntes (
    numero INT PRIMARY KEY,
    saldo DECIMAL(10,2) NOT NULL,
    codigo_agencia_fk INT,
    cpf_cliente VARCHAR(11),

    FOREIGN KEY (codigo_agencia_fk) REFERENCES Agencias(codigo),
    FOREIGN KEY (cpf_cliente) REFERENCES Clientes(cpf)
);
```

## Estudo de caso 2 
Uma empresa de agenciamento de mão-de-obra pretende informatizar o cadastro de profissionais, 
candidatos a empregos temporários.  
Pretende-se construir um banco de dados onde se possa manter os dados cadastrais dos profissionais, 
e seus contratos temporários com as empresas-clientes.  
O profissional é identificado por um número de controle e, além desta identificação, ficam registrados 
seu nome, endereço, data de nascimento e profissão. 
Os contratos de mão-de-obra temporária são feitos individualmente (um contrato para cada 
profissional), com as empresas-clientes. Cada contrato é identificado por um número único, e nele são 
registrados a empresa contratante, a vigência do contrato (data de início e de término), e o valor pago 
por hora trabalhada. As empresas-clientes são identificadas pelo CGC, e possuem um nome e 
endereço. 

### Entidades

| Entidade | PK | Atributos | FKs |
|:---|:---|:---|:---|
| `Profissionais` | `numero_controle` | `nome`, `endereco`, `data_nascimento`, `profissao` | — |
| `Contratos` | `numero_unico` | `data_de_inicio`, `data_de_termino`, `valor_por_hora` | `numero_profissional`, `cgc_empresa` |
| `Empresas_clientes` | `cgc` | `nome`, `endereco` | — |

### Relacionamentos

- `Profissionais` **1:N** `Contratos`
- `Empresas_clientes` **1:N** `Contratos`
---

```sql
CREATE DATABASE IF NOT EXISTS agencia_mao_de_obra;
USE agencia_mao_de_obra;

CREATE TABLE IF NOT EXISTS Profissionais (
    numero INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(200) NOT NULL,
    data_nascimento DATE NOT NULL,
    profissao VARCHAR(100) NOT NULL
);

CREATE TABLE IF NOT EXISTS Empresas_clientes (
    cgc INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(200) NOT NULL
);

CREATE TABLE IF NOT EXISTS Contratos (
    numero_unico INT PRIMARY KEY,
    data_de_inicio DATE NOT NULL,
    data_de_termino DATE NOT NULL,
    valor_por_hora DECIMAL(10,2) NOT NULL,
    cgc_empresa INT NOT NULL,
    numero_profissional INT NOT NULL,

    FOREIGN KEY (numero_profissional) REFERENCES PROFISSIONAIS(numero),
    FOREIGN KEY (cgc_empresa) REFERENCES EMPRESAS_CLIENTES(CGC)
);
```

## Estudo de caso 3 
Um clube de danças ensina danças de salão, tanto individualmente como em grupo.  
Este clube emprega dois tipos de instrutores: professores assalariados de tempo integral, e 
professores de tempo parcial.  
Os instrutores de tempo integral recebem semanalmente uma quantia fixa, e os de tempo parcial são 
pagos por uma noite ou por aula individual dada.  
O gerente deste clube gostaria de adquirir um sistema de informações, para controlar os estudantes e 
as aulas que eles freqüentam.  
Este gerente também gostaria de saber quantas e quais tipos de aulas cada professor ministrou. 

## Estudo de caso 4 
Um instituto de opinião pública vai realizar uma pesquisa em todos os estados da região sul do Brasil, 
para levantar dados sócio-econômicos sobre os domicílios e as pessoas que neles residem. Para isso,
o instituto contratou cerca de 5.000 entrevistadores, que percorrerão os 150 municípios escolhidos 
para a coleta.  
Os domicílios são classificados, de acordo com sua finalidade, em particulares (aqueles cuja finalidade 
é a moradia de pessoas), e em coletivos (hotéis e quartéis).  
Todos os domicílios entrevistados possuem um código, e devem ter guardadas as informações de sua 
localização (rua, bairro, cidade e estado).  
Nos domicílios particulares, são pesquisados o número de televisões e rádios existentes. Nos 
domicílios coletivos, são levantadas as informações de idade, sexo e grau de instrução. 

## Estudo de caso 5 
Uma clínica veterinária, especializada no tratamento de cães e gatos, pretende informatizar o seu 
sistema de controle de vacinas, de forma a melhorar a notificação aos clientes sobre a data e o tipo 
de vacina a ser aplicada em qualquer um dos animais cadastrados na clínica.  
Os clientes, quando são cadastrados na clínica, são identificados por um código numérico, e devem 
fornecer o nome, sobrenome, telefone e endereço completo (rua, número, complemento, bairro, 
cidade, estado, CEP).  
Para cada animal, que também é identificado por um código numérico, são registrados o nome, data 
de nascimento, espécie, raça, cor e sexo.  
As vacinas, por sua vez, também são identificadas por um código numérico, e possuem nome, nome 
do laboratório fabricante, e lote de fabricação. Quando o animal é vacinado, deve ser feito o registro 
da data de aplicação, o código da próxima vacina a ser tomada, e a respectiva data. 

## Estudo de caso 6 
Uma loja que comercializa artigos de informática resolveu expandir a sua forma de atuação no 
mercado, e passou a aceitar pedidos de compra por telefone.  
Os clientes, ao ligarem para a loja para fazerem seus pedidos, são obrigados a fornecer o nome, 
sobrenome, telefone e endereço completo (rua, número, complemento, bairro, cidade, estado, CEP). 
Os pedidos de compra são identificados por um número de controle, e contém as informações da data 
em que foi feito o pedido, e a forma de pagamento (cheque, dinheiro ou cartão). Os artigos 
comercializados na loja possuem um código, nome e preço unitário. 

## Estudo de caso 7  
Biblioteca 
Uma biblioteca mantém um conjunto de livros, de diversas categorias. Conforme as suas categorias, 
eles estão dispostos em estantes apropriadas.  
Um livro tem vários exemplares na biblioteca. São mantidos dados detalhados sobre autores e editoras 
dos livros para fins de consulta. Na biblioteca trabalham várias bibliotecárias. Cada bibliotecária é 
responsável por organizar periodicamente sempre o mesmo conjunto de estantes e realizar 
empréstimos de exemplares para clientes.   
Empréstimos cadastrados no BD devem conter a data da devolução e o valor diário da multa, 
permanecendo no BD até o cliente entregar o exemplar.  
A bibliotecária que realizou o empréstimo também é relevante de ser mantido no BD. Algumas 
bibliotecárias são estagiárias.  
Uma bibliotecária estagiária está sempre sob a responsabilidade de uma bibliotecária efetiva. Deve
se saber também a instituição de ensino da qual a estagiária vem. Defina os atributos que julgares 
relevantes para os fatos identificados. 