# Guia: escreva o cânone da sua marca

O cânone é um markdown que diz, pra você e pra qualquer IA que desenha com você, como a sua marca aparece numa tela: que cores usa e pra quê, que fonte faz cada papel, o que faz uma tela ser sua e o que ela nunca faz.

Este guia leva do zero a um cânone que funciona. A primeira versão sai em uma ou duas horas. Depois ele cresce aos poucos, uma tela por vez.

Dois jeitos de fazer:

- **Na conversa.** Instala a skill e chama `/sobrinho`. Com o cânone vazio, ela faz estas perguntas uma por vez e escreve as respostas no arquivo.
- **Na mão.** Responde aqui e preenche [`references/canone.md`](references/canone.md).

## Passo 1: junta o material

Identidade se observa no que já existe. Separa:

- Três telas, peças ou páginas que ficaram com a cara da marca.
- Três que ficaram sem graça ou "não era isso".
- Se já existe código, o arquivo onde as cores e fontes estão declaradas.
- Se já existe manual de marca, o PDF ou o link.

Marca nova, sem nada disso? Junta três referências de fora que você queria ter feito e anota o que te atrai em cada uma. O cânone começa menor e tudo bem.

## Passo 2: responde os blocos

Anota as respostas cruas. A arrumação vem no passo 3.

### Bloco 1: a marca

- Em uma frase, o que a marca faz e pra quem?
- Se ela fosse um lugar físico, qual seria? (Oficina, cartório, feira, consultório, estúdio.)
- Três adjetivos que descrevem o jeito dela. E três que ela não é de jeito nenhum.
- Existe mais de uma marca debaixo do mesmo teto? Qual é a mãe, qual é a filha, quais nunca se misturam?

### Bloco 2: as superfícies

- Onde a marca aparece em tela? Lista tudo: site, app, painel, loja, e-mail, apresentação.
- Em cada uma, a pessoa está fazendo o quê? Conhecendo, comprando, trabalhando o dia inteiro?
- Qual superfície pode ser mais solta e qual precisa ser mais densa e sóbria?

Daqui sai a tabela de skins: a mesma marca com comportamentos diferentes por superfície.

### Bloco 3: a cor

- Quais cores a marca já usa? Escreve o valor exato (hex) de cada uma, copiado do código ou do manual.
- Qual é a cor de assinatura, aquela que basta ver pra saber que é você?
- Qual cor faz o fundo, qual faz o texto, qual avisa erro?
- A cor de assinatura funciona como texto pequeno sobre o fundo? Mede o contraste (precisa de 4,5:1). Se falhar, define uma variante mais escura só pra texto.
- Quanto de cada cor cabe numa tela? (Exemplo: fundo e texto 90%, assinatura 5%.)
- Tem modo escuro? Se tem, quais valores mudam?
- Dá um nome próprio pra cada cor. Nome ajuda a IA e ajuda você: `sinal` diz mais que `amarelo-2`.

### Bloco 4: a tipografia

- Qual fonte faz os títulos? Qual faz o texto corrido? Tem uma terceira pra rótulo, número ou código?
- Você tem licença pra usar cada uma na web? De onde ela é carregada?
- Título é grande e pesado ou discreto? Caixa alta aparece onde?
- Qual é o menor tamanho de texto que você aceita?

Três fontes dão conta de quase toda marca. Cada fonte a mais precisa de um motivo escrito.

### Bloco 5: a forma

- Canto reto, pouco arredondado ou bem redondo? Escreve o valor: botão, campo, cartão.
- Tem sombra? Onde, e com que função?
- O que separa um bloco do outro: linha fina, cor de fundo, espaço?
- Ícone: de qual família, com traço ou preenchido, colorido ou de uma cor só?
- Foto e ilustração: de que tipo, feitas por quem, com que tratamento?

### Bloco 6: o movimento

