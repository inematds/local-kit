# PLANO — Local Kit em Português ("O Laboratório Local")

> Plano para recriar, em PT-BR, o site **https://hermes-masterclass.vercel.app/local-kit/**
> ("The Local Lab · Bonus Kit — Hermes Masterclass").
> Captura completa do original em `referencia/original.html` + `referencia/raw-images/` (baixados em 2026-07-16).

---

## 1. O que é o site original (análise completa)

Uma **página única, 100% self-contained** (HTML + CSS + JS inline, ~57KB, sem framework,
sem build, sem backend) que ensina a rodar LLMs localmente com Ollama. É um "kit bônus"
do capítulo 3 de uma masterclass sobre o agente "Hermes".

**Stack real:** 1 arquivo HTML · Google Fonts (Inter, JetBrains Mono, Newsreader itálica) ·
4 ilustrações JPG geradas por IA · ~11 logos SVG de modelos/ferramentas · vanilla JS (~130 linhas).

### 1.1 Design system

| Token | Valor | Uso |
|---|---|---|
| `--bg` | `#07080f` | fundo quase-preto azulado |
| `--card` / `--card-2` | `#12162a` / `#181d36` | cards |
| `--border` / `--border-2` | `#2c3560` / `#3d4878` | bordas |
| `--hermes` / `--hermes-2` | `#4b5cff` / `#8fa3ff` | azul-índigo da marca (acento principal) |
| `--amber` `--gold` `--green-2` `--red` `--p4` | `#f0b441` `#facc15` `#4ade80` `#ef4444` `#2dd4bf` | acentos semânticos |

- **Tipografia:** Inter (corpo/títulos 800–900, tracking negativo), JetBrains Mono
  (tags, comandos, números), Newsreader *itálica* (palavras de ênfase dentro dos títulos — assinatura visual).
- **Atmosfera:** barra gradiente de 3px fixa no topo; grain de ruído SVG (opacity .03,
  mix-blend overlay); 3 radial-gradients fixos de glow azul/teal; sombras profundas + glow;
  `fadeInUp` nas seções; cards com hover translateY.
- **Padrões repetidos:** `sec-tag` (pílula mono numerada "01 · ..." com dot pulsante),
  `h2` com `<em>` serifado colorido, `.lead`, `.callout` âmbar com ícone, `.sowhat`
  (caixa final "So what →"), `.links` (chips-pílula com logo), `.art` (ilustração com borda+glow).

### 1.2 Estrutura e conteúdo (seção a seção)

1. **Topbar** — link "← Masterclass · Home" + badge "Chapter 3 · Bonus Kit".
2. **Hero** — eyebrow verde "Powering Hermes · The Local Strategy"; H1 "The Local Lab.
   *Free. Private. Yours.*" (gradient text); subtítulo serifado; ilustração `lab-hero.jpg`.
3. **01 · The strategy — "Pick your mode first"** — ilustração `lab-modes.jpg` + 3 cards
   de modo: 🔒 **Vault** (100% local, dados sensíveis), 🔌 **Connected** (local no grosso,
   nuvem sob demanda — ★ estratégia diária), ☁️ **Cloud-first** (local só nos 5% privados).
4. **02 · Your machine — slider interativo de RAM/VRAM** ("What can *your* Mac actually run?").
   Slider de 8 stops (8/16/24/32/48/64/96/128 GB) → atualiza: número GB grande, tier com
   emoji+nome+contexto ("The Pocket Lab" 🧪, "The Workbench" ⚗️, "The Sweet Spot ★" ⚡,
   "The Forge" 🔥, "The Heavy Rig" 🚀, "Mission Control" 🛰️, "The Observatory" 🌌,
   "Mount Olympus" 🏛️), descrição, 3 chips de modelos recomendados (com comando `ollama pull`),
   e dois cards comparativos: ⏳ **time machine** ("tão potente quanto a fronteira de <data>")
   e 🎯 **closest modern relative** (equivalente atual: o3-mini, GPT-4o, o4-mini, Haiku…).
   Nota: modelo + KV-cache moram na memória; tamanhos Q4.
5. **03 · Best in class — "Three jobs. Three champions."** — 3 strips clicáveis (copiam o comando):
   **Qwen3-Coder 30B** (o coder, 24GB, ~40 tok/s), **DeepSeek-R1 14B** (o raciocinador, 16GB),
   **GPT-OSS 20B** (o generalista, 16GB).
