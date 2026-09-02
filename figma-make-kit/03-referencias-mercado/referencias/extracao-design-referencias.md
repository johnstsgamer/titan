# Extração de padrões — referências de design (Titan Play)

**Data:** 2026-08-30 · **Fonte:** `referencias/` (INDEX.md + RELATORIO-LANCAMENTOS-RECENTES.md + screenshots App Store)
**Método:** leitura visual de Tier 1 completo (uhf/, iptvx/, xciptv/), benchmark tivimate-android/, 4 priorizados de recentes/ (xciptv-player, iptv-core, watchup, aerial-tv), Tier 2 (smarters-lite, ibo-pro, implayer) e anti-padrão purple/. Citações no formato `app/arquivo.jpg`.
**Consumidores:** docs/16-design-system-spec.md (tokens), docs/17-screen-inventory.md (telas), PRD §3 ("Titan Standard").

---

## Bloco 1 — PADRÕES POR TELA

### 1.1 Home / biblioteca

**Estrutura canônica dos Tier 1 (topo → baixo):**

1. **Top bar mínima** — IPTVX (`iptvx/01.jpg`): tabs de escopo no topo ("Movies / Favorites / Live TV / DB Queue") + avatar à direita; XCIPTV (`xciptv/02.png`): logo circular pequeno + **search pill cinza-escura full-width**. UHF (`uhf/02.jpg`): dropdown "Home ˅" + busca. Nenhum usa tab bar com 5 itens no estilo premium; WatchUp (recente BR, `watchup-iptv-player/01.jpg`) é o contra-exemplo com tab bar 5 itens (Início/Filmes/Séries/Minha Lista/Busca).
2. **Hero banner carrossel** (~55–60% da altura): backdrop full-bleed com gradiente preto na base (IPTVX `iptvx/01.jpg`, XCIPTV `xciptv/02.png`); WatchUp usa **hero em card com radius ~16 e margens laterais** em vez de full-bleed — variação mais "iOS nativa". Título grande (logotipo do filme quando há), 1–2 linhas de sinopse cinza, gêneros separados por "·", **pill branca primária** ("Play"/"▶ Videos") + pill escura secundária ("+ Add"), page dots finos à direita. IPTVX usa 3 ações em linha sob o hero (Favorites/Play/Info, ícone sobre label ~11pt).
3. **Rows horizontais**: header = título bold branco ~17–20pt à esquerda + "See All" em cor de acento à direita (IPTVX `iptvx/03.jpg`). IPTVX e IPTV Core (`iptv-core-m3u-xtream-player/03.jpg`) replicam o **rank numérico gigante** (1 2 3) atrás dos pôsteres em "Trending/Top Picks" — plágio declarado do Top 10 Netflix, já validado 2×.
4. **Continue watching**: cards **16:9** (nunca pôster) com play circular central + barra de progresso fina na base (IPTVX `iptvx/01.jpg`, UHF `uhf/02.jpg`, WatchUp `watchup-iptv-player/01.jpg` "Continue Assistindo"). Largura ~45–50% da tela.
5. **Live na home**: UHF (`uhf/02.jpg`) organiza canais por **pills de país com bandeira** ("Live channels" + Canadá/Alemanha/Espanha) — o agrupador é nação, não "categorias M3U". IPTV Core (`iptv-core-m3u-xtream-player/01.jpg`) usa o padrão rival: **3 cards-destino empilhados full-width** ("Live TV" azul, "TV Series" laranja, "Movies" vermelho, ~76pt, ícone + subtítulo + chevron) + strip de status da conta (Active/Expiry/Playlist) — convenção Smarters modernizada.
6. **Badges sobre pôster**: XCIPTV (`xciptv/04.png`) quadrado verde "★ 8.3" no canto; IPTVX badge vermelho "NEW EPISODES"; IPTV Core usa os dois (rating + "Recently Added").
7. **Densidade**: ~2,5–3 pôsteres visíveis por row (pôster 110–125pt, 2:3, radius 8–12pt, gap 8–12pt). Fundo #000–#0B0B0E; **cards sem sombra** — separação por gap e pelo próprio pôster. iMPlayer (`implayer/04.jpg`) vai ao extremo: grid 3 colunas em fundo preto puro, zero cromia fora do pôster.
8. **Header de seção com emoji** (XCIPTV "😎 Free to Watch", `xciptv/02.png`) — único do conjunto; não copiar (PRD §3.1.7).

