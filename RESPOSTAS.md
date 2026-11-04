# Respostas da dupla — Atividade PontoCerto

## Dupla

| Papel | Nome completo | Usuário do GitHub |
|---|---|---|
| Integrante 1 | Lucas Calixto | lucas-calixto-lemos |
| Integrante 2 | Sérgio Bione | |

## Explicação da solução

<!-- 3 a 5 linhas: como calculaPontos e as fábricas de campanhas eliminam a repetição de código? -->

## Desafio 2

Porque essas promoções só duram um dia e a regra é bem curta (`\p -> p * 3` e `\p -> p * 2 + 10`). Não vale a pena criar uma função com nome que só vai ser usada uma vez, então a gente escreve a regra direto na chamada do `calculaPontos`.

## Desafio 3

Não devolve um número, devolve outra função (uma regra que multiplica os pontos por 5). Ela ainda tá esperando receber os pontos. O `:t campanhaMultiplicadora 5` mostra `Int -> Int`, que é o tipo de uma função que recebe um Int e devolve um Int. Se fosse um número ia aparecer só `Int`. Por isso o `:t blackFriday` também dá `Int -> Int`.

## Desafio 4

**a)** <!-- Por que as duas ordens dão resultados diferentes? -->

**b)** <!-- Qual ordem garante que o bônus de aniversário não seja multiplicado? Por quê? -->

## Desafio 5 — revisão de código

| Erro | Função | O que estava errado | Como o GHC avisou (resumo da mensagem) | Como corrigimos |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |

## Desafio 6 — Haskell × C

<!-- Cite duas diferenças entre o calculaPontos em Haskell e o calculaPontos em C. -->

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
(cole aqui)
```
