# Prompt para o Figma Make — Titan Play

Cole o texto abaixo no Figma Make depois de importar as telas e os assets do kit.

```text
Crie um app iOS mobile vertical chamado Titan Play: um streaming premium em português do Brasil para filmes, séries e canais ao vivo. Trabalhe a partir dos arquivos deste kit.

PRIORIDADE DOS MATERIAIS
1. Use `01-telas-mobile/00-*-conceito.png` como a direção visual principal.
2. Use as telas numeradas de `01-telas-mobile/` para cobrir os fluxos e estados funcionais.
3. Use somente os arquivos de `02-assets/` como assets no produto final:
   - `marca/01-logo-completo.png` no splash/onboarding;
   - `marca/03-wordmark-claro.png` ou `marca/04-wordmark-escuro.png` no header, conforme o contraste;
   - `marca/05-avatar-titan.png` no perfil;
   - `filmes/` e `series/` como capas de demonstração;
   - `canais/` como logos fictícios para Ao vivo e EPG.
4. `03-referencias-mercado/` é pesquisa visual. Não copie telas, logos, textos, nomes, ícones ou assets de UHF, IPTVX, XCIPTV, TiviMate ou outros concorrentes. Extraia apenas princípios: conteúdo em primeiro lugar, hero cinematográfico, catálogo rico, EPG legível e onboarding simples.

BASE VISUAL
- Frame: iPhone, 402 × 874 pt; respeite safe areas e use componentes com Auto Layout.
- Tema: dark-first, premium e cinematográfico, sem aparência de painel técnico de IPTV.
- Fundo `#090A0C`; surface `#16171C`; surface elevada `#202126`.
- Ação, seleção, CTA e aba ativa `#D81022`; dourado para nota, favorito e selo `#D6A540`.
- Texto principal `#F4F2EE`; secundário `#A4A3AD`; sucesso `#32C759`; destrutivo `#FF453A`.
- Fonte: SF Pro; fallback Inter. Espaçamento em múltiplos de 8 pt. Área de toque mínima 44 × 44 pt.
- Raios: poster 8 pt, card 16 pt, botão 18 pt. Sem sombras grandes; separe superfícies por contraste sutil, borda e espaçamento.
- Use gradiente escuro da metade inferior do hero até o fundo. A arte deve continuar sendo a protagonista.

TELAS A CONSTRUIR
1. Abertura/splash com logo oficial Titan.
2. Onboarding: nome e preferências de gênero.
3. Home: header compacto, hero/carrossel, CTAs “Assistir” e “Minha lista”, Continue assistindo (cards 16:9 com progresso), coleções e recomendações.
4. Filmes e Séries: busca local, filtro de gênero, contador de resultados e grid de posters 2:3.
5. Detalhe de filme: backdrop, título, ano · gênero · duração · classificação, nota dourada, CTA de assistir, lista e sinopse.
6. Detalhe de série: mesma estrutura, seletor de temporada e episódios com thumb 16:9.
7. Ao vivo: hub de canais com logo, programa atual e barra de progresso; destaque de canal em reprodução com badge “AO VIVO”.
8. Guia EPG: lista Agora/A seguir no celular, nunca uma área preta vazia. Crie loading, sem programação, erro com “Tentar novamente” e conteúdo. Para conteúdo, apresente canal, programa atual, horário, progresso e próxima atração.
9. Busca: estados idle, digitando/carregando, resultado agrupado por Filmes/Séries/Canais, vazio e erro.
10. Player: vídeo, título, scrubber, áudio/legenda, favoritos e AirPlay/PiP como ações secundárias.
11. Minha lista vazia e preenchida; Recentes com datas em pt-BR e progresso; Ajustes; Suporte.

NAVEGAÇÃO E ESTADOS
- Tab bar apenas nas rotas raiz: Início, Ao vivo, Filmes, Séries e Buscar. Ícone, label e indicador da aba ativa em vermelho Titan.
- Nas rotas profundas (detalhe, episódios, player, EPG, favoritos, recentes, ajustes e suporte), esconda a tab bar e use botão voltar circular de 44 × 44 pt.
- Todo carregamento deve mostrar skeleton e texto de estado. Todo erro precisa de ação de recuperação. Busca não pode exibir vazio enquanto a consulta ainda carrega.
- Interface em pt-BR: “Hoje, 23:58”, “Minha lista”, “Continuar assistindo”, “Tentar novamente”. Não exibir termos como playlist, M3U, Xtream, URL de EPG ou credenciais na Home.

ENTREGA NO FIGMA
- Crie uma página “Fluxo principal” com as telas em ordem de navegação e uma página “Componentes” com tokens, botões, PosterCard, ChannelRow, HeroBanner, EPGCard, estados vazios e skeletons.
- Conecte protótipos de home → detalhe → player; abas raiz; filme/série → detalhes; ao vivo → guia; busca → resultados.
- Use títulos e canais fictícios fornecidos no kit. Não introduza logos de canais reais, atletas, clubes, filmes/franquias ou atores reconhecíveis.
```