### 1.2 EPG / guia

Três paradigmas coexistem nas referências:

**A. Tabela de grade clássica (TiviMate, `tivimate-android/01-epg-reddit.jpg`, foto em TV real):**
- Coluna fixa à esquerda: número + logo + nome do canal; **ícone de catch-up (relógio com seta) por canal**.
- Timeline horizontal com cabeçalhos de hora; blocos de programa = retângulos arredondados, selecionado em destaque claro; **linha vertical de "agora" com ponto** atravessando a grade.
- Painel superior: vídeo preview + título, faixa de horário + **"8 min" restantes**, SxxEyy + sinopse.
- Fundo azul-marinho escuro, blocos um tom acima, texto branco. ~8–9 linhas visíveis = densidade alta.
- É o que o usuário de IPTV espera num "guia de verdade" — mas é o que a UHF rejeitou.

**B. Cards coloridos por canal (UHF, `uhf/04.jpg`) — "EPG reinventado":**
- Lista vertical de canais; **cada canal é um card grande cuja cor vem da marca do canal** (C SPAN azul, 2F laranja, BBC ONE vermelho etc.), com logo à esquerda, programa atual e horário dentro.
- Header: filtro por país (pills com bandeira) + linha de data "Today · 09:00".
- Radius ~16pt, altura de card ~64–72pt. Legibilidade mantida com overlay escuro sobre a cor.
- Custa densidade (~4–5 canais por tela vs 8–9 do TiviMate) mas ganha identidade — é a "assinatura visual" que o RELATÓRIO recomenda para screenshot.

**C. Lista "agora/a seguir" por canal (IPTV Core, `iptv-core-m3u-xtream-player/02.jpg`):**
- Preview de vídeo no topo + nome do canal; card do programa atual com thumb, **pill vermelho "LIVE NOW 08:00–09:00"** + "% concluído" à direita, título bold, sinopse 1 linha.
- Seção "UP NEXT": hora (cor de acento) + título + sinopse 1 linha, por linha.
- Versão iPhone do EPG — bate com o que o PRD §4.2 já prevê ("lista Agora/A seguir no iPhone").

**D. Catch-up como sheet dedicado (IPTVX, `iptvx/06.jpg`):** sheet "TV ARCHIVE - CATCH-UP" com cabeçalho de data em vermelho ("Monday, 20 July"), agrupado por canal (nome bold), linha = hora vermelha + programa + ícone download/play. Catch-up é uma tela própria, não um modo da grade.

### 1.3 Detalhe VOD / série

**UHF (`uhf/03.jpg`) — melhor da categoria:**
- Backdrop full-bleed topo ~45% com fade para o fundo (sem corte duro).
- Título display bold centralizado (~32–34pt, 2 linhas).
- **Meta em pills**: "★ 7.8" (dourado) · "1968" · "2h 29m" — pills escuras ~28pt de altura.
- Gêneros em texto corrido; **Play full-width** (~50pt, quase branco, radius full).
- Linha de 4 ações-ícone (favorito/assistido/trailer/other sources) sobre labels ~11pt.
- Sinopse cinza ~15pt; **seção RATINGS em 4 colunas** (IMDb/Rotten/Audience/Trakt) com barras coloridas + % (80/90/88/79) — prova social como bloco de primeira classe; CAST com avatares em scroll horizontal.

**IPTVX série (`iptvx/04.jpg`):** backdrop ~40% com **play circular central** (ataque direto ao conteúdo); "★ 89% (186 reviews)" + badge "TV-MA"; "5 SEASONS · January 20, 2008" em caps pequenas; "Also on" + badge do serviço; **seasons como tabs horizontais**; episódios em lista vertical (thumb 16:9 ~35% da largura + título + data + download).

**XCIPTV (`xciptv/03.png`):** bloco "Play Next" com extras/trailers em lista (thumb + "Trailer · 2:24 · December 3, 2022") + barra de progresso vermelha de marca.

