# Conteúdo PT-BR — Laboratório Local (INEMA)

> Copy completo, seção a seção, pronto para colar no `index.html` (Fase 2).
> Fatos/números/comandos preservados do original; texto todo traduzido/adaptado.
> Escada de tiers = tema futurista (PLANO.md §2.2.1), não a mitologia/alquimia do original.

---

## META

- **`<title>`:** `O Laboratório Local · Bonus Kit — INEMA.CLUB`
- **`<link rel="icon">`:** `raw-images/icon.png`
- **`lang`:** `pt-BR`
- **Badge do topo (topbar, canto direito):** `Capítulo 3 · Kit Bônus`
- **Link do topbar (canto esquerdo):** `← INEMA.CLUB · Início` → aponta para `https://inema.club/`
- **Footer:** `INEMA.CLUB · Kit bônus do Capítulo 3 · inema.club` (link para `https://inema.club/`)

---

## HERO

- **Eyebrow (verde, com hastes):** `Rodando modelos locais · A Estratégia Local`
- **H1 (com itálico serifado):**
  `O Laboratório Local.` <br> *`Grátis. Privado. Seu.`*
- **Subtítulo (serifado itálico):**
  `Qual modo rodar, o que sua máquina realmente aguenta, os modelos que valem o disco — e as duas armadilhas que fazem as pessoas acharem que local é ruim.`
- **Ilustração:** `raw-images/hero.jpg` — alt: `O Laboratório Local — a estação do futuro`

---

## SEÇÃO 01 — Escolha seu modo

- **Tag:** `01 · A estratégia`
- **H2 (com itálico):** `Escolha seu` *`modo`* `primeiro.`
- **Lead:** `Local não é tudo ou nada. Decida o quanto sai da sua máquina — a escolha do modelo vem depois.`
- **Ilustração:** `raw-images/modos.jpg` — alt: `Escolha seu modo — cofre, conectado, nuvem`

### Cards de modo (3)

1. **🔒 Cofre**
   - Lema (itálico): `nada nunca sai`
   - Parágrafo: `100% local, funciona offline. Dados de cliente, contratos, saúde, trabalho ainda não lançado.`
   - Tag: `trabalho sensível`

2. **🔌 Conectado**
   - Lema (itálico): `local primeiro, nuvem sob demanda`
   - Parágrafo: `O local cuida dos rascunhos e do trabalho pesado; você troca pra nuvem nas decisões mais difíceis.`
   - Tag: `★ a estratégia do dia a dia`

3. **☁️ Nuvem-primeiro**
   - Lema (itálico): `local só para os 5% privados`
   - Parágrafo: `Nuvem por padrão; cai pro local só quando algo não pode sair da máquina.`
   - Tag: `pouca vram`

---

## SEÇÃO 02 — Sua máquina

- **Tag:** `02 · Sua máquina`
- **H2 (com itálico):** `O que` *`sua`* `máquina realmente aguenta?`
- **Lead:** `Arraste até a memória da sua máquina — em Mac com Apple Silicon, memória unificada conta como VRAM. Em PC, use a VRAM da sua GPU.`

### Labels do slider

- **Label acima do número:** `sua memória · vram ou apple unificada`
- **Sufixo do número grande:** `GB`
- **Ticks abaixo do slider:** `8` `16` `24` `32` `48` `64` `96` `128`
- **Nota final do rig:** `Regra de bolso: o arquivo do modelo mais o cache de contexto moram na memória — deixe folga. Tamanhos assumem quantização Q4.`
- **Label do mini-slider (seção 04, sincronizado):** `seus GB`

### Tabela completa dos 8 tiers

> Nome futurista conforme a escada do PLANO.md §2.2.1. Emoji preservado onde fizer sentido
> ao novo nome; troquei os que remetiam a laboratório/mitologia por versões sci-fi.

---

#### Tier 1 — 8 GB — 🤖 A Cápsula

