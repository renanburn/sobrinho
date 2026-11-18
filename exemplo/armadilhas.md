# Armadilhas: Contravento (exemplo)

> Exemplo preenchido, de marca fictícia. Mostra o formato sintoma, causa, regra.

## 2026-03-12 · agendamento de revisão

- **Amarelo como texto.** Sintoma: o prazo "PRONTA EM 2 DIAS" em `sinal` sumia na tela do celular ao sol. Causa: `sinal` sobre `cal` tem contraste de 1,71:1. Regra: amarelo em texto ou ícone usa `sinal-texto`; `sinal` puro só em área (botão, faixa).
- **Valor de token citado de memória.** Sintoma: o botão saiu num amarelo mais claro que o da faixa. Causa: o hex foi digitado de cabeça, com um dígito trocado. Regra: abrir `tokens.css` antes de escrever qualquer cor, e usar a variável.

## 2026-03-20 · início do site

- **Faixa repetida.** Sintoma: a página ficou com cara de canteiro de obras. Causa: uma faixa em cada seção, cinco no total. Regra: uma faixa por tela, no começo da área principal (virou regra dura no cânone).
- **Título quebrando em quatro linhas.** Sintoma: em 375 px o título empurrava a foto pra fora da primeira tela. Causa: tamanho fixo pensado pro computador. Regra: título com tamanho fluido e teste em 375 px antes de olhar a versão larga.

## 2026-04-02 · e-mail de confirmação

- **Fonte que não chega.** Sintoma: no leitor de e-mail o título caiu numa serifa do sistema. Causa: a maioria dos leitores de e-mail ignora fonte carregada de fora. Regra: e-mail usa a pilha de fontes do sistema e leva a identidade pela faixa e pelas etiquetas.