**Síntese:** backdrop hero → título → pills de meta → Play full-width → ações secundárias → sinopse → blocos de metadado rico. Nunca tabela técnica crua.

### 1.4 Player + controles

**UHF (`uhf/06.jpg`) — padrão a seguir:**
- Controles **não são overlay sobre o vídeo**: vídeo encolhe para o topo e um **card escuro arredondado (~20pt radius)** ocupa a base com: eyebrow do gênero em caps ~11pt, título bold ~22pt, sinopse 2–3 linhas, **chips de áudio/legenda** ("Audio English 5.1", "Subtitles").
- Transport em **uma linha na base do card**: prev / play grande / next + ações (heart, cast, AirPlay) à direita.
- **Scrubber fino** com tempos nas pontas, números tabulares.
- Live (mesmo shot, "Game of Thrones"): eyebrow "S01 E10 · Fire and Blood" + progresso "46:21" — identidade visual do player é a mesma em VOD e live.

### 1.5 Listas de categoria / grid

- **Grid com filtro**: XCIPTV (`xciptv/04.png`) — nav "‹ Free to Watch" + busca; linha de contexto "**4478 Results**" + pill de filtro "All Genres ▾"; grid 3 colunas, título abaixo do pôster (~13pt, 1 linha com ellipsis). Contador de resultados exposto = sensação de catálogo grande bem tratado.
- **Sidebar de categorias (paisagem/iPad)**: Smarters Lite (`smarters-lite/03.png`) — coluna esquerda ~35% com busca + lista de categorias **com contador por categoria** (ativa em laranja), conteúdo à direita. É o padrão de iPad que o mercado espera.
- **Lista de canais (iPhone)**: iMPlayer (`implayer/01.jpg`) — pills de grupo no topo ("Recently Watched" ativo em vermelho), row = logo quadrado + nome bold + programa atual + **barra de progresso do programa fina** embutida no row. Densidade ~7 rows, zero cromia fora do logo.
- **Dashboard de TV (legado)**: ibo-pro (`ibo-pro/02.png`) — tiles grandes Live/Movies/Series/Account sobre gradiente colorido; é a convenção que os Tier 1 abandonaram; útil só como referência do que NÃO fazer na home do Titan.

### 1.6 Busca

- **Entrada de busca sempre visível na home** — ou como pill no topo (XCIPTV `xciptv/02.png`: pill cinza-escura full-width com lupa) ou como tab dedicada (WatchUp `watchup-iptv-player/01.jpg`, último item da tab bar com ícone de lupa).
- Nas listas grandes, a busca é **scoped ao contexto**: "Search channels..." (xciptv-player/02.jpg), "Search in categories" (smarters-lite/03.png) — busca local dentro do conjunto aberto, não global.
- Nas refs não há screenshot de resultados de busca; o padrão do mercado (IPTVX/Netflix-like) = resultados agrupados por tipo (Filmes/Séries/Canais) em rows horizontais.

### 1.7 Login / onboarding / configuração

- **Splash**: xciptv-player (`recentes/xciptv-player/01.jpg`) — fundo navy escuro, ícone centrado, nome + tagline ("Stream Player & Link Manager" — zero palavra IPTV, tática de compliance do RELATÓRIO §2). ibo-pro (`ibo-pro/01.png`) usa foto borrada colorida — datado.
- **Form de credenciais**: Smarters Lite (`smarters-lite/01.png`) é A convenção que todo usuário de IPTV conhece: "Any Name / Username / Password / http://url..." + "ADD USER" + "LIST USERS" — mas executada em gradiente roxo datado. A estrutura (4 campos + botão + lista de usuários salvos) permanece; o visual é o que o Titan substitui.
- **Escolha de fonte**: Aerial TV (`recentes/aerial-tv-reprodutor-iptv/02.jpg`) — "Connect New Source" com lista de cards escuros (Plex/Jellyfin/Emby/M3U/Xtream), logo colorido + título + descrição 2 linhas + chevron, e nota "All providers are added at the same level". É a versão elegante do jargão: técnico mas organizado.
- **QR pairing**: Aerial (`recentes/aerial-tv-reprodutor-iptv/03.jpg`) — "Scan QR Code" central + botão primário full-width; resolve "digitar credenciais no telefone/TV".
- **Onboarding**: TiviMate (`tivimate-android/04-welcome.jpg`) — fundo navy, ilustração orbital minimalista, headline bold, body cinza, page dots, "Next →" pill full-width, **"Skip" no topo direito**. 3 telas, zero marketing.
- **Estado vazio como tela de boas-vindas**: xciptv-player (`recentes/xciptv-player/02.jpg`) — "No channels yet / Add a stream URL to get started" + ilustração circular + botão "+ Add Channel" + contadores "0 channels / 0 favorites" no topo. Dual-purpose: tutor + prova de compliance (RELATÓRIO §2).
- **Status da conta pós-login**: IPTV Core (`iptv-core-m3u-xtream-player/01.jpg`) — strip com 3 chips: "STATUS Active" (verde), "EXPIRY Dec 31 2030", "PLAYLIST Demo Playlist" — bate com o Welcome/Status (tela 4 do inventário 17).

