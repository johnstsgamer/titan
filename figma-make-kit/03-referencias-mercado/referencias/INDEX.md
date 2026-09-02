# Referências de design — apps IPTV que NÃO parecem IPTV

Coletado em 2026-08-30 via API oficial da App Store (screenshots oficiais em alta resolução) + busca web para TiviMate.
Metadados completos em `_meta.json`. Cada pasta contém até 6 screenshots do iPhone + `icon.jpg`.

> **Ver também:** [RELATORIO-LANCAMENTOS-RECENTES.md](RELATORIO-LANCAMENTOS-RECENTES.md) — apps IPTV lançados nos últimos 10 meses, como se apresentaram para aprovação e os 5 candidatos escolhidos (screenshots em `recentes/`).
> **Análise derivada:** [extracao-design-referencias.md](extracao-design-referencias.md) — padrões visuais extraídos deste material para o design system (insumo de `docs/16` e `docs/17`; decisões em DEC-008).

---

## Tier 1 — streaming premium disfarçado (o que você pediu)

### 1. UHF — "Love your IPTV" → `uhf/`
**4,65★ · 2.188 avaliações (BR)** · Short Wavelength · [App Store](https://apps.apple.com/br/app/uhf-love-your-iptv/id6443751726)
A melhor referência do conjunto. Marketing oficial: *"your favorite content in a premium Apple interface"*.
- EPG reinventado: cards coloridos por programa, não a tabela cinza clássica (`04.jpg`)
- Página de título estilo Apple TV: hero poster, ratings Trakt/TMDB com pills coloridos (`03.jpg`)
- Continue watching, bandeiras de país para canais ao vivo, dark puro

### 2. IPTVX → `iptvx/`
**4,42★ · 3.008 (US)** · Bending X · [App Store](https://apps.apple.com/us/app/iptvx/id1451470024)
Clone visual de Netflix + Apple TV. Biblioteca VOD "beautifully organized" com rows horizontais, hero banners e iCloud Sync entre iPhone/iPad/Mac/Apple TV.

### 3. XCIPTV → `xciptv/`
**4,54★ · 4.606** · Aicha Ounaissar · [App Store](https://apps.apple.com/br/app/xciptv/id6471280288)
Hero banner em tela cheia estilo Disney+, gradiente azul, badges de nota (8.3/7.2) sobre os pôsteres, rows "Free to Watch".

## Tier 2 — bonitos, mas ainda com cara de player

| App | Pasta | Nota | Por que olhar |
|---|---|---|---|
| Smarters Player Lite | `smarters-lite/` | 4,85★ · 259.922 | O mais usado do mundo; convenção de UI que os usuários já conhecem |
| ibo Pro Player | `ibo-pro/` | 4,84★ · 9.446 | Padrão do mercado BR; dashboard de TV clássico (Live/Movies/Series) |
| VU IPTV Player | `vu-player/` | 4,83★ · 17.456 | Tiles com gradiente vibrante, dashboard moderno |
| iMPlayer | `implayer/` | 4,80★ · 2.100 | Dark minimalista, listas de grupo limpas, VOD dedicado |

## Tier 3 — evita (datados/genéricos)

`purple/` (4,33★), `mega-iptv/` (4,45★), `flix-pro/` (4,76★ mas visual roxo genérico estilo template) — mantidos só como contraste do que NÃO fazer.

## Benchmark Android/TV

- **TiviMate** → `tivimate-android/` — o IPTV mais elogiado em UX de TV. EPG dark clássico (`01-epg-reddit.jpg`, foto real em TV) e onboarding limpo (`04-welcome.jpg`).

---

## Padrões extraídos (o que faz "não parecer IPTV")

1. **Dark-first** com superfícies em camadas, nunca fundo cinza-claro de guia de TV
2. **Pôsteres TMDB grandes** no lugar de nomes de arquivo/arquivos .m3u expostos
3. **Hero banner** em tela cheia no VOD (Netflix/Disney+)
4. **Rows horizontais** ("Trending", "Continue watching") em vez de grid de canais
5. **EPG redesenhado** — cards coloridos por programa (UHF) em vez da tabela
6. **Metadados ricos integrados** — notas, gêneros, elenco via Trakt/TMDB
7. **Zero jargão IPTV** na UI — nada de "playlist", "Xtream codes", "EPG URL" na home
8. **Onboarding curto** e escuro (TiviMate), configuração técnica escondida depois
