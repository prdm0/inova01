# AGENTS.md - Apresentacao Inovatec e SIS Ambiental

Este arquivo orienta qualquer sessao de trabalho nos slides Quarto da raiz do
projeto. Ele complementa, mas nao substitui, as regras tecnicas da aplicacao em
`desenvolvimento_projeto/AGENTS.md`.

## Objetivo da apresentacao

A apresentacao em `index.qmd` comunica, em junho de 2026, o estado atual do
projeto de inteligencia artificial para automatizacao de calculos no
licenciamento ambiental. A narrativa deve deixar claro o que ja foi feito, o
que esta funcionando e quais validacoes ainda dependem da area tecnica.

## Arquivos principais

- `index.qmd`: fonte unica do conteudo dos slides.
- `style.scss`: tema visual do RevealJS.
- `_quarto.yml`: projeto Quarto com saida em `docs/`.
- `docs/index.html`: resultado compilado da apresentacao.
- `imgs/`: imagens, prints e diagramas usados nos slides.
- `codigos_html/`: animacoes e iframes ja usados na apresentacao.
- `desenvolvimento_projeto/`: aplicacao web, motor, orquestrador, RAG e laudos.

## Regra de saida

Todo conteudo compilado deve estar em `docs/`. Sempre renderize a partir da raiz
com `quarto render index.qmd` ou `quarto render` antes de considerar o trabalho
concluido.

## Padrao visual dos slides

- Manter o formato RevealJS em `1920 x 1080`.
- Preservar o tema atual, as cores de `style.scss`, o rodape e o logo.
- Usar textos curtos, com no maximo 5 a 6 itens por frame.
- Evitar URLs longas visiveis. Use rotulos curtos para links.
- Evitar tabelas densas e imagens pequenas demais para leitura.
- Imagens e screenshots devem respeitar os limites do frame.
- Conteudo novo nao deve depender de rolagem para ser apresentado.
- Se houver duas colunas, usar proporcoes ja adotadas, como `55% / 45%`,
  `50% / 50%` ou `45% / 55%`.
- Classes novas em `style.scss` devem ser pequenas, reaproveitaveis e restritas
  aos novos slides.

## Linguagem

- Escrever em portugues do Brasil, com acentos corretos.
- Usar linguagem direta e institucional.
- Evitar cliches de inteligencia artificial.
- Nao prometer reducao de prazo ou ganho quantitativo sem validacao.
- Preferir "foi implementado", "esta em teste" e "esta em validacao" quando
  o status for real.
- Separar claramente entrega tecnica de validacao institucional.
- Nao afirmar calculos normativos novos sem consultar `desenvolvimento_projeto/`
  e suas fontes.

## Conteudo factual ja identificado

- A aplicacao web Shiny existe e opera como wizard de entrada.
- O motor deterministico em R usa Plumber e concentra os calculos normativos.
- O orquestrador em Python usa FastAPI para coordenar extracao, RAG, motor e
  geracao de texto do laudo.
- A LLM nao deve calcular valores numericos. Os calculos ficam no motor R.
- O RAG usa textos estruturados da LUOS e da NA-101 como base normativa.
- O relatorio tecnico e gerado em PDF com Quarto.
- A stack Docker Compose contem `motor`, `orquestrador`, `interface` e `ollama`.

## Capturas da aplicacao

Antes de usar screenshots nos slides:

- Verificar se `http://localhost:3838/` esta acessivel.
- Capturar a landing page, o wizard e, quando possivel, a revisao ou resultado.
- Salvar imagens em `imgs/` com nomes claros, por exemplo
  `sis_ambiental_landing.png`.
- Nao usar prints com erros, spinners permanentes ou campos vazios quando isso
  prejudicar a narrativa.
- Se a geracao de laudo depender de servico externo indisponivel, comunicar que
  a captura mostra o fluxo ate a etapa de confirmacao.

## Onde inserir novos slides

Os novos frames de progresso devem ficar entre `Objetivos Especificos` e a secao
`Como funciona o sistema hoje?`. Esse ponto faz a ponte entre a proposta original
e a demonstracao do prototipo.

## Sequencia recomendada dos novos frames

1. O que ja foi construido.
2. Arquitetura implementada.
3. Interface web em operacao.
4. Calculo auditavel e separacao de responsabilidades.
5. Relatorio tecnico automatico e proximas validacoes.

## Validacao obrigatoria

Antes de encerrar uma tarefa nos slides:

- Rodar `quarto render index.qmd`.
- Confirmar que `docs/index.html` foi atualizado.
- Revisar visualmente os novos frames no navegador quando possivel.
- Verificar se imagens usadas no deck existem em `imgs/` ou `codigos_html/`.
- Verificar se nao houve overflow horizontal aparente.

## Agentes recomendados

Use os agentes de `.opencode/agent/` quando a tarefa envolver mais de uma etapa:

- `slides-content-researcher`: pesquisa factual no projeto de desenvolvimento.
- `slides-story-editor`: transforma achados em narrativa simples para slides.
- `slides-screenshot-operator`: planeja e executa capturas da aplicacao.
- `slides-visual-compliance`: revisa frame, tipografia, cor e limites visuais.
- `slides-render-reviewer`: valida renderizacao Quarto e saida em `docs/`.