### 1.8 iPad vs iPhone

- **iPhone**: stack vertical single-column; hero full-bleed ou card; EPG como lista "agora/a seguir"; grid 3 colunas de pôsteres.
- **iPad/paisagem**: IPTVX (`iptvx/02.jpg`) mostra a biblioteca em **grade de pôsteres 5–6 colunas** com rank numérico e detail com painel lateral; Smarters Lite (`smarters-lite/03.png`) mostra o padrão **split: sidebar de categorias (~35%) + grid à direita**; TiviMate (TV) mostra a grade EPG completa que no iPad vira a "grade horizontal clássica" já prevista no PRD §4.2. Regra emergente: elementos de navegação lateralizam (tabs → sidebar), rows horizontais viram grids, hero reduz de 60% para painel superior ou some em favor do grid.

---

## Bloco 2 — PROPOSTA DE ADOÇÃO NO DESIGN SYSTEM (vs docs/16 atual)

### 2.1 Tokens — adicionar/ajustar

O 16 atual cobre superfícies/conteúdo/marca. O que as referências expõem e falta:

| Proposta | Valor/regra | Evidência | Nota |
|---|---|---|---|
| `accent.live` | alias de `brand.crimson` #C1121F; uso: pill "LIVE NOW", linha vertical do "agora", progresso de programa | `iptv-core/02.jpg`, `tivimate/01` (linha do agora) | Token funcional; formaliza o "badge AO VIVO" já citado no 16 |
| `surface.channelTint` | **regra, não hex**: cor dominante extraída do logo do canal + overlay escuro ~45%, texto branco AA | `uhf/04.jpg` (cards EPG coloridos) | Exige dominant-color no cache de logos |
| `radius.poster = 8` · `radius.card = 12` · `radius.sheet = 16–20` | O 16 não define raios; PRD fixa 12pt só para cards | pôsteres `iptvx/03.jpg`; card do player `uhf/06.jpg` | Completar o 16 |
| `gradient.hero = black→transparent` na metade inferior | O 16 manda `crimsonDeep→transparent`; TODAS as refs usam preto→transparente para não tingir o pôster | `iptvx/01.jpg`, `xciptv/02.png` | crimsonDeep fica para splash/fundos de marca |
| Escala tipográfica | hero/detail title 32–34 display bold; section header 17–20 semibold; body 15; grid label 13; meta/caps 11 (tracking largo) | `uhf/03.jpg`, `iptvx/03.jpg`, `xciptv/04.png` | O 16 não tem escala; números tabulares p/ horários já previsto |
| `content.onTint` | branco #FFFFFF para texto sobre channelTint/arte | `uhf/04.jpg` | Contraste garantido sobre cor variável |
| Rating | **manter** `brand.gold` no pill "★ 7.8" — mercado usa verde (`xciptv/04.png`), mas verde já é `semantic.success`; não competir | `uhf/03.jpg` | Decisão consciente contra a convenção |

### 2.2 Componentes novos (com estados)