- **Nota de contexto:** `mantenha o contexto ≤16–32K`
- **Descrição:** `Pequena, mas de verdade. Llama 3.2, Gemma 3 e Qwen3 nos tamanhos compactos — bate-papo, rascunhos e trabalho braçal, ágil em quase qualquer hardware.`
- **Chips (modelo · comando):**
  - ★ Llama 3.2 3B → `ollama pull llama3.2:3b`
  - Gemma 3 4B → `ollama pull gemma3:4b`
  - Qwen3 4B → `ollama pull qwen3:4b`
- **Máquina do tempo:**
  - Data: `fim de 2022 — 3 anos e meio atrás`
  - Nota: `Os modelos pequenos de hoje superam o ChatGPT original (GPT-3.5) com folga.`
- **Parente moderno mais próximo:**
  - Nome: `≈ o andar nano de hoje`
  - Nota: `Trabalhos de nível GPT-5.4-Nano — bate-papo, rascunhos, triagem. A cadeira barata que fica sempre ligada.`

---

#### Tier 2 — 16 GB — 🔧 A Doca

- **Nota de contexto:** `32K confortável`
- **Descrição:** `A classe de 14–20B se abre. O GPT-OSS 20B — o modelo aberto da OpenAI, feito pra rodar em 16GB — chega junto com um raciocinador de verdade.`
- **Chips:**
  - ★ GPT-OSS 20B → `ollama pull gpt-oss:20b`
  - Qwen3 14B → `ollama pull qwen3:14b`
  - DeepSeek-R1 14B → `ollama pull deepseek-r1:14b`
- **Máquina do tempo:**
  - Data: `janeiro de 2025 — 18 meses atrás`
  - Nota: `O GPT-OSS 20B troca socos com o o3-mini — a própria OpenAI reivindicou essa paridade no post de lançamento.`
- **Parente moderno mais próximo:**
  - Nome: `≈ OpenAI o3-mini`
  - Nota: `O parente mais próximo oficial — direto do post de lançamento da OpenAI. Em termos Claude: batendo na porta do Haiku.`

---

#### Tier 3 — 24 GB — ⚡ O Núcleo ★ (ponto ideal — o tier desta lição)

- **Nota de contexto:** `64K com quantização de KV-cache`
- **Descrição:** `Qwen3-Coder 30B a ~40 tok/s com contexto de verdade — a melhor experiência de código local por real investido. É o tier em torno do qual esta lição inteira foi construída.`
- **Chips:**
  - ★ Qwen3-Coder 30B → `ollama pull qwen3-coder:30b-a3b`
  - Gemma 3 27B → `ollama pull gemma3:27b`
  - GPT-OSS 20B → `ollama pull gpt-oss:20b`
- **Máquina do tempo:**
  - Data: `meados de 2024 — dois anos atrás`
  - Nota: `Esse tier joga na liga do GPT-4o — o melhor modelo do planeta naquela época.`
- **Parente moderno mais próximo:**
  - Nome: `≈ o andar rápido de hoje`
  - Nota: `Cavalos de trabalho tipo Haiku 4.5 / Flash — a mesma liga de tarefas, uma conta bem diferente.`

---

#### Tier 4 — 32 GB — 🔥 O Reator

- **Nota de contexto:** `contexto maior, mais folga`
- **Descrição:** `O mesmo coder, mas a folga extra vai direto pra contexto e velocidade — e os raciocinadores de 32B cabem sem apertar.`
- **Chips:**
  - ★ Qwen3-Coder 30B → `ollama pull qwen3-coder:30b-a3b`
  - DeepSeek-R1 32B → `ollama pull deepseek-r1:32b`
  - Qwen3 32B → `ollama pull qwen3:32b`
- **Máquina do tempo:**
  - Data: `setembro de 2024 — quase dois anos atrás`
  - Nota: `A DeepSeek fez o benchmark do destilado R1-32B passar do o1-mini — números publicados por eles mesmos.`
- **Parente moderno mais próximo:**
  - Nome: `≈ OpenAI o1-mini`
  - Nota: `O raciocinador mini que os destilados desse tier foram feitos pra igualar. Em termos Claude: raciocínio nível Haiku.`

---

#### Tier 5 — 48 GB — 🚀 A Nave de Carga

