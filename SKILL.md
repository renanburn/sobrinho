---
name: sobrinho
version: 0.1.0
description: |
  Engenharia de design com a identidade de quem usa. Lê o cânone da marca
  (references/canone.md: tokens, tipografia, forma, assinatura, regras duras) e o
  aprendizado acumulado ANTES de desenhar ou reformar qualquer interface. Escolhe
  a skin da superfície, escreve um plano de design curto, critica o plano,
  constrói com os tokens reais, valida com screenshot e registra o que aprendeu.
  Com o cânone ainda vazio, entrevista o dono da marca pelo GUIA.md e preenche
  o cânone antes de desenhar.
  Use when: "desenha a tela", "reforma a home", "aplica a nossa identidade",
  "deixa com a nossa cara", "cria componente/landing/dashboard", "tá com cara de
  IA", "que token uso aqui", /sobrinho.
  NOT for: imagem gerada por IA, só reescrever texto, trocar uma cor num lugar
  só (faz direto).
argument-hint: "[briefing ou superfície] [--marca nome]"
---

# Sobrinho

Toda IA desenha bem e desenha parecido. Falta a ela saber quem é a marca: quais cores já estão no ar, que fonte carrega, o que essa marca nunca faz. O Sobrinho lê isso em `references/canone.md` antes de decidir qualquer coisa, e anota em `aprendizado/` o que cada tela ensinou.

Regra-mãe: **cada fato de design mora num lugar só.** Antes de criar token, cor, fonte, raio ou curva de animação, procura onde já existe (cânone, seção 1). Valor duplicado envelhece em dois lugares e a identidade se dilui.

## Antes de tudo: o cânone está preenchido?

Lê o cabeçalho de `references/canone.md`.

- `status: vazio`: para e entrevista. Segue o `GUIA.md` bloco por bloco, uma pergunta por vez, e escreve as respostas no cânone. Se o projeto já tem código, lê os arquivos de estilo primeiro e chega com as respostas prontas pra pessoa confirmar ou corrigir. Quando os blocos 1 a 8 tiverem resposta, troca pra `status: ativo`, põe a versão do dia e segue o fluxo.
- `status: ativo`: segue o fluxo abaixo.

Em nenhum dos dois casos a skill inventa identidade. O que o cânone deixa em branco vira pergunta pro dono da marca.

## O que esta skill faz e o que passa adiante

| Etapa | Quem faz |
|---|---|
| Identificar marca e superfície, escolher a skin | esta skill (cânone, seção 2) |
| Plano de design (tokens, tipografia, layout, assinatura, movimento) | esta skill |
| Construir na stack que o projeto já usa | esta skill |
| Texto da interface | a régua de voz do dono, se existir |
| Validar o visual | screenshot, com a ferramenta de navegador que o agente tiver |
| Registrar o que aprendeu e propor regra | esta skill (`aprendizado/`) |
| Aprovar regra nova no cânone | o dono da marca |

## Fluxo (copia e marca)

```
- [ ] 1. Ler references/canone.md inteiro, aprendizado/receituario.md e aprendizado/armadilhas.md
- [ ] 2. Cravar: marca, superfície, o trabalho único desta tela, quem usa
- [ ] 3. Abrir o arquivo de tokens REAL do projeto (o cânone, seção 1, diz qual é). Valor citado de memória não vale
- [ ] 4. Plano de design curto: 4 a 6 tokens de cor (dos que existem), papéis tipográficos, layout (1 frase + wireframe ASCII), assinatura (1 elemento), movimento (o que anima e por quê)
- [ ] 5. Crítica do plano, antes de escrever código (perguntas mais abaixo)
- [ ] 6. Construir. Cor, raio e fonte por token. Celular primeiro
- [ ] 7. Todo elemento que aparece, muda ou some tem entrada, permanência e saída decididas
- [ ] 8. Texto da interface revisado pela régua de voz da marca
- [ ] 9. Screenshot em 375 px e 1280 px, claro e escuro se o projeto tiver os dois. Olhar de verdade e tirar um acessório
- [ ] 10. Registrar em aprendizado/receituario.md (o que funcionou) ou aprendizado/armadilhas.md (o que quebrou). Se merece virar regra, PROPOR ao dono da marca
```

