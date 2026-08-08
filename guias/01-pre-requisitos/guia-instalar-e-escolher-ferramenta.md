# GUIA INSTALAR E ESCOLHER A FERRAMENTA — terminal, desktop ou Codex (a votação da Aula 1)

> **Estou perdido em:** "Claude Code, Claude Desktop, Codex, VS Code… qual deles eu instalo pra fazer esta aula?".
> **O que você vai ter no final:** UMA ferramenta instalada e funcionando, escolhida pelo seu perfil — e a certeza de que as 7 skills entregam o mesmo resultado nas quatro opções.
> **Fontes cruzadas:** o `README.md` deste repo (seção "Qual ferramenta você usa?", opções A/B/C) · o `AGENTS.md` (que descreve como o Codex carrega as skills espelhadas em `.agents/skills/`) · a Aula 1 ao vivo, onde a professora fez uma votação e comparou desktop × terminal na prática · a página oficial de setup do Claude Code (`code.claude.com/docs/en/setup`, consultada em 03/08/2026 — comandos, requisitos de sistema e exigência de plano pago conferidos linha a linha) · a documentação e o pacote npm oficial do Codex CLI.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 🧰 Ferramenta | Terminal aberto, e você sabe em que pasta ele está | leia [guia-terminal-e-pastas.md](guia-terminal-e-pastas.md) |
| 🔑 Conta/acesso | Conta Claude **paga** (Pro, Max, Team, Enterprise ou Console) **ou** conta OpenAI paga | ⚠️ **o plano gratuito do Claude.ai NÃO dá acesso ao Claude Code** — é exigência oficial, não limitação de uso. Assine em [claude.ai](https://claude.ai), ou vá pela **Opção D** deste guia |
| 🧰 Ferramenta | Sistema compatível: macOS 13+, Windows 10 (build 1809+), Ubuntu 20.04+/Debian 10+ · 4 GB de RAM | sistema mais antigo: use a **Opção D** (colar o `SKILL.md` em qualquer IA de chat) |

## A escolha, em uma tabela

As 7 skills são **arquivos de texto** dentro do projeto. Qualquer ferramenta que consiga ler esses arquivos executa a aula. A escolha é de conforto, não de resultado.

| Opção | Como é na prática | Escolha se… |
|---|---|---|
| **A. Claude Code no terminal** | Você digita `/desenho-processo-comercial` numa telinha preta. Direto, rápido, sem enfeite. Na Aula 1: *"ele não explica nada, você tem que saber o que está fazendo"* | você já é confortável com terminal, ou quer o caminho que a maioria da turma escolheu |
| **B. Claude Desktop (aba Code)** | Aplicativo com janela. Ao digitar `/`, ele **mostra a descrição de cada skill**; você vê a pasta em que está trabalhando; o HTML de cada entrega abre dentro do próprio app | você é iniciante, ou já se perdeu entre abas de terminal. Avaliação da professora na Aula 1: *"didaticamente falando, o Claude Desktop arrasou"* |
| **C. Codex CLI** | Mesma coisa do terminal, do lado da OpenAI. Lê o `AGENTS.md` da raiz e as skills espelhadas em `.agents/skills/` | você já usa Codex pra programar, ou sua assinatura é OpenAI |
| **D. Sem instalar nada** | Você abre o `SKILL.md` num editor de texto, copia o conteúdo e cola numa conversa do ChatGPT/Gemini | você não quer instalar nada agora. Funciona pior (a IA não sabe qual arquivo vem depois), mas resolve o problema comercial igual |

⚠️ **O que NÃO muda entre elas:** o `git clone` do projeto é sempre feito no terminal (próximo guia). Depois disso, tanto faz. E em qualquer opção, o resultado sai em `.md` + `.html`.

**VS Code conta como qual?** Como a opção A. O terminal embutido do VS Code é um terminal normal — com a vantagem de você enxergar a árvore de pastas do lado. Na Aula 1: *"basicamente é o terminal; a diferença é que no VS Code você consegue ver as pastas, que também é tão bom quanto"*.

## Opção A — Instalar o Claude Code (terminal)

1. Abra o terminal.
2. Rode o instalador oficial:

   **macOS / Linux:**
   ```bash
   curl -fsSL https://claude.ai/install.sh | bash
   ```

   **Windows (PowerShell):**
   ```powershell
   irm https://claude.ai/install.ps1 | iex
   ```

   ⚠️ **Está em dúvida se a sua janela é PowerShell ou CMD?** O prompt do PowerShell começa com `PS C:\`; o do CMD é só `C:\`, sem o `PS`. Se você errar, a mensagem diz qual é qual — veja o erro N8.

3. **Feche o terminal e abra de novo.** (Sem isso o comando novo não é reconhecido — é o erro N2 abaixo.)
4. Confirme a instalação:
   ```bash
   claude --version
   ```
   Tem que responder algo como `2.1.211 (Claude Code)`. Se responder "comando não encontrado", vá ao erro N2.
5. Rode `claude` uma vez. Ele abre o navegador pra você entrar na sua conta Claude. Autorize e volte ao terminal.

**Alternativas ao instalador nativo** (use se o comando acima falhar, ou se você já usa um gerenciador de pacotes):

| Onde | Comando |
|---|---|
| macOS com Homebrew | `brew install --cask claude-code` |
| Windows com WinGet | `winget install Anthropic.ClaudeCode` |
| Qualquer sistema, com Node.js 22+ | `npm install -g @anthropic-ai/claude-code` |

⚠️ **O instalador nativo se atualiza sozinho em segundo plano.** Homebrew e WinGet **não** — neles você atualiza na mão (`brew upgrade claude-code` / `winget upgrade Anthropic.ClaudeCode`).

⚠️ **Nunca use `sudo npm install -g`** — gera problema de permissão e risco de segurança.

**No Windows, vale instalar o [Git for Windows](https://git-scm.com/downloads/win)** (você já vai precisar dele pro `git clone` do próximo guia). Com ele instalado, o Claude Code usa o Git Bash e ganha capacidade de rodar comandos; sem ele, cai no PowerShell.

## Opção B — Instalar o Claude Desktop

1. Acesse **[claude.ai/download](https://claude.ai/download)**.
2. Baixe a versão do seu sistema (Windows ou macOS) e instale como qualquer programa.
3. Abra o aplicativo e entre com sua conta.
4. Na barra lateral, clique em **Code** (não é o chat normal — o chat normal não enxerga suas pastas).
5. Clique em abrir/adicionar pasta e escolha a pasta do projeto (a que você vai criar no próximo guia).

Quando você digitar `/` dentro dele, as 7 skills aparecem numa lista **com a descrição de cada uma ao lado**. É a diferença prática mais útil pra quem está começando.

## Opção C — Instalar o Codex CLI

1. Instale (precisa do **Node.js 22 ou superior**):
   ```bash
   npm install -g @openai/codex
   ```

   ⚠️ **Repare no `@openai/`.** `npm install -g codex` instala um pacote sem relação nenhuma — é o erro mais comum da instalação do Codex.

   Alternativas: `brew install --cask codex` (macOS) ou `curl -fsSL https://chatgpt.com/codex/install.sh | sh` (Mac/Linux).
2. Autentique:
   ```bash
   codex login
   ```
3. Abra na pasta do projeto:
   ```bash
   codex
   ```
4. Peça naturalmente: *"quero desenhar meu processo comercial"*, ou use `@desenho-processo-comercial` se a sua interface usar esse prefixo.

O Codex lê sozinho o `AGENTS.md` da raiz do projeto — ele já sabe onde estão as skills e qual é a primeira a rodar.

## Opção D — Sem instalar nada

1. Baixe o projeto (próximo guia, caminho do ZIP).
2. Abra `.claude/skills/desenho-processo-comercial/SKILL.md` em qualquer editor de texto (Bloco de Notas serve).
3. Copie tudo **a partir do título `# Desenho do Processo Comercial`** — pule o bloco entre `---` no topo.
4. Cole numa conversa nova no ChatGPT, Gemini ou similar, e responda as perguntas.
5. Ao terminar, abra o próximo `SKILL.md` na mão e repita.

**A limitação honesta:** a IA não vai saber automaticamente qual arquivo vem depois, e não vai criar a Central de Entregas sozinha. Você faz esse controle manualmente.

## Teste de sucesso

**Opções A e C:** no terminal, rode:

```bash
claude --version
```
(ou `codex --version`)

Tem que sair um número de versão, tipo `2.x.x`. Se sair "comando não encontrado", a instalação não terminou.

**Opção B:** abra o Claude Desktop, vá em **Code**, e confirme que existe um campo pra digitar. Se você já tiver a pasta do projeto aberta, digite `/` — as skills devem aparecer.

**Opção D:** abra um `SKILL.md` no editor e confirme que você consegue ler o texto.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| N1 | O instalador pede senha de administrador | Normal em Mac/Linux | digite a senha do seu usuário (ela não aparece na tela — veja o erro W3) |
| N2 | `claude: command not found` / `'claude' não é reconhecido` logo depois de instalar | O terminal ainda está com a lista de comandos antiga carregada | 1) **feche o terminal e abra de novo** (resolve na maioria das vezes) 2) `claude --version` 3) rode **`claude doctor`** — ele imprime um diagnóstico completo da instalação e das configurações, com os problemas encontrados e a correção sugerida 4) se persistir, reinstale, ou use uma das alternativas (Homebrew / WinGet / npm) |
| N3 | Windows bloqueou o script: *"execução de scripts foi desabilitada neste sistema"* | Política de execução padrão do PowerShell | rode `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, responda `S`/`Y`, e repita a instalação |
| N4 | `npm: command not found` ao tentar instalar o Codex | Node.js não está instalado | instale o Node.js em [nodejs.org](https://nodejs.org) (versão LTS), feche o terminal, abra de novo e repita |
| N5 | Instalei, abri, mas digitei `/` e **nenhuma skill do cohort aparece** | A ferramenta foi aberta numa pasta que não é a do projeto | é o erro mais comum do repo inteiro — veja `R6` no [guia-baixar-e-abrir-o-projeto.md](guia-baixar-e-abrir-o-projeto.md) |
| N6 | Abri o Claude Desktop mas ele só mostra um chat, sem pasta nenhuma | Você está na aba de chat, não na aba **Code** | clique em **Code** na lateral e abra a pasta do projeto ali |
| N7 | As skills aparecem no Claude Code mas não no autocompletar do Desktop (ou o contrário) | Comportamento conhecido de algumas versões: a skill funciona se digitada inteira, mesmo sem aparecer na lista ([issue #58556](https://github.com/anthropics/claude-code/issues/58556)) | 1) digite o nome completo `/desenho-processo-comercial` e aperte Enter mesmo assim 2) se executar, siga normal 3) se não, atualize a ferramenta pra última versão |
| N8 | `The token '&&' is not a valid statement separator` | Você rodou o comando do **CMD** dentro do **PowerShell** | use o comando do PowerShell: `irm https://claude.ai/install.ps1 \| iex` |
| N9 | `'irm' is not recognized as an internal or external command` | O contrário: você rodou o comando do **PowerShell** dentro do **CMD** | 1) abra o **PowerShell** (tecla Windows → digite `powershell`) e rode lá 2) ou use o comando de CMD: `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd` |
| N10 | Instalei o Codex e o comando não existe, ou instalou outra coisa | Você rodou `npm install -g codex` sem o `@openai/` | 1) `npm uninstall -g codex` 2) `npm install -g @openai/codex` 3) se der `EBADENGINE` ou erro de versão, atualize o Node pra 22+ |
| N11 | O instalador falhou com `403` ou `syntax error near unexpected token '<'` | O download veio quebrado (rede, proxy, firewall corporativo) | 1) tente de novo 2) se repetir, use uma das alternativas: Homebrew (Mac), WinGet (Windows) ou npm 3) em rede corporativa, teste fora dela |

**Se nada resolver:** print da mensagem de erro + *"o que tem que ser feito? PESQUISE isso antes de responder"* numa conversa com a IA — a palavra PESQUISE faz ela buscar na web em vez de chutar.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | com a ferramenta instalada, baixe o projeto |
| 📖 Ler | [guia-baixar-e-abrir-o-projeto.md](guia-baixar-e-abrir-o-projeto.md) — `git clone`, abrir na pasta certa e rodar a primeira skill |
| 🚑 Se travar | o catálogo N1–N11 acima; se for "não achou a skill", vá direto pro `R6` do próximo guia |
