# Reddit Video Maker

Programa feito inspirado nos videos do [Canal do Filipe Deschamps](https://www.youtube.com/channel/UCU5JicSrEM5A63jkJ2QvGYw) no youtube

Videos feitos com o programa podem ser encontrados [aqui](https://www.youtube.com/channel/UCMhGMDIb1P1NEeqqW2zsPdw/)

## Pré-requisitos

- git
- Node

## Funcionalidades Principais

- Cria a imagem do Titulo
- Cria as imagens com as frases
- Usa a api Text-to-Speech do Google para gerar as falas
- Juntas as imagens com os arquivos de audio em clips
- Junta todos os clips em ordem pra gerar o video completo
- Faz upload automaticamente para o Youtube (Opcional)

## Instalação

Clone o repositorio em seu computador e na pasta raiz rode `npm install` ou `yarn`

```bash
# Clone this repository
$ git clone https://github.com/GMarroquio/RedditVideoMaker

# Go into the repository
$ cd RedditVideoMaker

# Install dependencies
$ yarn install
```

## Como usar

#### Credenciais

Dentro da pasta `credentials` cole a credencial do google cloud text-to-speech com o nome `tts.json`

Dentro do arquivo `links.json` cole todos os links que deseja transformar em video

```json
["reddit.com/r/...", "reddit.com/r/...", "reddit.com/r/..."]
```

#### Logo do subreddit

Dentro da pasta `assets/templates` cole o logo do sub com o nome do sub todo em minusculo e com a extenção `.png`

```
#exemplo
Para o subreddit r/ProRevenge
 - prorevenge.png
```

A imagem deve ter 60px x 60px

#### Final do video

Para o final do video, dentro da pasta `assets/video` cole o do fim com o nome `fim.mp3` e a imagem final com o nome `fim.png`. O programa ira gerar um arquivo chamado `fim.avi` que será usado em todos os videos. Se ja exister um arquivo `fim.avi` dentro da pasta, ele não é sobrescrito

#### Executar o programa

Abra o terminal e execute `yarn run`

Os videos serão salvos na pasta `videos`

### Upload automatico

Dentro da pasta `credential` cole a credencial do Youtube com o nome de `yt.json`

Na hora de executar o passe a flag -y

```bash
$ yarn start -y
```

obs: O limite de uploads da api gratuita do Youtube é de 10000 créditos por dia e cada video consome 1605 créditos, o que permite o envio de 6 videos por dia.

### Limpeza de arquivos

#### Dist

Caso não queira apagar os arquivos temporários execute o programa com a flag `-c:d`

```bash
$ yarn start -c:d
```

obs: Com essa flag o programa só fara o vídeo do primeiro link

#### Videos

Caso queira apagar os arquivos dentro da pasta de `videos` execute o programa com a flag `-c:v`

```bash
$ yarn start -c:v
```
