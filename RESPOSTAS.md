# Respostas da dupla — Atividade PontoCerto

## Dupla

| Papel | Nome completo | Usuário do GitHub |
|---|---|---|
| Integrante 1 | Lucas Calixto | lucas-calixto-lemos |
| Integrante 2 | Sérgio Bione | |

## Explicação da solução

Antes cada campanha precisava de uma função de cálculo nova, quase igual às outras. Agora a gente tem só um `calculaPontos`, que recebe a regra como argumento e aplica no valor, então pra campanha nova basta passar outra regra. E as fábricas (`campanhaMultiplicadora` e `campanhaBonus`) criam as regras a partir de um número, assim não precisa escrever uma função pra "vezes 3", outra pra "vezes 5" etc, é só chamar `campanhaMultiplicadora 3` ou `campanhaMultiplicadora 5`.

## Desafio 2

Porque essas promoções só duram um dia e a regra é bem curta (`\p -> p * 3` e `\p -> p * 2 + 10`). Não vale a pena criar uma função com nome que só vai ser usada uma vez, então a gente escreve a regra direto na chamada do `calculaPontos`.

## Desafio 3

Não devolve um número, devolve outra função (uma regra que multiplica os pontos por 5). Ela ainda tá esperando receber os pontos. O `:t campanhaMultiplicadora 5` mostra `Int -> Int`, que é o tipo de uma função que recebe um Int e devolve um Int. Se fosse um número ia aparecer só `Int`. Por isso o `:t blackFriday` também dá `Int -> Int`.

## Desafio 4

**a)** Porque a ordem muda a conta. No primeiro, multiplica primeiro e depois soma o bônus: 150 * 5 = 750, + 200 = 950. No segundo, soma o bônus primeiro e depois multiplica tudo: (150 + 200) * 5 = 1750, ou seja, o bônus também acaba sendo multiplicado por 5.

**b)** Tem que ser primeiro `blackFriday` e depois `aniversarioCliente`, ou seja, `acumula blackFriday aniversarioCliente`. Assim a multiplicação acontece antes e o bônus de 200 só é somado no final, sem ser multiplicado.

## Desafio 5 — revisão de código

| Erro | Função | O que estava errado | Como o GHC avisou (resumo da mensagem) | Como corrigimos |
|---|---|---|---|---|
| 1 | `fimDeSemana` | A lambda usava `=>` em vez de `->` (`\p => p * 4`), que é o jeito do JavaScript | `parse error on input '=>'` | Trocamos para `\p -> p * 4` |
| 2 | `aplicaRegraDuasVezes` | A assinatura dizia que o primeiro argumento era `Int`, mas `regra` é usada como função | Não consegue casar o tipo: `regra` tem tipo `Int` mas está sendo aplicada a um valor como se fosse função | Mudamos a assinatura para `(Int -> Int) -> Int -> Int` |
| 3 | `natal` | Faltava passar o bônus de 300 para a fábrica, então `natal` ficava sendo a própria `campanhaBonus` (`Int -> (Int -> Int)`) e não uma regra | `Couldn't match type`: esperava `Int -> Int` e recebeu `Int -> Int -> Int` | Escrevemos `natal = campanhaBonus 300` |
| 4 | `promocaoAtual` | `pontosEmDobro 100` já calcula o número 200, então guardava um `Int` e não a função | `Couldn't match expected type 'Int -> Int' with actual type 'Int'` | Tiramos o `100`: `promocaoAtual = pontosEmDobro` |

## Desafio 6 — Haskell × C

1. Em Haskell o tipo da regra é só `(Int -> Int)`, já em C tem que usar a sintaxe de ponteiro para função `int (*regra)(int)`, que é bem mais confusa.
2. Em Haskell dá pra passar uma lambda direto pro `calculaPontos` (como na Promoção Relâmpago) e criar regras com as fábricas. Em C não tem lambda, então toda regra precisa ser uma função com nome escrita antes (`pontosEmDobro`, `bonus50`).

## Evidência de execução

Saída do `main` de `fidelidade.hs`:

```text
(cole aqui)
```

Saída do `main` de `revisao.hs` (depois de corrigido):

```text
(cole aqui)
```

Saída de `pontocerto.c`:

```text
160
130
250
300
```