- A marca se mexe rápido e seco ou devagar e macio?
- O que anima: troca de página, abertura de menu, número mudando, entrada de conteúdo na rolagem?
- Qual a duração de uma animação curta e de uma longa? (Ponto de partida comum: 150 a 250 ms e 300 a 500 ms.)
- O que acontece com tudo isso quando a pessoa pede menos movimento no sistema dela?

### Bloco 7: a assinatura

A pergunta que mais vale: **tirando o logo, o que faz uma tela ser sua?**

- Um elemento gráfico que se repete (uma faixa, um carimbo, uma moldura, um jeito de numerar).
- Um jeito de tratar número, data ou rótulo.
- Um tipo de foto ou de ilustração.
- Um gesto de layout (título enorme, muita margem, grade apertada).

Escolhe um ou dois e diz quantas vezes cada um aparece por tela. Assinatura usada em todo canto vira ruído.

### Bloco 8: o que a marca nunca faz

A lista que mais protege a identidade. Olha pras três telas que ficaram sem graça e anota o que estragou cada uma.

- Que recurso visual te dá arrepio? (Gradiente, brilho, vidro fosco, botão em formato de pílula, emoji na interface.)
- Que tipo de imagem está proibido? (Banco de imagem, gente sorrindo pra câmera, ilustração genérica.)
- Que combinação de cores nunca aparece junta?
- O que a concorrência faz e você quer distância?

Escreve cada item como regra curta, com o motivo ao lado quando ele existir. Regra com motivo sobrevive a exceção; regra solta vira mania.

### Bloco 9: onde mora cada coisa

- Em que arquivo estão os tokens de cor, fonte e raio? Esse arquivo manda.
- Qual é a stack do projeto? (Framework, biblioteca de estilo, biblioteca de animação, biblioteca de componentes.)
- Existe um segundo lugar com os mesmos valores (manual, Figma, outra pasta)? Qual dos dois vence quando discordam?
- Quem aprova uma regra nova?

## Passo 3: passa pro cânone

Preenche [`references/canone.md`](references/canone.md) com as respostas. Três cuidados:

- **Valor exato.** `#f2b705` no lugar de "amarelo forte". 6 px no lugar de "cantinho arredondado".
- **Uso ao lado do valor.** Token sem papel definido acaba usado em tudo.
- **Curto.** O cânone que funciona cabe em duas ou três telas de rolagem. Bloco sem resposta fica em branco com um "decidir" ao lado, e a skill pergunta quando precisar.

Antes de encarar o seu, lê o [`exemplo/canone.md`](exemplo/canone.md) pra ver o formato preenchido.

Quando os blocos 1 a 8 tiverem resposta, troca o cabeçalho do arquivo pra `status: ativo` e põe a data na versão.

## Passo 4: testa numa tela pequena

Escolhe uma tela de baixo risco (uma página de contato, um cartão, um formulário) e pede:

```text
/sobrinho desenha a página de contato
```

Olha o plano de design que ela escreve antes do código. Se o plano saiu com a cara da marca, o cânone está bom. Se saiu genérico, o bloco 7 (assinatura) ou o bloco 8 (o que nunca faz) está raso: volta neles.

## Passo 5: mantém vivo

O cânone muda devagar e por decisão sua. O aprendizado cresce a cada tela.

- Um jeito de resolver funcionou e vale repetir? A skill anota em `aprendizado/receituario.md`.
- Algo quebrou ou enganou? Vai pra `aprendizado/armadilhas.md`, com sintoma, causa e regra.
- Uma receita se provou em tela real e você quer que vire lei? Aprova, e ela sobe pro cânone com versão nova.

Sem esse filtro, cada conversa com a IA cria uma regrinha e em dois meses o cânone contradiz a si mesmo. Com ele, a skill propõe e você decide.

## A fronteira

O cânone descreve a sua marca. Copiar o cânone de outra marca dá uma tela que parece a dela, feita pior. O exemplo deste kit serve de molde de formato e para aí.