1. **HeroBanner** (carrossel): backdrop + gradiente + título/meta + 1 primária + 1 secundária + page dots. Estados: loading (skeleton), vazio (esconde), erro (esconde). Auto-advance ~6s, pausa na interação.
2. **ContinueWatchingCard** 16:9: thumb + play circular + progresso fino. Estados: normal, pressionado (scale 0.97), sem progresso.
3. **PosterCard**: 2:3, radius 8, label 13pt opcional, slot de badge (`RatingBadge` ★ dourado, `NewBadge` crimson). Estados: skeleton shimmer (PRD §3.1.5), placeholder de arte falha (inicial do título sobre `surface.raised`), pressionado.
4. **SectionHeader**: título + "See All"; variante com rank numérico gigante (`iptvx/03.jpg`).
5. **ChannelRow** (`implayer/01.jpg`): logo + nome + programa atual + barra de progresso fina; estado favorito.
6. **EPGCard** (UHF) com `channelTint` + **EPGNowIndicator** (linha + dot) + **EPGTimeHeader** (TiviMate) para a grade do iPad.
7. **NowNextCard / UpNextRow** (`iptv-core/02.jpg`): versão iPhone do EPG.
8. **SeasonTabs + EpisodeRow** (`iptvx/04.jpg`): tabs + linha thumb/título/data/ícone.
9. **PlayerInfoCard** (`uhf/06.jpg`): eyebrow + título + sinopse + **AudioChip** (pills de áudio/legenda) + transport + scrubber. Estados: visível, fade 3,5s (PRD §3.3), buffering, erro.
10. **AccountStatusStrip** (`iptv-core/01.jpg`): chips Active/Expiry/Playlist; success/warning (expirando)/error (expirada → toast, PRD §4.1).
11. **SourceCard** (`aerial-tv/02.jpg`): logo + título + descrição 2 linhas + chevron — onboarding/importação.
12. **EmptyStateCta** (`recentes/xciptv-player/02.jpg`): ilustração + título + instrução + CTA; refina o EmptyStateView já exigido no 16.
13. **CategorySidebar** (iPad, `smarters-lite/03.png`): lista + contador + busca local.
14. **FilterPill + ResultsCount** (`xciptv/04.png`): "4478 Results" + "All Genres ▾".

### 2.3 Regras iPad

- Regular width: CategorySidebar (~320–360pt) + conteúdo; rows horizontais viram grid 5–6 colunas (`iptvx/02.jpg`); EPG vira grade com gutter de tempo (TiviMate); hero reduz para ~35% ou vira banner no topo do grid; PlayerInfoCard ao lado do vídeo, não abaixo.
- Multitarefa (Split View): breakpoints por size class, não por device.

---

## Bloco 3 — IMPLICAÇÕES NO INVENTÁRIO (docs/17)

Telas/estados que as referências mostram e o 17 não cobre:

