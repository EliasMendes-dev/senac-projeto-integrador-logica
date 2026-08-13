## 1) Faça um programa que calcule e mostre a área de um círculo. Sabe-se que: Área = π * R²

```
ALGORITMO
DECLARE PI, RAIO, AREA NUMERICO

ESCREVA "INFORME O VALOR DO RAIO"
LEIA RAIO

PI <- 3.14
AREA <- PI * RAIO * RAIO

ESCREVA "A ÁREA É ", AREA

FIM-ALGORITMO
```

## 2) Faça um programa que receba um número positivo e maior que zero, calcule e mostre:

- a) o número digitado ao quadrado;
- b) o número digitado ao cubo;
- c) a raiz quadrada do número digitado;
- d) a raiz cúbica do número digitado;

```
ALGORITMO
DECLARE NUMERO, QUADRADO, CUBO, RAIZ_QUADRADA, RAIZ_CUBICA NUMERICO

ESCREVA "INFORME UM NÚMERO POSITIVO E MAIOR QUE ZERO"
LEIA NUMERO

QUADRADO <- NUMERO * NUMERO
CUBO <- NUMERO * NUMERO * NUMERO
RAIZ_QUADRADA <- NUMERO ^ (1 / 2)
RAIZ_CUBICA <- NUMERO ^ (1 / 3)

ESCREVA "O NÚMERO AO QUADRADO É ", QUADRADO
ESCREVA "O NÚMERO AO CUBO É ", CUBO
ESCREVA "A RAIZ QUADRADA É ", RAIZ_QUADRADA
ESCREVA "A RAIZ CÚBICA É ", RAIZ_CUBICA

FIM-ALGORITMO
```

## 3) Faça um programa que receba dois números maiores que zero, calcule e mostre um elevado ao outro.

```
ALGORITMO
DECLARE NUMERO1, NUMERO2, RESULTADO1, RESULTADO2 NUMERICO

ESCREVA "INFORME DOIS NÚMEROS MAIORES QUE ZERO"
LEIA NUMERO1, NUMERO2

RESULTADO1 <- NUMERO1 ^ NUMERO2
RESULTADO2 <- NUMERO2 ^ NUMERO1

ESCREVA "O PRIMEIRO NÚMERO ELEVADO AO SEGUNDO É ", RESULTADO1
ESCREVA "O SEGUNDO NÚMERO ELEVADO AO PRIMEIRO É ", RESULTADO2

FIM-ALGORITMO
```

## 4) Faça um programa que receba uma medida em pés, faça as conversões a seguir e mostre os resultados. Sabendo que 1 pé = 12 polegadas, 1 jarda = 3 pés, 1 milha = 1.760 jardas.

- a) polegadas;
- b) jardas;
- c) milhas;

```
ALGORITMO
DECLARE PES, POLEGADAS, JARDAS, MILHAS NUMERICO

ESCREVA "INFORME UMA MEDIDA EM PÉS"
LEIA PES

POLEGADAS <- PES * 12
JARDAS <- PES / 3
MILHAS <- JARDAS / 1760

ESCREVA "ESSA MEDIDA EM POLEGADAS É ", POLEGADAS
ESCREVA "ESSA MEDIDA EM JARDAS É ", JARDAS
ESCREVA "ESSA MEDIDA EM MILHAS É ", MILHAS

FIM-ALGORITMO
```

## 5) Faça um programa que receba o ano de nascimento de uma pessoa e o ano atual, calcule e mostre:

- a) a idade dessa pessoa;
- b) quantos anos ela terá em 2050.

```
ALGORITMO
DECLARE ANO_NASCIMENTO, ANO_ATUAL, IDADE_ATUAL, IDADE_2050 NUMERICO

ESCREVA "INFORME SEU ANO DE NASCIMENTO E O ANO ATUAL"
LEIA ANO_NASCIMENTO, ANO_ATUAL

IDADE_ATUAL <- ANO_ATUAL - ANO_NASCIMENTO
IDADE_2050 <- 2050 - ANO_NASCIMENTO

ESCREVA "SUA IDADE SERÁ ", IDADE_ATUAL
ESCREVA "SUA IDADE EM 2050 SERÁ ", IDADE_2050

FIM-ALGORITMO
```

## 6) O custo ao consumidor de um carro novo é a soma do preço de fábrica com o percentual de lucro do distribuidor e dos impostos aplicados ao preço de fábrica. Faça um programa que receba o preço de fábrica de um veículo, o percentual de lucro do distribuidor e o percentual de impostos, calcule e mostre:

- a) o valor correspondente ao lucro do distribuidor;
- b) o valor correspondente aos impostos;
- c) o preço final do veículo.