- **Nota de contexto:** `contexto longo viável`
- **Descrição:** `A classe 70B chega, quantizada — o Llama de porte carro-chefe da Meta, com o coder ainda residente ao lado.`
- **Chips:**
  - ★ Llama 3.3 70B → `ollama pull llama3.3:70b`
  - DeepSeek-R1 32B → `ollama pull deepseek-r1:32b`
  - Qwen3-Coder 30B → `ollama pull qwen3-coder:30b-a3b`
- **Máquina do tempo:**
  - Data: `março de 2023 — mais de três anos atrás`
  - Nota: `O GPT-4 original — este tier supera com folga o modelo que mudou tudo.`
- **Parente moderno mais próximo:**
  - Nome: `≈ os carros-chefe de 405B de 2024`
  - Nota: `A Meta posicionou o Llama 3.3 70B no nível do seu carro-chefe de 405B — a classe que enfrentou GPT-4o e Claude 3.5 Sonnet.`

---

#### Tier 6 — 64 GB — 🛰️ Controle da Missão

- **Nota de contexto:** `contexto longo, múltiplos modelos`
- **Descrição:** `Raciocínio de fronteira destilado pra 70B, rodando com contexto genuinamente longo — ou vários modelos menores residentes ao mesmo tempo.`
- **Chips:**
  - ★ DeepSeek-R1 70B → `ollama pull deepseek-r1:70b`
  - Llama 3.3 70B → `ollama pull llama3.3:70b`
  - Qwen3-Coder 30B → `ollama pull qwen3-coder:30b-a3b`
- **Máquina do tempo:**
  - Data: `os carros-chefe de 2024 — dois anos atrás`
  - Nota: `Respostas de classe 405B vivendo na sua mesa — agora com o contexto pra usá-las de verdade.`
- **Parente moderno mais próximo:**
  - Nome: `≈ os gigantes abertos alugados`
  - Nota: `Território GLM / DeepSeek — o que falta é contexto e velocidade, não classe.`

---

#### Tier 7 — 96 GB — 🌌 A Estação Orbital

- **Nota de contexto:** `~128K prático`
- **Descrição:** `A classe 120B entra em cena — o GPT-OSS 120B pede ~80GB — com espaço sobrando pro coder e um raciocinador.`
- **Chips:**
  - ★ GPT-OSS 120B → `ollama pull gpt-oss:120b`
  - DeepSeek-R1 70B → `ollama pull deepseek-r1:70b`
  - Qwen3-Coder 30B → `ollama pull qwen3-coder:30b-a3b`
- **Máquina do tempo:**
  - Data: `abril de 2025 — 15 meses atrás`
  - Nota: `O GPT-OSS 120B aterrissa perto do o4-mini — paridade reivindicada pela própria OpenAI.`
- **Parente moderno mais próximo:**
  - Nome: `≈ OpenAI o4-mini`
  - Nota: `O parente mais próximo oficial, direto do post de lançamento. Em termos Claude: território Haiku 4.5.`

---

#### Tier 8 — 128 GB — 🪐 A Frota Estelar

- **Nota de contexto:** `contexto longo em tudo`
- **Descrição:** `Tudo desta página roda ao mesmo tempo, todos com contexto de verdade. Nesse ponto, seu gargalo são as ideias, não a memória.`
- **Chips:**
  - ★ GPT-OSS 120B → `ollama pull gpt-oss:120b`
  - Llama 3.3 70B → `ollama pull llama3.3:70b`
  - DeepSeek-R1 70B → `ollama pull deepseek-r1:70b`
- **Máquina do tempo:**
  - Data: `abril de 2025 — 15 meses atrás`
  - Nota: `Raciocínio classe o4-mini, totalmente offline — com espaço pro elenco inteiro ao lado.`
- **Parente moderno mais próximo:**
  - Nome: `≈ OpenAI o4-mini`
  - Nota: `Raciocínio quase-fronteira que nunca sai da sua mesa — território Haiku 4.5, em termos Claude.`

---

## SEÇÃO 03 — Três trabalhos. Três campeões.