1. **Tela 11 "Detail simples" é subdimensionada** — nas refs o detalhe é a tela mais rica: ratings multi-fonte (`uhf/03.jpg`), extras "Play Next" (`xciptv/03.png`), seasons/episódios (`iptvx/04.jpg`). Spec precisa de variantes Detail VOD vs Detail Série (PRD §4.3–4.4 já diferencia; o 17 não).
2. **Empty state do catálogo com CTA de importação** (`recentes/xciptv-player/02.jpg`): o 17 tem Catalog Grid (8) sem empty state documentado; para o revisor da App Store esse estado É a tela (RELATÓRIO §2).
3. **Sheet de catch-up por data** (`iptvx/06.jpg`): §9 cita "entrada ao catch-up" mas não existe tela para o arquivo. Nova tela/sheet filha da 9.
4. **Menu de contexto do canal** (`iptvx/05.jpg`: favoritar, esconder, recategorizar via long-press): ausente no 17; mínimo = favoritar/esconder.
5. **"Conectar fonte" como tela própria** (`aerial-tv/02.jpg`): o 17 tem Login (3) único; refs tratam conexão como tela reutilizável — base para multi-playlist (PRD pergunta #2).
6. **QR pairing** (`aerial-tv/03.jpg`): não coberto; candidato pós-MVP.
7. **PiP/AirPlay como estados do Player** (`watchup/03.jpg`): §12 cobre loading/buffering/error, não PiP/route-picker.
8. **Filtro + contador na lista de categoria** (`xciptv/04.png`): telas 7/8 não especificam filtro de gênero nem contagem.
9. **Busca com resultados agrupados por tipo**: §10 não especifica composição dos resultados.
10. **Status da conta embutido na Home** (`iptv-core/01.jpg`): decidir entre tela 4 dedicada vs strip persistente + banner toast (PRD §4.1 sugere banner).

---

## Bloco 4 — ANTI-PADRÕES (com evidência)

1. **Dashboard de ícones sem conteúdo** — `purple/01.png`: 6 tiles "Watch Live TV / EPG Guide / Reminder / VOD / Series / Catch Up" sobre fundo roxo, zero pôster, zero conteúdo. É o oposto exato do princípio "o conteúdo é a estrela" (PRD §3): a home vira menu de rótulos.
2. **Cor de marca em grande área + acento gritante** — `purple/01.png` (laranja sobre roxo, tab bar com pill laranja) e `smarters-lite/01.png` (gradiente roxo/magenta atrás de campos brancos chapados). Confirma a regra do 16: acento raro, nunca superfície inteira.
3. **Fundo de foto borrada colorida** — `ibo-pro/01.png` e `ibo-pro/02.png`: splash e dashboard sobre foto sunset; data o app e briga com qualquer pôster. Fundo deve ser neutro escuro; cor vem do conteúdo.
4. **Verbos de sistema expostos** — `ibo-pro/02.png`: botões "Reload" e "Exit" na tela principal. Nada disso existe em UHF/IPTVX.
5. **Emoji como sistema de ícones** — `xciptv/02.png` ("😎 Free to Watch"); quebra com SF Symbols e com o tom premium (PRD §3.1.7).
6. **Texto ilegível sobre vídeo em estado compacto** — `watchup/03.jpg`: badge "AD VIVO" no PiP ilegível. Todo texto sobre vídeo exige scrim ou chip opaco.
7. **Preto puro sem camadas** — `implayer/04.jpg`: funciona no OLED mas não dá hierarquia; o 16 já resolve com `surface.raised` #141419.
8. **Conteúdo "perfeito" na captura** — IPTV Core lança com typo no hero: "Sprite Tnight" (`iptv-core/03.jpg`). Testar sempre com strings longas/reais (nomes de 40 chars, títulos com typo).
9. **Anti-padrões de lançamento** (RELATÓRIO §2/§6): logo de canal real (HBO) em screenshot (Lit) e futebol na capa (TV ao Vivo) = risco legal/rejeição; estado vazio como único shot (XCIPTV) = compliance máximo mas conversão fraca; molduras de device pesadas nos apps fracos vs frame mínimo nos bons.

---

## Bloco 5 — POSTURA DE LANÇAMENTO (extraído do RELATÓRIO; alimenta 18/06 depois)

1. **Shot 1 sempre o app preenchido e bonito** — hero + Continue Watching com playlist demo neutra; nunca onboarding (padrão transversal, RELATÓRIO §6).
2. **Shot 2 = importação de playlist** ("Adicione sua lista em 30s") — conta a história de compliance pro revisor e ainda é tutor (VisionX provou).
3. **EPG com cards coloridos (padrão UHF `uhf/04.jpg`) como assinatura visual** — é o shot 4 do blueprint do RELATÓRIO §7; ninguém mais no conjunto tem isso tão distinto.
4. **Compliance visível sem feio**: splash/tagline sem a palavra IPTV (`recentes/xciptv-player/01.jpg`), modo demo sem credenciais (IPTV Core), zero marcas de terceiros e zero futebol nos pôsteres do demo.
5. **Shot "de prestígio"**: AirPlay/PiP com paisagem neutra (WatchUp e Aerial repetem o padrão).
6. **Nome com keyword, UI sem jargão** (XCIPTV provou nos dois sentidos): título da loja carrega IPTV/M3U/Xtream; dentro do app, zero "playlist/Xtream/EPG URL" na home.
7. **Texto de loja**: L1 com dor, L2 disclaimer em caps (Lit/VisionX), 8–12 bullets, fecho com convite ao demo — esqueleto já validado (RELATÓRIO §4/§7).
8. **Regra visual dos shots**: moldura mínima, cores da marca, texto grande legível na busca da loja (RELATÓRIO §7).

---

## Aplicação na doc (2026-08-30)

Extração aprovada pelo dispatcher e aplicada na doc canônica. Nada novo criado em `docs/`; `TitanPlay/`, `referencias/` intocados.

### O que entrou em cada arquivo

**`docs/16-design-system-spec.md`** (mantido como FONTE ÚNICA de design):
- Seção **Raios**: `radius.poster` 8 · `radius.card` 12 · `radius.hero` 16 · `radius.sheet` 20 (pt).
- Seção **Tipografia**: escala `tipo/hero` (Display Bold 32/36) → `tipo/titulo` (22/26) → `tipo/secao` (20/24, já do PRD) → `tipo/linha` (17/22) → `tipo/corpo` (15/20) → `tipo/rotulo` (13/16) → `tipo/meta` (11/13 caps tracking +0.6).
- Tokens novos: `accent.live` (alias `#C1121F`), `surface.channelTint` (regra), `content.onTint` (`#FFFFFF`).
- Gradientes: hero = `surface.base` → transparente nos ~50% inferiores; `crimsonDeep→transparent` restrito a splash/fundo de marca.
- Tabela **"Componentes de catálogo e player"**: 16 componentes (HeroBanner, ContinueWatchingCard, PosterCard, SectionHeader, ChannelRow, EPGCard, EPGNowIndicator/EPGTimeHeader, NowNextCard/UpNextRow, SeasonTabs+EpisodeRow, PlayerInfoCard, AudioChip, AccountStatusStrip, SourceCard, EmptyStateCta, CategorySidebar, FilterPill+ResultsCount), cada um com estados.

**`docs/17-screen-inventory.md`** (numeração 1–19 estável, sub-entradas a/b + nota final):
- 3a Connect Source · 9a Sheet de Catch-up · 9b Menu de contexto de canal.
- 11 renomeado "Detail VOD / Detail Série" com variantes.
- 8: filtro + contador + empty state obrigatório com CTA de importação. 10: busca agrupada por tipo + escopo local. 12: PiP/AirPlay como estados. 7: sidebar no iPad. 4: nota do strip persistente.

**`docs/18-app-store-screenshot-plan.md`** (edição trivial): 1 bullet na "Evidência de mercado" — EPG colorido como shot-assinatura (posição 3–5). O resto do bloco 5 já estava coberto pela seção existente do 18; nada forçado.

**`docs/doc.md`**: 2 linhas do mapa ajustadas — 16 = "Tokens e componentes de design com valores (fonte única)"; 17 = "19 telas mínimas do app + sub-telas e estados mapeados".

### Hexes/valores escolhidos (decisões locais registradas)

| Decisão | Valor | Racional |
|---|---|---|
| `accent.live` | `#C1121F` (alias de `brand.crimson`) | Função própria sem hue novo; acompanha a marca se mudar |
| `content.onTint` | `#FFFFFF` | Texto sobre channelTint/arte; contrasta com `content.primary` #F5F5F7 em fundo de superfície |
| `surface.channelTint` | regra: cor dominante do logo + scrim `#000000` @45%; texto `content.onTint`; scrim sobe se contraste < 4.5:1 | Cor variável por canal; nunca um hex fixo |
| `gradient.hero` | `#0B0B0E` opaco → `rgba(11,11,14,0)`, ~50% inferiores do backdrop | Grafite da própria base funde com o fundo da tela; evita `#000` puro (PRD §3.1.1) |
| Raios | 8 / 12 / 16 / 20 | 12 mantém o compromisso do PRD §3.3; 20 = PlayerInfoCard (`uhf/06.jpg`) |
| Rating | mantém `brand.gold` | Contra a convenção verde do mercado (`xciptv/04.png`); verde reservado a `semantic.success` |

### Pendências

- Nenhuma bloqueante. Observações registradas: `surface.channelTint` exige extração de cor dominante no cache de logos (impacto técnico futuro em AppCore); download no catch-up (ícone do IPTVX) deixado como decisão futura na 9a; QR pairing (Aerial) segue fora do escopo — pós-MVP.
