# Arquivo Morto

Jogo de investigação criminal e dedução para telemóvel. Cada caso é um crime por resolver: lês as pistas, reconstróis numa planta onde estava cada pessoa no momento do crime e descobres o culpado.

Joga-se sozinho ou com 2 a 4 pessoas, cada uma no seu telemóvel.

https://bolinhared.github.io/ArquivoMorto/

## Como se joga

1. Escolhe um caso no **Arquivo de casos**.
2. Lê as tuas **pistas**. Há dois tipos:
   - **Declaração:** o que um suspeito diz. É verdadeira, a não ser que uma prova a desminta.
   - **Prova:** sempre verdadeira.
3. Coloca as seis pessoas na **planta** (6×6), onde estavam no momento do crime:
   - cada linha e cada coluna tem exactamente uma pessoa, incluindo a vítima;
   - não se pode ocupar obstáculos (móveis com fundo escuro);
   - a vítima fica na única posição que sobra.
4. **O culpado é a única pessoa que estava na mesma divisão que a vítima.** A arma é a da divisão da vítima.
5. Com a planta completa, faz a **acusação**: quem, com que arma e, como bónus, porquê.

### Pontuação

| Critério | Pontos |
| --- | --- |
| Caso resolvido (planta, culpado e arma) | 60 |
| Sem acusações erradas | 20 |
| Sem ajudas | 10 |
| Motivo certo (bónus) | 10 |

O jogo nunca diz qual dos elementos da acusação estava errado.

### Jogar em grupo

- Cada pessoa abre o jogo no seu telemóvel, escolhe o mesmo caso, o mesmo número de jogadores e um número de jogador diferente.
- Cada jogador recebe pistas diferentes. Só juntando-as se resolve o caso, por isso têm de conversar.
- Acusam juntos, num só telemóvel.
- **Variante competitiva:** todos escolhem «1 jogador» e ganha quem resolver primeiro.

Não é preciso internet nem servidor para jogar em grupo.

## Casos

| Caso | Título | Dificuldade | O que ensina |
| --- | --- | --- | --- |
| 001 | O Assassinato na Mansão Blackwood | Fácil | As regras da planta; mentiras desmentidas por provas |
| 002 | Morte no Expresso do Norte | Médio | Pistas relativas («duas colunas à direita de…») |

Todos os casos foram verificados por computador: têm uma única solução, todas as pistas são necessárias e resolvem-se sem tentativa e erro.

## Publicar no GitHub Pages

1. Cria um repositório novo no GitHub (por exemplo, `arquivo-morto`).
2. Carrega os ficheiros desta pasta (`index.html` e `README.md`) com **Add file › Upload files**.
3. Vai a **Settings › Pages**.
4. Em **Branch**, escolhe `main` e a pasta `/ (root)`. Carrega em **Save**.
5. Passado um ou dois minutos, o jogo fica disponível em `https://<o-teu-utilizador>.github.io/arquivo-morto/`.

O jogo é um único ficheiro `index.html`, com as imagens incluídas dentro dele. Também funciona se o abrires directamente no computador ou no telemóvel.

## Estrutura técnica

- HTML, CSS e JavaScript puros, num só ficheiro. Sem frameworks nem módulos.
- O progresso fica guardado no próprio dispositivo (`localStorage`), por caso.
- Tipos de letra: Courier Prime e Libre Franklin, do Google Fonts. Sem internet, o jogo usa tipos de letra do sistema.

### Acrescentar um caso

Os casos estão no array `CASES`, no início do `<script>` do `index.html`. Cada caso define:

- `people`: vítima e cinco suspeitos;
- `map`, `cells`, `div`: divisões, obstáculos e assentos da planta;
- `weapons`: uma arma por divisão;
- `cards`: as pistas (declarações e provas);
- `deal`: que pistas recebe cada jogador em 2, 3 e 4 jogadores;
- `sol`: a solução;
- `hints` e `reveal`: ajudas e revelação final.

Os retratos e os chãos de cada caso são escolhidos em `IMG` e `FLOORS`. Antes de publicar um caso novo, é preciso confirmar que a planta tem uma única solução.

## Créditos

- Retratos: [Free 39 Portraits Pixel Art Assets Pack](https://craftpix.net/), da Craftpix. Licença: https://craftpix.net/file-licenses/
- Mobília e chãos: Interior/Furniture Asset Pack, da Sierrassets.
- Inspiração: Murdle, Murdoku, Cluedo e Sherlock Holmes Consulting Detective.

## Estado

Protótipo jogável. Próximos passos: Casos 003 a 005, com mentiras escondidas, pistas negativas e plantas maiores; instalação como app (PWA).
