# Painel RUF 2026 · Unicatólica

Este repositório contém um painel estático para leitura gerencial do RUF 2026, com comparação entre a Unicatólica, FICR, Unileste e UCB.

## Estrutura

- `index.html`: interface, filtros, comparativos e visualizações. Não contém os rankings embutidos.
- `dados/manifest.json`: catálogo dos cursos, nomes oficiais, arquivos esperados e data da base.
- `dados/*.csv`: planilhas do RUF utilizadas pelo painel.

## Publicação no GitHub Pages

Envie `index.html`, a pasta `dados/` e este README para a raiz do repositório. Depois, em **Settings → Pages**, selecione a branch `main` e a pasta `/root`.

O painel usa caminhos relativos, por isso funciona em um repositório publicado como GitHub Pages mesmo quando o endereço inclui o nome do repositório.

## Atualização dos dados

Para atualizar um curso já existente, substitua o CSV correspondente dentro de `dados/`. Para adicionar um curso novo, coloque o CSV em `dados/` e inclua ou ajuste sua entrada em `dados/manifest.json`.

Os nomes das instituições comparadas são identificados pelos nomes oficiais presentes nos arquivos:

- Unicatólica: `Centro Universitário Católica de Quixadá`
- FICR: `Faculdade Católica Imaculada Conceição do Recife`
- Unileste: `Centro Universitário Católica do Leste de Minas Gerais`
- UCB: `Universidade Católica de Brasília`

O painel mantém a indicação **Não localizado** quando uma instituição não aparece em determinada carreira. Isso não significa posição zero.

## Abrir localmente

Como o navegador normalmente bloqueia `fetch()` quando um HTML é aberto diretamente por `file://`, prefira o GitHub Pages. Para testar localmente, execute na raiz do repositório:

```bash
python3 -m http.server 8000
```

Depois abra `http://localhost:8000`.

A importação de CSV pelo botão do painel continua disponível para testes temporários no navegador, mas não altera os arquivos do repositório.