- **Tag:** `03 · Os melhores da categoria`
- **H2 (com itálico):** `Três trabalhos. Três` *`campeões.`*
- **Lead:** `Não colecione modelos — designe-os. Clique num comando pra copiar.`

### Campeões (3)

1. **01 · Qwen3-Coder 30B**
   - Papel (kicker): `o programador`
   - Descrição: `Qualidade de classe 32B na velocidade de um modelo pequeno. O rei do código local.`
   - Pill: `24GB · ~40 tok/s`
   - Comando: `ollama pull qwen3-coder:30b-a3b`

2. **02 · DeepSeek-R1 14B**
   - Papel: `o raciocinador`
   - Descrição: `Cadeia de raciocínio de fronteira, destilada. Veja ele pensar antes de responder.`
   - Pill: `16GB · 32B / 70B acima`
   - Comando: `ollama pull deepseek-r1:14b`

3. **03 · GPT-OSS 20B**
   - Papel: `o generalista`
   - Descrição: `Os pesos abertos da OpenAI. Bate-papo, ferramentas e agentes, no estilo da casa.`
   - Pill: `feito para 16GB`
   - Comando: `ollama pull gpt-oss:20b`

---

## SEÇÃO 04 — Seis casas. Todos os tamanhos.

- **Tag:** `04 · O cenário local`
- **H2 (com itálico):** `Seis casas. Todo` *`tamanho.`*
- **Lead:** `Toda casa lança uma **escada de tamanhos** — o mesmo cérebro, escalado pra cima ou pra baixo. O Ollama é a porta de entrada pra todas elas. **Os pontos que cabem na sua máquina ficam acesos** (sincronizado com o slider acima) — clique em qualquer ponto pra copiar o comando de pull.`

### Cabeçalho do gráfico

- Título: `O cenário de modelos locais`
- Botões do toggle: `tamanho` / `poder`

### Subtítulos das 6 famílias (linha abaixo do nome)

1. **Qwen3** → `pragmático · adora ferramentas`
2. **DeepSeek-R1** → `pensa em voz alta`
3. **GPT-OSS** → `genes de fronteira · rígido`
4. **Gemma 3** → `polido · o mais seguro`
5. **Llama** → `o padrão · meio-termo`
6. **Mistral** → `enxuto · relaxado`

### Labels do eixo de poder (view "power")

- `papo rápido`
- `trabalho de verdade`
- `nível agente`
- `quase-fronteira`

### Eixo de tamanho (view "size", mantém números)

- `1B` `8B` `30B` `70B` `120B`

### Rodapé do gráfico

- Legenda esquerda: `tamanho do ponto = parâmetros · faixa verde = alcance da sua máquina (arraste o slider) · ★ = o coder`
- Legenda de sync (dinâmica via JS, ver Microcopy): `✦ acesos = cabem nos seus X GB`

### Callout — Mesmos cérebros, modos diferentes

- Ícone: 🎭
- Título: `Mesmos cérebros, modos diferentes`
- Texto: `Alinhamento também é especificação técnica. **Gemma e GPT-OSS** vêm travados de fábrica — recusam qualquer coisa mais picante, o que é exatamente o que você quer pra uso seguro em família ou de frente pro cliente. **Llama** fica no meio-termo; **Mistral** é mais solto. E existem também modelos totalmente **neutros**, que você mesmo direciona — essa é a especialidade da Nous Research, com modelos abertos e steeráveis feitos sob medida pra esse tipo de controle. Escolha o temperamento certo pro trabalho certo.`

  > Nota de tradução: o original cita "lesson 3.6" (aula interna da masterclass Hermes); removido conforme instrução — a menção agora é neutra, só sobre o produto da Nous Research.

### Links (3)

1. `ollama.com` (com logo)
2. `ver a biblioteca de modelos →`
3. `LM Studio (interface gráfica)` (com logo)

---

## SEÇÃO 05 — O contexto honesto