6. **04 · The local landscape — gráfico interativo "Six houses. Every size."**
   6 linhas (Qwen3, DeepSeek-R1, GPT-OSS, Gemma 3, Llama, Mistral) com dots posicionados
   por tamanho de parâmetros; toggle **size ⇄ power** (dots animam para posição de
   capacidade); mini-slider de GB **sincronizado em duas vias** com o slider da seção 02;
   faixa verde = alcance da sua máquina; dots que não cabem ficam apagados (`dim`);
   clique no dot copia `ollama pull <tag>`; ★ = o coder. Eixos: 1B–120B (size) /
   "quick chat → real work → agent-grade → frontier-adjacent" (power).
   + Callout 🎭 "Same brains, different manners" (alinhamento: Gemma/GPT-OSS travados,
   Llama meio-termo, Mistral solto, Nous neutro) + links ollama.com / library / LM Studio.
7. **05 · The honest context — "How good is local, really?"** — ilustração `lab-spectrum.jpg`
   + 4 bandas: local·small (pocket brain), local·30B ★ ("a fronteira de ontem"),
   rented giants (GLM/DeepSeek/Kimi — abertos mas enormes, centavos pra alugar),
   frontier cloud (os 5% mais difíceis). + Callout ⚖️ "a vantagem do local não é QI:
   é custo zero por token, zero egress de dados, sem rate limit".
8. **06 · The two traps — "Why people think local is bad."** — 2 cards vermelhos:
   **(a)** default de 4.096 tokens do Ollama vs 256K nativos do Qwen3-Coder (barra
   comparativa 1,6%) → fix `OLLAMA_CONTEXT_LENGTH=65536 ollama serve`;
   **(b)** a parede do KV-cache (70B ≈ 42GB só de cache a 128K; consumer = 32–64K usável)
   → fix quantização de KV-cache `q8_0`.