O passo 1 é o que faz a skill melhorar com o uso: ela só aprende se lê o que anotou. O passo 3 existe porque valor de token citado de memória troca um dígito e ninguém percebe até a tela estar no ar.

## Passo 2: escolher a skin

Skin é o jeito que a mesma marca se comporta numa superfície. Site de apresentação e painel de produto usam a mesma paleta e pedem densidade, raio e ritmo diferentes. A tabela de superfícies fica na seção 2 do cânone.

Superfície fora da tabela é decisão nova, e decisão nova é do dono da marca. Pergunta antes de derivar.

## Passo 4: o plano de design

Cabe numa tela de texto. Formato:

```
Tela: <nome> · Marca: <marca> · Skin: <skin>
Trabalho da tela: <uma frase>
Cor: <4 a 6 tokens e o papel de cada um>
Tipografia: <qual fonte faz título, texto e rótulo>
Layout: <uma frase>
  <wireframe ASCII>
Assinatura: <o elemento que faz a tela ser desta marca>
Movimento: <o que anima, quando, e o que isso informa>
```

Um exemplo preenchido está em `exemplo/plano-de-design.md`.

## Passo 5: a crítica do plano

Responde por escrito, uma linha cada:

1. Parece o padrão que toda IA entrega? Sinais comuns: roxo em gradiente, cartão de vidro fosco, creme com serifa e terracota, preto com verde-limão, três cartões iguais com ícone em cima.
2. Tirando o logo, dá pra saber de quem é a tela? Se a resposta é "de qualquer um", falta assinatura.
3. Fere alguma regra dura do cânone (seção 8)?
4. Usa token, fonte ou raio que o cânone desconhece?
5. Repete uma armadilha já anotada?

Plano que falha em qualquer uma volta pro passo 4.

## Piso de construção

Vale pra qualquer marca e qualquer stack. O gosto fica no cânone; aqui fica o que protege quem usa a tela.

1. Cor só por token (variável CSS, classe do tema, constante). Hex solto em componente é dívida: achou, converte.
2. Raio, sombra e espaçamento por token.
3. Contraste AA em texto: 4,5:1 no corpo, 3:1 em título grande.
4. Foco visível pra quem navega por teclado.
5. Toda animação atrás de `prefers-reduced-motion`. Animação informa mudança de estado; enfeite sai.
6. Em 375 px a tela funciona inteira, sem rolagem lateral.
7. Texto de botão diz o que acontece ao tocar.
8. Componente de terceiro: confere a licença no dia em que copia.

## Passo 9: olhar o screenshot

Código que compila e teste que passa deixam regressão visual escapar. Tira o screenshot nas duas larguras e compara com o plano: a assinatura aparece? A hierarquia lê na ordem certa? Algum texto quebrou feio?

Depois tira um acessório: o elemento que está ali só porque dava pra pôr.

Em reforma, tira o par antes e depois da mesma tela, no mesmo estado. Em app nativo, captura no simulador com fonte grande e no modo escuro.

## Passo 10: registrar e propor

- Funcionou e vale repetir: entrada em `aprendizado/receituario.md`, com data, tela e o motivo.
- Quebrou ou enganou: entrada em `aprendizado/armadilhas.md`, no formato sintoma, causa, regra.
- Merece virar regra do cânone: entra no receituário marcada **[proposta]**, com a tela onde foi testada. Só muda o cânone com o ok do dono da marca, e depois de aplicada em pelo menos uma tela real.

Os dois arquivos de aprendizado só crescem. Entrada antiga que deixou de valer ganha uma linha embaixo dizendo o que mudou.

## Quando o cânone e o código divergem

O código em produção manda. A skill avisa a divergência, pergunta qual dos dois está certo e corrige o lado errado. Ao mudar um fato no cânone, procura o mesmo valor nos outros arquivos do projeto e alinha, ou troca a cópia por um apontamento.

## Referências

- `references/canone.md`: a identidade da marca. Fonte da verdade, tokens, tipografia, forma, movimento, assinatura, regras duras, processo de atualização, dívidas
- `GUIA.md`: as perguntas que preenchem o cânone
- `aprendizado/receituario.md`: o que funcionou, por tela
- `aprendizado/armadilhas.md`: o que quebrou e como evitar
- `exemplo/`: cânone, plano, receituário e armadilhas de uma marca fictícia, pra ver o formato