- **Tag:** `05 · O contexto honesto`
- **H2 (com itálico):** `Local é bom,` *`de verdade?`*
- **Lead:** `Resposta honesta: um bom 30B local hoje faz o que a fronteira fazia não faz muito tempo — e pra rascunho, trabalho braçal e documento privado, isso já é a maior parte dos seus tokens.`
- **Ilustração:** `raw-images/espectro.jpg` — alt: `O espectro de poder — de 8B até a fronteira`

### As 4 bandas

1. **local · pequeno** → `O cérebro de bolso`
   `Bate-papo, rascunhos, resumos — rápido, leve, roda em quase qualquer coisa.`

2. **local · 30B ★** → `A fronteira de ontem`
   `Código de verdade, agentes de verdade, contexto de verdade — na sua própria mesa, de graça.`

3. **gigantes alugados** → `Abertos, mas enormes`
   `GLM, DeepSeek, Kimi — fronteira de peso aberto. Grandes demais pra hospedar em casa; centavos pra alugar.`

4. **nuvem de fronteira** → `Os 5% mais difíceis`
   `Raciocínio profundo, arquitetura, bom gosto de design. Manda pra cá — e depois volta pra casa.`

### Callout — Onde a linha realmente passa

- Ícone: ⚖️
- Título: `Onde a linha realmente passa`
- Texto: `Em raciocínio puro, a fronteira ainda ganha — é por isso que o modo Conectado existe. Mas a vantagem do local não é QI: é **custo zero por token, zero saída de dados e nenhum limite de taxa**. Direcione por tarefa, não por lealdade.`

---

## SEÇÃO 06 — As duas armadilhas

- **Tag:** `06 · As duas armadilhas`
- **H2 (com itálico):** `Por que acham que local é` *`ruim.`*
- **Lead:** `Geralmente não é o modelo. É uma dessas duas configurações.`

### Armadilha 1 — O padrão de 4.096 tokens

- Ícone: 🧠
- Título: `O padrão de 4.096 tokens`
- Texto: `O contexto real do Qwen3-Coder é de **256K**. O Ollama entrega ele travado em **4K** — você está usando ~1,6% do cérebro e depois culpando o modelo.`
- Labels das barras: `nativo · 256K` / `padrão · 4K` (em vermelho)
- Fix: `**Fix:** \`OLLAMA_CONTEXT_LENGTH=65536 ollama serve\``

### Armadilha 2 — A parede do KV-cache

- Ícone: 🌊
- Título: `A parede do KV-cache`
- Texto: `Contexto consome memória: um 70B precisa de **~42GB só de cache a 128K**. Máquinas de consumidor batem o teto por volta de **32–64K utilizáveis** — é o cache que não cabe, não o modelo.`
- Fix: `**Fix:** quantização do KV-cache — \`q8_0\` reduz o cache de memória praticamente pela metade, com perda mínima de qualidade.`

---

## SEÇÃO 07 — Ligando os fios

- **Tag:** `07 · Ligando os fios`
- **H2 (com itálico):** `Três comandos para uma` *`sala lacrada.`*
- **Lead:** `O Ollama expõe um endpoint compatível com OpenAI em **localhost:11434** — seu agente pluga como qualquer outro cérebro. Nada sai da máquina.`

### Bloco de terminal

- Título da barra: `terminal · local e grátis`
- Botão: `copiar` (comportamento de copiar o bloco inteiro)

Comandos (comandos shell intactos, comentários traduzidos):

```
# 1 · puxe o coder
$ ollama pull qwen3-coder:30b-a3b

# 2 · suba o contexto ANTES de julgar
$ OLLAMA_CONTEXT_LENGTH=65536 ollama serve

# 3 · aponte seu cliente pra localhost
$ <seu-cliente-openai-compatible> --model qwen3-coder:30b-a3b --base-url http://localhost:11434/v1
```

