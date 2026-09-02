# Relatório — Apps IPTV lançados nos últimos 10 meses: apresentação, ASO e aprovação

**Janela:** 2025-10-30 → 2026-08-30 · **Coleta:** 2026-08-30 via API oficial da App Store + páginas web da loja
**Dados:** 352 apps varridos → ~100 lançados na janela → 16 com tração em `recentes/` (screenshots, descrição completa, metadados em `recentes/_meta-recentes.json`, títulos/subtítulos em `recentes/_titulos-subtitulos.json`)

---

## 1. Realidade da janela

Dos ~100 lançamentos IPTV: só **3 passaram de 40 avaliações** (XCIPTV 114, VisionX 49, IPTV Core 19); ~70 morreram com zero. Passar na revisão é fácil; sair do zero é o jogo. Os 3 que cresceram = nome com keyword + screenshots de produto pronto + nota inicial alta + updates mensais.

## 2. Como passaram na revisão (compliance)

| Padrão | Freq. | Exemplo real |
|---|---|---|
| Disclaimer de conteúdo | 14/16 | "Este aplicativo não fornece nenhum conteúdo ou canais IPTV" |
| Xtream/M3U/EPG (posição: player de APIs) | 15/16 | "player for your own M3U playlists, Xtream profiles" |
| Bring-your-own playlist | 8/16 | "Add your own source" / "use without credentials" |
| Modo demo sem credenciais | 6/16 | IPTV Core: "Demo Playlist · Active" |
| "Not affiliated" / independente | 3/16 | "sem afiliação com provedores de conteúdo" |

**Fórmula-padrão do disclaimer** (variações dos 14): *"Este app é APENAS um player de mídia. NÃO fornece, hospeda, vende ou distribui canais, filmes, séries ou qualquer conteúdo."* Lit IPTV coloca em CAIXA ALTA já na 2ª linha; Vuleo abre a 2ª frase com ele.

**Visual:** XCIPTV usou **estado vazio como screenshot** ("No channels yet — Add a stream URL") — prova direta ao revisor de que não entrega conteúdo. VisionX mostrou o form de importação com "Add Playlist". Nuvox pôs o disclaimer dentro do próprio screenshot. Contra-exemplos arriscados: Lit exibe logo HBO num canal; "TV ao Vivo" pôs futebol na capa.

## 3. Títulos e subtítulos (o que está na loja)

Apple permite 30 chars em cada. Padrão do mercado: **título = Marca + IPTV + Player + keyword extra**; **subtítulo = slot de keywords** (funcionalidade, não slogan).

| App | Título (chars) | Subtítulo (chars) |
|---|---|---|
| IPTV Core | IPTV Core: M3U Xtream Player (28) | Smarters, TV ao Vivo e Futebol (30) |
| Smarter Stream | Smarter IPTV Stream (19) | Reprodutor IPTV inteligente (27) |
| TV ao Vivo | IPTV Player – TV ao Vivo (24) | Assistir TV online, listas M3U (30) |
| Lit | Lit IPTV Player - Smart IPTV (28) | Create Playlists,Replay TV,EPG (30) |
| Aerial TV | Aerial TV: Reprodutor IPTV (26) | Sincronize e assista (20) |
| WatchUp! | WatchUp! IPTV Player (20) | Simples, rápido e elegante. (27) |
| Orbizy | Orbizy IPTV Player (18) | M3U & Xtream Codes (18) |
| Flux | IPTV Player - Xtream M3U: Flux (30) | Assista IPTV - VOD, Séries (26) |
| Nuvox | Nuvox IPTV (9) | Nuvox PRO IPTV Stream Player (27) |
| Vuleo | Vuleo - Reprodutor de Mídia (26) | Seus canais, filmes e séries (28) |
| XCIPTV | XCIPTV Player (13) | — sem subtítulo |
| VisionX | IPTV VisionX (11) | — sem subtítulo |
| Spark | Spark Media Player (18) | — sem subtítulo |

Leituras: quem já tem marca (XCIPTV, VisionX, Spark) dispensa keyword no subtítulo. Quem nasceu agora empilha keywords: "Smarters" é roubada do concorrente maior (IPTV Core usa no subtítulo!), "Futebol" é isca de busca BR, "Replay/EPG/Catch-up" (Lit) captura quem busca funcionalidade.

## 4. Descrições — anatomia (texto real)

Estrutura comum aos 16 (0 emojis em todos; 1.100–4.000 chars; bullets de 3 a 35):

1. **Linha 1 = proposta de valor em 1 frase** — "Pare de sofrer com travamentos. IPTV Core é o player mais rápido..." (dor) · "Sua mídia. Cada dispositivo." (Aerial, visão) · "O WatchUp! é o reprodutor mais rápido, moderno e elegante" (superlativo)
2. **Disclaimer o mais cedo possível** — Lit: 2ª linha, caps. VisionX: "IMPORTANT: IPTV VisionX does NOT provide any channels, streams, or media content". Spark: 1º bullet.
3. **Blocos de features em bullets** (Smarter Stream usa 35; Aerial 27; Flux 24) — suporte a formatos, multi-tela, EPG, organização, privacidade
4. **Micro-história de configuração** — Orbizy: "Adicione suas credenciais Xtream ou links M3U e nós organizamos todo o catálogo magicamente"
5. **Fecho de privacidade/segurança** — "Seguro e Privado: Não fornecemos nenhum conteúdo" (Orbizy)

