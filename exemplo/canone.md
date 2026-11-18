---
status: ativo
versao: 2026.03.10.1
marca: Contravento
---

# Cânone de design: Contravento (exemplo)

> Exemplo preenchido pra você ver o formato. A Contravento é uma marca fictícia, inventada pra este kit: bicicletaria de bairro, com oficina e loja, um site e uma página de agendamento de revisão. Qualquer semelhança com marca real é coincidência. Use como molde de formato; o seu cânone é outro.

## 0. Regra-mãe

Cada fato de design mora num lugar só; os outros apontam. Quando este arquivo e o código em produção divergirem, o código manda e este arquivo é corrigido.

## 1. Onde mora cada coisa

| O quê | Arquivo que manda | Quem consome |
|---|---|---|
| Tokens de cor | `src/styles/tokens.css` | site e agendamento |
| Fontes | `src/styles/fontes.css` (arquivos em `public/fontes/`) | site e agendamento |
| Raio, sombra, espaçamento | `src/styles/tokens.css` | site e agendamento |
| Movimento | `src/styles/tokens.css` | site e agendamento |
| Componentes base | `src/componentes/base/` (botão, campo, cartão, faixa) | site e agendamento |

Stack do projeto: HTML e CSS com variáveis, sem biblioteca de estilo. Um script pequeno pro calendário do agendamento.

Quem aprova regra nova: a dona da oficina.

## 2. Marca e superfícies

A marca em uma frase: oficina de bairro que conserta a bicicleta que você já tem, antes de te vender outra.

Três adjetivos que ela é: prática, franca, de mão na graxa.

Três que ela não é: esportiva de elite, fofa, tecnológica.

| Superfície | Skin | O que a pessoa faz ali | Densidade |
|---|---|---|---|
| Site (início, serviços, a oficina) | **vitrine** | conhece a oficina e decide se confia | solta: título grande, foto, muito respiro |
| Agendamento de revisão | **balcão** | escolhe serviço, dia e horário em menos de um minuto | densa: formulário, sem foto, tudo visível sem rolar |
| E-mail de confirmação | **balcão** | confere o que marcou | uma coluna, só texto e a faixa |

Superfície fora da tabela (loja com carrinho, por exemplo) é decisão nova: perguntar antes de derivar.

## 3. Cor

| Token | Valor | Uso | Contraste sobre `cal` |
|---|---|---|---|
| `cal` | `#f7f8f5` | fundo | |
| `brita` | `#eceee8` | fundo de cartão e de campo | |
| `asfalto` | `#1c1f24` | texto principal, listra escura da faixa | 15,5:1 |
| `graxa` | `#566070` | texto secundário, rótulo | 5,96:1 |
| `sinal` | `#f2b705` | assinatura: botão principal e faixa | 1,71:1, nunca como texto |
| `sinal-texto` | `#7a5900` | o amarelo quando precisa ser texto ou ícone | 6,05:1 |
| `freio` | `#c2362b` | erro e aviso de horário indisponível | 5,11:1 |
| `linha` | `asfalto` a 12% | divisória | |

Texto sobre o botão `sinal` é sempre `asfalto` (9,09:1).

Proporção por tela: `cal` e `brita` 85%, `asfalto` e `graxa` 10%, `sinal` até 5%. `freio` só aparece em erro.

Modo escuro: fora da primeira versão, por decisão. A oficina atende de dia e o site segue igual.

## 4. Tipografia

| Papel | Fonte | Pesos | De onde carrega |
|---|---|---|---|
| Título | Bricolage Grotesque | 700 e 800 | arquivo próprio em `public/fontes/` (licença OFL) |
| Texto | Atkinson Hyperlegible | 400 e 700 | arquivo próprio (licença OFL) |
| Rótulo, número, preço | IBM Plex Mono | 500 | arquivo próprio (licença OFL) |

Menor tamanho de texto: 15 px.

Caixa alta aparece em: rótulo em mono, com espaçamento de 0,08em. Título nunca vai em caixa alta.

## 5. Forma

| Elemento | Raio |
|---|---|
| Botão e campo | `--raio-controle: 6px` |
| Cartão | `--raio-cartao: 10px` |

Sombra: nenhuma. Cartão se separa pelo fundo `brita` e pela `linha`.

O que separa blocos: espaço em múltiplos de 8 px; `linha` só entre itens de lista.

Ícones: traço de 1,5 px, uma cor só (`asfalto` ou `graxa`).

Foto e ilustração: foto da oficina de verdade, luz do dia, mão com graxa pode. Sem ilustração.

## 6. Movimento

| Token | Valor | Uso |
|---|---|---|
| `--curva-padrao` | `cubic-bezier(0.2, 0.8, 0.2, 1)` | toda transição de interface |
| `--tempo-curto` | `160ms` | botão, campo, troca de estado |
| `--tempo-longo` | `320ms` | abertura de painel, troca de etapa |

O que anima: troca de etapa no agendamento (a etapa nova entra da direita), confirmação de horário escolhido, erro de campo. No site, só a troca de foto da oficina.

Com movimento reduzido: tudo vira troca de opacidade em `--tempo-curto`.

## 7. Assinatura

O que faz uma tela ser da Contravento, tirando o logo:

- **A faixa.** Listras diagonais `sinal` e `asfalto`, 8 px de altura, como fita de sinalização de obra. Marca o começo da área principal.
- **A etiqueta de peça.** Etapa, preço e prazo em mono, no formato de etiqueta: `01 / 04`, `R$ 90`, `PRONTA EM 2 DIAS`.

Quantas vezes por tela: uma faixa. Etiquetas, quantas a informação pedir.

## 8. Regras duras

- Amarelo `sinal` nunca em texto sobre fundo claro: o contraste é 1,71:1. Texto amarelo usa `sinal-texto`.
- Uma faixa por tela. Duas viram enfeite.
- Faixa sempre chapada, em duas cores. Fita de sinalização com degradê deixa de parecer fita.
- Sem foto de banco de imagem. Ciclista de lycra em estrada vazia é o oposto do bairro.
- Sem linguagem de competição: cronômetro, ranking e pódio ficam fora. Quem vem aqui usa a bicicleta pra ir trabalhar.
- Peça e serviço com nome de oficina (câmara, pastilha, cabo de freio), nunca com código de catálogo.
- Botão diz o que acontece: "Agendar revisão", nunca "Enviar".
- Preço sempre visível antes de a pessoa escolher o horário. Franqueza é parte da marca.

## 9. Como atualizar

1. Mudou um valor: muda primeiro em `src/styles/tokens.css`, depois aqui.
2. Regra nova: entra como **[proposta]** em `receituario.md`, com a tela onde foi testada. Sobe pra cá com o ok da dona e depois de aplicada em uma tela real.
3. Cada mudança aqui ganha versão nova, pela data.

## 10. Dívidas conhecidas

1. A página "A oficina" ainda usa um cinza fora dos tokens no rodapé.
2. O e-mail de confirmação carrega a fonte do sistema: as fontes da marca ainda não foram testadas nos leitores de e-mail.