> Nota de adaptação (regra do PLANO.md §2.1 e da tarefa): o original usa o CLI proprietário
> `hermes config set model ...`. Aqui, o passo 3 vira uma instrução genérica: aponte
> **qualquer cliente compatível com OpenAI** (seu agente, script, LM Studio, etc.) para
> `http://localhost:11434/v1`, usando o `--base-url` (ou equivalente) do cliente escolhido.
> O texto de exemplo acima usa `<seu-cliente-openai-compatible>` como placeholder — na Fase 2,
> avaliar se vale trocar por um exemplo mais concreto (ex.: `curl` num endpoint `/chat/completions`,
> ou o nome de um cliente real tipo `openai` CLI) para não soar abstrato demais.

### Links (2)

1. `baixar Ollama` (com logo)
2. `prefere interface gráfica? LM Studio` (com logo)

### Ilustração final

- `raw-images/final.jpg` — alt: `Sua máquina. Sua mente.`

### Caixa "E daí →"

- Label: `E daí →`
- Texto: `Hoje à noite: arraste o slider até sua máquina, puxe os **modelos recomendados**, e suba o contexto **antes** de julgar qualquer coisa. Seu laboratório é grátis, privado e está sempre aberto.`

---

## MICROCOPY JS

- **Feedback de cópia (comandos, dots do gráfico, botão do terminal):** `copiado ✓`
  (substitui `copied ✓` em todos os lugares — dots do gráfico de famílias, comandos dos
  3 campeões, botão de copiar do terminal)
- **Legenda de sync do gráfico (dinâmica):**
  `✦ acesos = cabem nos seus X GB` (com `X` = valor atual do slider; quando a view é "poder",
  acrescentar ` · ordenado por capacidade`)
- **Tooltips dos pontos do gráfico (`data-tip`, formato `<tag> · <nota>`):**
  - Para os que cabem numa faixa de GB: `<tag> · cabe em <N>GB+` (ex.: `qwen3:4b · cabe em 8GB+`)
  - Para o campeão marcado com ★: `★ <tag> · cabe em <N>GB+`
  - Para os que rodam em qualquer hardware (gemma3:1b, llama3.2:1b): `<tag> · roda em qualquer lugar`
  - Ao clicar (feedback temporário): `copiado ✓`
- **`aria-label` dos sliders (rig principal e mini-slider do gráfico):** `Memória da máquina`
- **Alt-texts das imagens:** ver cada seção acima (já em PT-BR)

---

## Tabela de referência rápida — mapa de nomes aplicado

| Elemento | Original | PT-BR usado aqui |
|---|---|---|
| Título do site | The Local Lab · Free. Private. Yours. | O Laboratório Local · *Grátis. Privado. Seu.* |
| Seção 01 | Pick your mode | Escolha seu modo |
| Modos | Vault / Connected / Cloud-first | Cofre / Conectado / Nuvem-primeiro |
| Seção 02 | Your machine | Sua máquina |
| Tiers (8) | Pocket Lab → Mount Olympus | Cápsula → Doca → Núcleo ★ → Reator → Nave de Carga → Controle da Missão → Estação Orbital → Frota Estelar |
| Comparativos | time machine / closest modern relative | máquina do tempo / parente moderno mais próximo |
| Seção 03 | Three jobs. Three champions. | Três trabalhos. Três campeões. |
| Papéis | the coder / the reasoner / the all-rounder | o programador / o raciocinador / o generalista |
| Seção 04 | Six houses. Every size. | Seis casas. Todos os tamanhos. |
| Eixo poder | quick chat / real work / agent-grade / frontier-adjacent | papo rápido / trabalho de verdade / nível agente / quase-fronteira |
| Seção 05 | The honest context | O contexto honesto |
| Seção 06 | The two traps | As duas armadilhas |
| Seção 07 | Wire it up / a sealed room | Ligando os fios / uma sala lacrada |
| Encerramento | So what → | E daí → |

---

## Contagem

- **8 tiers** traduzidos por completo (nome, emoji, contexto, descrição, 3 chips cada,
  máquina do tempo, parente moderno) = seção 02.
- **10 seções de copy** cobertas: meta, hero, 01, 02, 03, 04, 05, 06, 07, microcopy JS.
- **3 campeões**, **6 famílias**, **4 bandas**, **2 armadilhas**, **3 comandos finais** —
  todos com fatos/números/comandos preservados do original.
