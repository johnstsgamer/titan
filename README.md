# Kit para Figma Make — Titan Play

Este pacote reúne telas, marca, mídias e benchmarks para montar a versão mobile vertical do Titan Play no Figma Make. As telas de produto e os assets do Titan são os materiais de uso; as referências de mercado servem somente de inspiração e não devem ser copiadas.

## Importação recomendada

1. Leia e cole o conteúdo de [`prompt.md`](prompt.md) no Figma Make.
2. Importe primeiro os arquivos `00-*-conceito.png` de `01-telas-mobile/`; eles definem a direção visual de maior fidelidade.
3. Use `01-home.png` a `16-suporte.png` para cobrir os fluxos: home, ao vivo, EPG, catálogo, busca, detalhes, player, lista, recentes, ajustes e suporte.
4. Importe `02-assets/marca/` antes de qualquer outra mídia: o Make deve usar estes PNGs em header, splash e avatar.
5. Use os posters de filmes/séries e os SVGs fictícios de `02-assets/canais/` como conteúdo de demonstração. As imagens dentro de `03-referencias-mercado/` não entram no produto final.

## Estrutura

| Pasta | Conteúdo |
| --- | --- |
| `01-telas-mobile/` | 7 referências de conceito e 16 telas de fluxo em 1206 × 2622 px. |
| `02-assets/filmes/` | 3 posters fictícios, sem texto, para o catálogo de filmes. |
| `02-assets/series/` | 3 posters fictícios, sem texto, para o catálogo de séries. |
| `02-assets/canais/` | 6 logos/cartões vetoriais fictícios: Titan News, Arena, Cine Prime, Mundo Doc, Som FM e Play Kids. |
| `02-assets/marca/` | 5 variações oficiais do Titan: logo completo, wordmarks e avatar. |
| `02-assets/poster-collection-filmes-e-series.png` | A prancha original dos seis posters, caso seja útil como painel de referência. |
| `03-referencias-mercado/referencias/` | Benchmark preservado de apps de streaming/IPTV: screenshots, metadados e relatórios. Não usar como asset de produto. |
| `03-referencias-mercado/referencias-origem.zip` | Arquivo de origem, mantido para rastreabilidade. |
| `prompt.md` | Prompt canônico, já estruturado, para colar no Figma Make. |

## Uso da marca

- `01-logo-completo.png`: splash, onboarding e capa de apresentação.
- `02-wordmark-vinho.png`: aplicação em fundos claros ou vinho.
- `03-wordmark-claro.png`: header escuro e peças de comunicação claras.
- `04-wordmark-escuro.png`: hero e superfícies escuras.
- `05-avatar-titan.png`: avatar de perfil, favicon ou ícone de app — nunca como personagem repetido em cards de catálogo.

## Como usar as referências de mercado

- Priorize `uhf/`, `iptvx/` e `xciptv/` para hierarquia de conteúdo, hero e catálogo; não replique a UI ou marcas deles.
- Consulte `tivimate-android/` para entender a densidade do guia em tela grande e `recentes/` para padrões de onboarding, player e estados vazios.
- Use `purple/`, `mega-iptv/` e `flix-pro/` como anti-referências: não adotar dashboards genéricos, gradientes dominantes nem jargão técnico na home.
- A curadoria e os padrões extraídos estão documentados em `03-referencias-mercado/referencias/INDEX.md` e `extracao-design-referencias.md`.

## Regras visuais

- Fundo: `#090A0C`; superfícies: `#16171C`; superfície elevada: `#202126`.
- Ação/aba ativa: `#D81022`; nota, selo e favorito: `#D6A540`.
- Texto: `#F4F2EE`; metadados: `#A4A3AD`.
- Use SF Pro (ou Inter como fallback), grade de 8 pt, cards com 16 pt e botões com 18 pt de raio.
- A tab bar só aparece nas rotas raiz: Início, Ao vivo, Filmes, Séries e Buscar.
- Para detalhes, player, EPG, favoritos, recentes, ajustes e suporte, use botão Voltar — sem tab bar.

## Prompt para o Figma Make

O prompt completo e atualizado fica em [`prompt.md`](prompt.md). A versão curta abaixo é só uma visão geral:

```text
Crie um app iOS vertical chamado Titan Play, um streaming premium em português do Brasil. Use as telas importadas com prefixo 00 como direção visual principal e as demais como referência de fluxos. A interface precisa parecer nativa, escura e cinematográfica: fundo #090A0C, cards #16171C, CTA e aba ativa #D81022, notas e selos #D6A540, texto #F4F2EE e secundário #A4A3AD. Use SF Pro, espaçamento de 8 pt, cards com 16 pt e botões com 18 pt.

Monte os fluxos: abertura, onboarding (nome e gêneros), home com hero e trilhos horizontais, filmes, séries, detalhe de filme, detalhe de série com temporadas/episódios, ao vivo, guia EPG, busca vazia e com resultado, player, favoritos, recentes, ajustes e suporte. Use os PNGs em 02-assets/filmes e 02-assets/series como capas, e os SVGs em 02-assets/canais como logos do Ao vivo/EPG. Todas as artes e canais são fictícios.

Na home, destaque um hero com gradiente até o fundo e CTAs “Assistir” e “Minha lista”. Na raiz, a navegação inferior tem Início, Ao vivo, Filmes, Séries e Buscar; a aba ativa é vermelha com indicador inferior. Nas rotas profundas, esconda a tab bar e mostre voltar circular de 44 × 44 pt. Para EPG, faça loading, sem programação, erro e conteúdo — nenhuma área preta grande pode parecer falha. Para busca, crie idle, carregando, resultado, vazio e erro.
```

## Observação sobre as artes

Os posters e logos novos são fictícios e foram criados apenas como placeholders visuais para prototipagem. Substitua-os pelos metadados, licenças e materiais oficiais antes de publicar o app.