9. **07 · Wire it up — "Three commands to a sealed room."** — janela de terminal com
   botão copy: `ollama pull` → `OLLAMA_CONTEXT_LENGTH=65536 ollama serve` →
   apontar o agente para `http://localhost:11434/v1`. + links download + ilustração
   `lab-closer.jpg` + caixa **So what →** ("hoje à noite: arraste o slider, puxe os
   recomendados, suba o contexto ANTES de julgar").
10. **Footer** mono discreto.

### 1.3 Interações JS (tudo vanilla, ~130 linhas)

- Array `GBS` (8 valores) + array `TIERS` (8 objetos: emoji, nome, ctx, desc, chips,
  time-machine, comparativo moderno) → função `rigUpdate()` renderiza tudo.
- `REACH[]` — largura da faixa verde por stop do slider.
- Mapa `PW{}` — posição de "poder" de cada modelo para o toggle size⇄power.
- `chartSync(gb)` — apaga dots acima do GB, move faixa, sincroniza mini-slider e legenda.
- Copy-to-clipboard em: dots do gráfico, comandos dos champions, botão do terminal
  (feedback "copied ✓" com timeout).

### 1.4 Assets capturados

- `referencia/original.html` — página completa.
- `referencia/raw-images/` — lab-hero.jpg, lab-modes.jpg, lab-spectrum.jpg, lab-closer.jpg
  (ilustrações do "laboratório") + logos: qwen, deepseek, openai-white, gemma, meta,
  mistral, glm, kimi, claude, gemini, ollama, lmstudio (SVG).
  (`icon.png` não existe no servidor — 404 no original também.)

---

## 2. O que vamos construir — "**Laboratório Local**" em PT-BR

Mesma página, mesma arquitetura (1 HTML self-contained, zero build), todo o texto em
português brasileiro, publicada via GitHub Pages neste próprio repo (`local-kit`).

### 2.1 Decisões de produto

- **Formato:** página única `index.html` na **raiz** do repo (é o app do projeto, não um "guia").
- **Idioma:** PT-BR completo — inclusive tooltips, aria-labels, comentários do terminal
  e microcopy ("copiado ✓"). Comandos de shell permanecem como são.
- **Identidade: padrão INEMA dark-âmbar** (decidido em 2026-07-16). Repintar os tokens:
  acento primário âmbar (`#f59e0b`/âmbar INEMA no lugar do azul `--hermes`), secundário
  sky/ciano (no lugar do verde), fundo dark premium INEMA. Manter a *arquitetura* visual
  do original (grain, glows, serif itálica nos títulos, pílulas mono) só que na paleta
  INEMA. Topbar/footer com logo + INEMA.CLUB (sem "Hermes Masterclass").
- **Adaptação de contexto:** o original assume Mac/Apple Silicon e o agente "Hermes".
  Versão PT-BR: falar de **Mac (memória unificada) E PC com GPU (VRAM)** em pé de
  igualdade, e no passo 3 do terminal apontar um cliente genérico compatível com
  OpenAI (ex.: `--base-url http://localhost:11434/v1`) em vez do CLI `hermes`.
- **Ilustrações: gerar 4 novas no flux2-klein** (decidido) — não reutilizar os JPG do
  original em produção (ficam só como referência). Tema visual: **futurista** (ver 2.2.1),
  não "laboratório de alquimia". Paleta das imagens: dark com âmbar/dourado dominante +
  toques ciano (casar com o site INEMA). Os 4 temas:
  1. `hero.jpg` — datacenter/estação pessoal do futuro, uma máquina soberana brilhando em âmbar;
  2. `modos.jpg` — tríptico cofre lacrado / ponte conectada / nuvem distante;
  3. `espectro.jpg` — escada de poder, de um chip na palma da mão até uma megaestrutura no horizonte;
  4. `final.jpg` — pessoa diante da própria máquina, "sua máquina, sua mente".
  Logos SVG dos modelos podem ser reutilizados (logomarcas públicas das empresas).

### 2.2 Mapa de tradução dos nomes

| Original | PT-BR proposto |
|---|---|
| The Local Lab · Free. Private. Yours. | O Laboratório Local · *Grátis. Privado. Seu.* |
| Pick your mode | Escolha seu modo |
| Vault / Connected / Cloud-first | Cofre / Conectado / Nuvem-primeiro |
| Your machine | Sua máquina |
| The Pocket Lab … Mount Olympus (escada de tiers) | **substituída por escada FUTURISTA própria — ver 2.2.1** (nada de mitologia/alquimia) |
| time machine / closest modern relative | máquina do tempo / parente moderno mais próximo |
| Three jobs. Three champions. | Três trabalhos. Três campeões. |
| the coder / the reasoner / the all-rounder | o programador / o raciocinador / o generalista |
| Six houses. Every size. | Seis casas. Todos os tamanhos. |
| quick chat / real work / agent-grade / frontier-adjacent | papo rápido / trabalho de verdade / nível agente / quase-fronteira |
| The honest context | O contexto honesto |
| The two traps | As duas armadilhas |
| Wire it up / a sealed room | Ligando os fios / uma sala lacrada |
| So what → | E daí → |

#### 2.2.1 Escada de tiers — tema FUTURISTA (substitui os nomes do original)

O original mistura laboratório de alquimia e mitologia ("The Forge", "Mount Olympus").
A versão INEMA usa uma progressão sci-fi coerente — quanto mais memória, mais longe no futuro/espaço:

| GB | Emoji | Nome PT-BR | Substitui |
|---|---|---|---|
| 8 | 🤖 | **A Cápsula** | The Pocket Lab |
| 16 | 🔧 | **A Doca** | The Workbench |
| 24 | ⚡ | **O Núcleo ★** (ponto ideal — o tier da lição) | The Sweet Spot ★ |
| 32 | 🔥 | **O Reator** | The Forge |
| 48 | 🚀 | **A Nave de Carga** | The Heavy Rig |
| 64 | 🛰️ | **Controle da Missão** | Mission Control |
| 96 | 🌌 | **A Estação Orbital** | The Observatory |
| 128 | 🪐 | **A Frota Estelar** | Mount Olympus |

Descrições de cada tier: traduzir o conteúdo técnico do original (modelos, contexto,
comparativos) trocando as metáforas para o vocabulário sci-fi correspondente.

### 2.3 Dados a preservar tal e qual (o coração da página)

- Os **8 tiers** com seus modelos, contextos e comparativos históricos (traduzir textos,
  manter fatos: GPT-OSS 20B ≈ o3-mini, tier 24GB ≈ GPT-4o, 48GB > GPT-4 original, etc.).
- As **6 famílias** com todos os dots/tags/posições e o mapa `PW`.
- Os **3 campeões** e seus comandos `ollama pull`.
- As **2 armadilhas** com números (4K vs 256K = 1,6%; 70B ≈ 42GB de cache a 128K) e fixes.
- Os **3 comandos** finais.
- *Revisão opcional na Fase 1: checar se em jul/2026 vale atualizar alguma recomendação
  (ex.: novas versões de Qwen/Llama), mantendo a estrutura.*

---

## 3. Fases de execução

### Fase 1 — Conteúdo (½ dia)
1. Traduzir/adaptar todo o copy seção a seção (usar o mapa 2.2), guardando em
   `conteudo.md` para revisão do Nei antes de codar.
2. ~~Decidir identidade visual~~ **Decidido: padrão INEMA dark-âmbar** + escada futurista (2.2.1).
3. (Opcional) Revisar atualidade das recomendações de modelos.

### Fase 2 — Página (1 dia)
4. Portar o `index.html`: copiar a base do original, substituir todo texto pelo PT-BR,
   `lang="pt-BR"`, ajustar marca/links. Manter CSS e JS praticamente intactos
   (traduzir strings do JS: tiers, tooltips, "copied ✓" → "copiado ✓", legenda do sync).
5. Gerar as 4 ilustrações no flux2-klein (temas futuristas da seção 2.1, paleta
   dark âmbar+ciano, proporção larga ~16:7 como no original) → `raw-images/`; copiar logos SVG.
6. Criar `raw-images/icon.png` (favicon — o original nem tem).

### Fase 3 — QA (½ dia)
7. Testar as 4 interações: slider (8 stops × todos os campos), sincronismo bidirecional
   dos 2 sliders, toggle size⇄power com animação e dim dos dots, todos os copy-to-clipboard.
8. Responsivo: breakpoints 820/780/760/720/680/640/480px do original.
9. Revisão de texto final (tom: direto, levemente épico, como o original).

### Fase 4 — Publicação
10. `git init` + repo `inematds/local-kit` (autor `inematds <inematds@gmail.com>`),
    commit + push; ativar GitHub Pages (main, `/`).
11. Concluído = push no origin + página respondendo em
    `https://inematds.github.io/local-kit/`.
12. (Se desejado) card no portal via skill `atualiza-portal`.

---

## 4. Estrutura final do repo

```
local-kit/
├── PLANO.md              ← este plano
├── conteudo.md           ← copy PT-BR aprovado (Fase 1)
├── index.html            ← a página (self-contained)
├── raw-images/           ← ilustrações novas + logos SVG + icon.png
└── referencia/           ← captura do original (não publicar no Pages? é público de
    ├── original.html        qualquer forma; manter para diff/consulta)
    └── raw-images/
```

---

## 5. Execução por agente (Sonnet)

Este plano foi escrito para ser executável por um agente Sonnet sem contexto extra.
Avaliação de viabilidade (2026-07-16):

- ✅ **Fases 2 e 3 (portar HTML + QA):** totalmente executáveis por Sonnet — o
  `referencia/original.html` contém 100% do CSS/JS a portar; este plano contém todo o
  mapa de tradução (2.2) e a escada de tiers (2.2.1). Trabalho mecânico e bem definido.
- ⚠️ **Imagens (flux2-klein):** Sonnet executa, mas os prompts das 4 ilustrações
  (seção 2.1) devem ser seguidos à risca; se o resultado visual ficar fraco, escalar
  a curadoria para o modelo principal ou pedir revisão do Nei.
- ⚠️ **Fase 1 (copy PT-BR):** Sonnet consegue, mas o tom (direto, levemente épico) é a
  parte mais sensível — gerar `conteudo.md` e **parar para aprovação do Nei** antes da Fase 2.
- ✅ **Fase 4 (git/Pages):** mecânica; autor `inematds <inematds@gmail.com>`, repo
  `inematds/local-kit`, Pages em main `/`. Se o push tocar `.github/workflows/`, usar SSH.

**Instruções ao agente executor:**
1. Ler este PLANO.md inteiro + `referencia/original.html` antes de escrever qualquer coisa.
2. Padrão visual INEMA: dark premium, acento âmbar, secundário sky/ciano (referência:
   skill `projetos-landing-guia` / cursos INEMA existentes).
3. Não inventar conteúdo técnico novo — os dados (tiers, modelos, comandos, números)
   vêm do original, apenas traduzidos e re-tematizados conforme 2.2/2.2.1.
4. Checkpoint obrigatório: apresentar `conteudo.md` ao Nei antes de codar o `index.html`.
5. Fechar o loop: abrir o `index.html` final (browser/screenshot) e testar slider,
   sincronismo, toggle size⇄power e clipboard antes de dar por pronto.
