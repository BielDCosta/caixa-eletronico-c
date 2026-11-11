# Caixa Eletrônico (ATM) em C

Programa em C que simula um caixa eletrônico: pede o valor do saque, valida a entrada e mostra quantas cédulas e moedas serão entregues.

Atividade 2 (A2.2) da disciplina Algoritmos e Pensamento Computacional (APC) – UNICID.

## Como rodar

Precisa de um compilador C, como o `gcc`.

```bash
gcc atm.c -o atm
./atm
```

Exemplo:

```
=== CAIXA ELETRONICO (ATM) ===
Saldo disponivel: R$ 1000
Digite o valor do saque: 285
Saque de R$ 285 autorizado.
Notas entregues:
2 nota(s) de 100
1 nota(s) de 50
1 nota(s) de 20
1 nota(s) de 10
1 nota(s) de 5
```

## Como funciona

1. Lê o valor do saque (o saldo inicial é R$ 1000).
2. Valida a entrada: precisa ser um número inteiro, maior que zero e menor ou igual ao saldo.
3. Calcula a distribuição com divisão inteira (`/`) para a quantidade e módulo (`%`) para o que sobra, das cédulas maiores para as menores: 100, 50, 20, 10, 5, 2 e moeda de 1.
4. Mostra apenas as cédulas e moedas com quantidade maior que zero.

## Testes

| Valor | Resultado |
|-------|-----------|
| 50    | Autorizado: 1 nota de 50 |
| 95    | Autorizado: 1 nota de 50, 2 notas de 20 e 1 nota de 5 |
| 123   | Autorizado: 1 nota de 100, 1 nota de 20, 1 nota de 2 e 1 moeda de 1 |
| 1005  | Erro: saldo insuficiente (máximo R$ 1000) |
| 0     | Erro: valor inválido (precisa ser maior que zero) |
| abc   | Erro: entrada inválida (precisa ser um número inteiro) |