Variação de tom: técnico-transparente (Aerial lista Plex/Jellyfin/Emby/Xtream logo na abertura) vs. lifestyle (Lit/WatchUp falam de "experiência", não de protocolos).

## 5. Palavras-chave (extraídas de títulos + subtítulos + descrições)

**Alta frequência na janela:** `IPTV` · `player` · `M3U`/`M3U8` · `Xtream` (Codes) · `TV ao vivo` · `lista/playlist` · `reprodutor`
**Médias:** `Smarters`/`smart` · `EPG` · `VOD` · `séries` · `filmes` · `canais` · `stream/streaming` · `assistir TV online` · `catch-up`/`replay` · `futebol` · `sincronizar` · `multi-tela/AirPlay`
**Só em descrição (não exibidas):** 4K, HDR, Dolby, Chromecast, privacidade, sem travamentos, rápido

Conclusão ASO: o pacote mínimo que TODOS os recém-chegados usam = `IPTV + Player + M3U + Xtream + TV ao vivo`. Diferenciação vem do subtítulo (funcionalidade única: replay, sync, futebol).

## 6. Imagens da loja — narrativa visual (sequência real dos candidatos)

| App | Shot 1 (capa) | Shot 2 | Shot 3 | Linguagem |
|---|---|---|---|---|
| **Lit** | Foto lifestyle (2 pessoas, amarelo) + app com VOD Netflix-like | "Catch Up On Live TV" com player e canal HBO | "Always Know What To Watch" com elenco/trailers | Cores de marca fora do padrão; conteúdo real com marcas (arriscado) |
| **Aerial** | "Configure Uma Vez" + tela de fontes (Plex/Jellyfin/Emby/M3U/Xtream) | "AirPlay — Continue em qualquer tela" paisagem neutra | — | Pitch multi-dispositivo estilo Apple; setup honesto |
| **XCIPTV** | Splash dark "Stream Player & Link Manager" (zero palavra IPTV) | **Estado vazio** "No channels yet — Add a stream URL" | — | Compliance máximo; conversão fraca |
| **VisionX** | "Watch Live TV Anywhere" + home com bloco Add Playlist | "Import M3U Playlists" com form e "My Playlist · 120 channels" | — | Vermelho/branco denso; importa como herói do fluxo |
| **WatchUp!** | "Filmes, séries e canais ao vivo" + home dark com hero e Continue Watching | "AirPlay — Continue em qualquer tela" | — | Streaming BR limpo; zero jargão em tela |

**Padrões transversais:** shot 1 sempre o app PREENCHIDO e bonito (nunca o onboarding); shot 2 quase sempre é a importação/conexão de playlist (função compliance); AirPlay/multi-tela é o shot "de prestígio" recorrente; frames de iPhone em mockup colorido nos apps fracos, device quase sem moldura nos bons; TODO disclaimer importante aparece na descrição, não na imagem (Nuvox é a exceção defensiva).

## 7. Blueprint — ideias para o app que vou lançar

### Título + subtítulo (3 opções)
1. **[Marca] IPTV Player** (seguro) · subtítulo: "M3U, Xtream, EPG e VOD" (22)
2. **[Marca]: TV ao Vivo e M3U** (BR-busca) · subtítulo: "Séries, filmes e replay" (23)
3. **[Marca] — Seu player de TV** (diferenciado, estilo Aerial/Vuleo) · subtítulo: "Sync entre iPhone, iPad e TV" (28)

### Descrição (esqueleto testado pelos aprovados)
- L1 proposta de valor com dor: "Sua lista inteira, organizada como Netflix — sem travamentos."
- L2 disclaimer caps: "IMPORTANTE: este app é APENAS um reprodutor. NÃO fornece, hospeda ou vende canais, filmes ou séries. Traga sua própria lista M3U ou Xtream."
- 8–12 bullets: player 4K/HDR, EPG bonito, catch-up/replay, multi-tela/AirPlay, organização automática com pôsteres, busca, favoritos, privacidade ("não coletamos suas credenciais")
- Fecho: convite a testar com playlist demo embutida

### Storyboard de screenshots (6 shots)
1. Home preenchida com playlist demo neutra (pôsteres genéricos, SEM logos de canais, SEM futebol) — hero + Continue Watching
2. "Adicione sua lista em 30s" — form de importação M3U/Xtream (compliance + tutor)
3. Detalhe de título com pôster, sinopse e Play (estilo UHF/IPTVX)
4. EPG redesenhado com cards coloridos (assinatura visual do app)
5. AirPlay/multi-tela com paisagem neutra (sem marcas)
6. Prova social/qualidade: "4K sem travamentos" com player ao vivo
Regra: moldura mínima, cores da marca, texto grande legível em busca.

### Pacote de keywords (~100 chars App Store Connect)
`iptv,player,m3u,m3u8,xtream,tv,ao,vivo,epg,listas,series,filmes,replay,smart,vod,4k`
(Nunca comprar nome de concorrente — "Smarters" é marca alheia e motiva rejection 5.2.2.)

### Decisões de compliance (o que os 5 candidatos provaram)
1. Disclaimer caps na 2ª linha da descrição (Lit/VisionX)
2. Shot 2 = importação de playlist (VisionX) — conta a história pro revisor
3. Modo demo sem credenciais (IPTV Core) — revisor testa sem conta
4. Zero marcas de terceiros em screenshots (o HBO da Lit é o contra-exemplo)
5. Nome com keyword, UI sem jargão (XCIPTV provou nos dois sentidos)