```
ALGORITMO
DECLARE PRECO_FABRICA, PERCENTUAL_LUCRO, PERCENTUAL_IMPOSTO NUMERICO
DECLARE VALOR_LUCRO, VALOR_IMPOSTO, PRECO_FINAL NUMERICO

ESCREVA "INFORME O PREÇO DE FÁBRICA DO VEÍCULO, O PERCENTUAL DE LUCRO DO DISTRIBUIDOR E O PERCENTUAL DE IMPOSTOS"
LEIA PRECO_FABRICA, PERCENTUAL_LUCRO, PERCENTUAL_IMPOSTO

VALOR_LUCRO <- PRECO_FABRICA * PERCENTUAL_LUCRO / 100
VALOR_IMPOSTO <- PRECO_FABRICA * PERCENTUAL_IMPOSTO / 100
PRECO_FINAL <- PRECO_FABRICA + VALOR_LUCRO + VALOR_IMPOSTO

ESCREVA "O VALOR DO LUCRO DO DISTRIBUIDOR É ", VALOR_LUCRO
ESCREVA "O VALOR DOS IMPOSTOS É ", VALOR_IMPOSTO
ESCREVA "O PREÇO FINAL DO VEÍCULO É ", PRECO_FINAL

FIM-ALGORITMO
```

## 7) Faça um programa que receba o número de horas trabalhadas e o valor do salário mínimo, calcule e mostre o salário a receber, seguindo estas regras:

- a) a hora trabalhada vale a metade do salário mínimo.
- b) o salário bruto equivale ao número de horas trabalhadas multiplicado pelo valor da hora trabalhada.
- c) o imposto equivale a 3 porcento do salário bruto.
- d) o salário a receber equivale ao salário bruto menos o imposto.

```
ALGORITMO
DECLARE HORAS_TRABALHADAS, SALARIO_MINIMO, VALOR_HORA NUMERICO
DECLARE SALARIO_BRUTO, IMPOSTO, SALARIO_RECEBER NUMERICO

ESCREVA "INFORME O NÚMERO DE HORAS TRABALHADAS E O VALOR DO SALÁRIO MÍNIMO"
LEIA HORAS_TRABALHADAS, SALARIO_MINIMO

VALOR_HORA <- SALARIO_MINIMO / 2
SALARIO_BRUTO <- HORAS_TRABALHADAS * VALOR_HORA
IMPOSTO <- SALARIO_BRUTO * 0.03
SALARIO_RECEBER <- SALARIO_BRUTO - IMPOSTO

ESCREVA "O SALÁRIO A RECEBER É ", SALARIO_RECEBER

FIM-ALGORITMO
```

## 8) Um trabalhador recebeu seu salário e o depositou em sua conta bancária. Esse trabalhador emitiu dois cheques e agora deseja saber seu saldo atual. Sabe-se que cada operação bancária de retirada paga CPMF de 0,38 porcento e o saldo inicial da conta está zerado.

```
ALGORITMO
DECLARE SALARIO, CHEQUE1, CHEQUE2, CPMF1, CPMF2, SALDO_ATUAL NUMERICO

ESCREVA "INFORME O SALÁRIO DEPOSITADO, O VALOR DO PRIMEIRO E DO SEGUNDO CHEQUE"
LEIA SALARIO, CHEQUE1, CHEQUE2

CPMF1 <- CHEQUE1 * 0.0038
CPMF2 <- CHEQUE2 * 0.0038

SALDO_ATUAL <- SALARIO - CHEQUE1 - CPMF1 - CHEQUE2 - CPMF2

ESCREVA "O SALDO ATUAL É ", SALDO_ATUAL

FIM-ALGORITMO
```

## 9) Pedro comprou um saco de ração com peso em quilos. Ele possui dois gatos, para os quais fornece a quantidade de ração em gramas. A quantidade diária de ração fornecida para cada gato é sempre a mesma. Faça um programa que receba o peso do saco de ração e a quantidade de ração fornecida para cada gato, calcule e mostre quanto restará de ração no saco após cinco dias.

```
ALGORITMO
DECLARE PESO_SACO, RACAO_POR_GATO, RACAO_RESTANTE NUMERICO

ESCREVA "INFORME O PESO DO SACO DE RAÇÃO E A QUANTIDADE DE RAÇÃO FORNECIDA PARA CADA GATO"
LEIA PESO_SACO, RACAO_POR_GATO

RACAO_RESTANTE <- (PESO_SACO * 1000) - (RACAO_POR_GATO * 2 * 5)

ESCREVA "A QUANTIDADE DE RAÇÃO QUE RESTARÁ APÓS CINCO DIAS É ", RACAO_RESTANTE, " GRAMAS"

FIM-ALGORITMO
```