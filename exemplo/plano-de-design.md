# Plano de design: agendamento de revisão (exemplo)

> O que a skill escreve nos passos 4 e 5, antes de qualquer código. Marca fictícia, cânone em [`canone.md`](canone.md).

Pedido: "desenha a página de agendamento de revisão".

## Plano

```
Tela: agendamento de revisão · Marca: Contravento · Skin: balcão
Trabalho da tela: a pessoa escolhe serviço, dia e horário em menos de um minuto.
Cor: cal (fundo), brita (cartão de serviço e campos), asfalto (texto),
     graxa (rótulos), sinal (botão "Agendar revisão" e faixa), freio (horário indisponível)
Tipografia: Bricolage Grotesque 800 no título da etapa; Atkinson Hyperlegible no
     texto e nos campos; IBM Plex Mono nas etiquetas de etapa, preço e prazo
Layout: uma coluna no celular, etapa atual aberta e as outras recolhidas com o resumo.
  +--------------------------------+
  |////////// faixa ///////////////|
  | 01 / 04                        |
  | Que revisão a bicicleta pede?  |
  | +----------------------------+ |
  | | Revisão básica      R$ 90  | |
  | | PRONTA EM 2 DIAS           | |
  | +----------------------------+ |
  | +----------------------------+ |
  | | Revisão completa    R$ 180 | |
  | | PRONTA EM 4 DIAS           | |
  | +----------------------------+ |
  | 02 / 04  Dia                   |
  | 03 / 04  Horário               |
  | 04 / 04  Seu contato           |
  | [      Agendar revisão       ] |
  +--------------------------------+
Assinatura: a faixa no topo, uma vez; etapas e preços como etiqueta de peça.
Movimento: a etapa seguinte entra da direita em 320 ms quando a anterior é respondida;
     o cartão escolhido troca a borda pra asfalto em 160 ms. Com movimento reduzido,
     as duas viram troca de opacidade.
```

## Crítica

1. Parece o padrão de IA? Quase: a primeira ideia tinha três cartões lado a lado com ícone em cima. Trocado por lista em uma coluna, com preço e prazo em etiqueta.
2. Tirando o logo, dá pra saber de quem é? Sim: faixa e etiquetas em mono.
3. Fere regra dura? O preço aparece antes do horário, como a regra pede. O botão diz "Agendar revisão".
4. Token fora do cânone? Nenhum.
5. Repete armadilha anotada? A do amarelo em texto: o prazo ia em `sinal`, foi pra `graxa`.

Plano aprovado. Segue pra construção.
