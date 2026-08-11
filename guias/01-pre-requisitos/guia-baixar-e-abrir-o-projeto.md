# GUIA BAIXAR E ABRIR O PROJETO — do `git clone` até a primeira skill respondendo

> **Estou perdido em:** "baixei o projeto (acho), abri a ferramenta, digitei `/desenho-processo-comercial` e apareceu **No commands match**".
> **O que você vai ter no final:** o projeto na sua máquina, a ferramenta aberta **dentro da pasta certa**, e a Skill 1 rodando de verdade.
> **Fontes cruzadas:** o `README.md` deste repo (Cenário 1 e Cenário 2 de instalação, incluindo o aviso das quatro pastas) · o `templates/README.md` (*"nenhuma skill cria esse painel do zero"*) · a própria `SKILL.md` da `squad-sales-bonus`, que lê `squads/squad-sales/` em tempo de execução · o `docs/SKILLS-INDEX.md` (FAQ de suporte: *"Digitei `/desenho-processo-comercial` e apareceu 'No commands match'"*) · a Aula 1 ao vivo, onde o clone falhou por pasta duplicada e depois por falta de `cd` · pesquisa web sobre o erro `destination path already exists`.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber abrir o terminal e usar `cd`, `ls`, `pwd` | leia [guia-terminal-e-pastas.md](guia-terminal-e-pastas.md) |
| 🧰 Ferramenta | Claude Code, Claude Desktop ou Codex instalado | leia [guia-instalar-e-escolher-ferramenta.md](guia-instalar-e-escolher-ferramenta.md) |
| 🧰 Ferramenta | `git` instalado (rode `git --version`) | se der erro: baixe em [git-scm.com](https://git-scm.com) — ou use o caminho do ZIP no Passo 1C |

## Antes de tudo: qual é o seu cenário?

| Seu caso | Vá para |
|---|---|
| Vou começar um projeto **novo** só pra esta aula | **Passo 1A** |
| Já tenho um projeto rodando e quero **só as skills** dentro dele | **Passo 1B** |
| Não tenho git / não quero mexer com terminal | **Passo 1C** |

## Passo 1A — Projeto novo (o caminho da aula)

1. No terminal, vá até a pasta onde você quer guardar o projeto:
   ```bash
   cd Documentos
   ```
2. **Confira que você está no lugar certo** antes de clonar:
   ```bash
   pwd
   ```
   Este é o passo que a professora pulou duas vezes ao vivo na Aula 1. Não pule.
3. Baixe o projeto:
   ```bash
   git clone https://github.com/marketingLendario/cohort-vendas.git
   ```
   Isso cria a pasta `cohort-vendas` **dentro de onde você está**, com tudo dentro.
4. **Entre na pasta que acabou de nascer.** O `git clone` cria a pasta, mas não te coloca dentro dela:
   ```bash
   cd cohort-vendas
   ```
   Fala literal da aula: *"ele criou, mas não abriu a pasta"*.
5. Confirme:
   ```bash
   pwd
   ls
   ```
   O `pwd` tem que terminar em `cohort-vendas`, e o `ls` tem que mostrar `README.md`, `AGENTS.md`, `GUIA-DO-ALUNO.html`, `GUIA-DO-ALUNO-AULA-2.html`, `guias`, `docs`, `templates`, `squads`, `exemplos`.

   > **Não vê `squads` nem `GUIA-DO-ALUNO-AULA-2.html`?** Seu clone é antigo. Rode `git pull` dentro da pasta.

Vá para o **Passo 2**.

## Passo 1B — Já tenho um projeto, quero só as skills dentro dele

Não clone o repositório inteiro por cima do seu projeto. Clone numa pasta temporária, copie **quatro** pastas, e apague a temporária.

⚠️ **São quatro pastas, não duas.** Skills sozinhas não bastam:

| Pasta | Se você esquecer |
|---|---|
| `.claude/skills` | nenhuma skill aparece no Claude Code |
| `.agents/skills` | nenhuma skill aparece no Codex |
| `templates` | **a Central de Entregas nunca nasce.** Nenhuma skill cria o painel do zero — a primeira skill de cada aula copia `templates/central-de-entregas.html` (Aula 1) ou `templates/central-de-entregas-aula2.html` (Aula 2) pra raiz do seu projeto. Sem a pasta, não há de onde copiar |
| `squads` | **a Skill 8 não tem o que ler.** O `/squad-sales-bonus` lê os frameworks em tempo de execução dentro de `squads/squad-sales/agents/` e `squads/squad-sales/tasks/`. Sem a pasta, ela não tem mente nenhuma pra aplicar |

⚠️ **Os comandos são diferentes no Windows e no Mac/Linux.** Use o bloco da sua máquina — copiar o bloco errado é o erro `R9` do catálogo.

**Mac / Linux (Terminal), ou Windows com Git Bash:**

```bash
cd /caminho/do/seu/projeto
git clone https://github.com/marketingLendario/cohort-vendas.git /tmp/cohort-vendas-temp
mkdir -p .claude/skills .agents/skills templates squads
cp -R /tmp/cohort-vendas-temp/.claude/skills/. .claude/skills/
cp -R /tmp/cohort-vendas-temp/.agents/skills/. .agents/skills/
cp -R /tmp/cohort-vendas-temp/templates/. templates/
cp -R /tmp/cohort-vendas-temp/squads/. squads/
rm -rf /tmp/cohort-vendas-temp
```

**Windows (PowerShell)** — mesma sequência, comandos do sistema:

```powershell
cd C:\caminho\do\seu\projeto
git clone https://github.com/marketingLendario/cohort-vendas.git $env:TEMP\cohort-vendas-temp
New-Item -ItemType Directory -Force .claude\skills, .agents\skills, templates, squads
Copy-Item "$env:TEMP\cohort-vendas-temp\.claude\skills\*" .claude\skills\ -Recurse -Force
Copy-Item "$env:TEMP\cohort-vendas-temp\.agents\skills\*" .agents\skills\ -Recurse -Force
Copy-Item "$env:TEMP\cohort-vendas-temp\templates\*" templates\ -Recurse -Force
Copy-Item "$env:TEMP\cohort-vendas-temp\squads\*" squads\ -Recurse -Force
Remove-Item "$env:TEMP\cohort-vendas-temp" -Recurse -Force
```

> `$env:TEMP` é a pasta temporária do seu usuário no Windows — o equivalente do `/tmp` do Mac/Linux. Você não precisa saber o caminho dela; o PowerShell resolve sozinho.

**Confira antes de seguir** — as quatro pastas têm que responder:

```bash
ls .claude/skills .agents/skills templates squads
```

⚠️ **Se você já tiver uma skill com o mesmo nome de alguma das 11, o comando sobrescreve só ela.** Revise antes se isso for um problema. O mesmo vale se você já tem uma pasta `templates/` própria: os arquivos do repo entram ao lado dos seus, e só sobrescrevem os de nome igual.

**Usa Codex?** Copie também o `AGENTS.md` deste repo e cole o conteúdo dele **no final** do seu `AGENTS.md` — não substitua o seu inteiro.

Depois disso, no Passo 2 você abre a ferramenta **na pasta do seu projeto**, não numa pasta `cohort-vendas`.

## Passo 1C — Sem git (caminho do ZIP)

1. Acesse **[github.com/marketingLendario/cohort-vendas](https://github.com/marketingLendario/cohort-vendas)**.
2. Clique no botão verde **Code** → **Download ZIP**.
3. Extraia o arquivo (botão direito → Extrair tudo / Descompactar).
4. Renomeie a pasta extraída de `cohort-vendas-main` para `cohort-vendas` (opcional, mas evita confusão).
5. **Cenário 2 (projeto existente):** arraste **quatro** coisas pra dentro do seu projeto:
   - a pasta `skills` de dentro de `.claude` → pra dentro do `.claude` do seu projeto
   - a pasta `skills` de dentro de `.agents` → pra dentro do `.agents` do seu projeto
   - a pasta `templates` inteira → pra raiz do seu projeto (**sem ela a Central de Entregas nunca aparece**)
   - a pasta `squads` inteira → pra raiz do seu projeto (**sem ela a Skill 8 não tem o que ler**)

   Se `.claude` e `.agents` não existirem no seu projeto, crie primeiro.

⚠️ **`.claude` e `.agents` começam com ponto — são pastas ocultas.** No Windows: aba **Exibir** → marque **Itens ocultos**. No Mac: **Command + Shift + .** (ponto) no Finder.

## Passo 2 — Abrir a ferramenta DENTRO da pasta

Esta é a causa quase certa do erro "No commands match". Faça a checagem antes de abrir qualquer coisa:

```bash
ls .claude/skills
```

**Resposta esperada** — 11 pastas. Elas vêm em ordem alfabética, não na ordem da aula:

```
desenho-processo-comercial
diagnostico-gargalos-funil
discovery-script
escada-de-ofertas
lead-scoring-ia
montagem-higiene-crm
playbook-vendas-vivo
qualificacao-bant-gpct
regua-comunicacao-comercial
social-selling-comercial
squad-sales-bonus
```

**Por que 11 e não 7:** são as 7 skills numeradas da Aula 1, mais o bônus `squad-sales-bonus` (que a Central da Aula 1 mostra como card 8), mais as 3 skills da Aula 2 (`montagem-higiene-crm`, `lead-scoring-ia`, `diagnostico-gargalos-funil`). Todas ficam disponíveis desde o primeiro dia — você roda na ordem da aula, não na ordem do `ls`.

Apareceram? Você está no lugar certo. Deu erro de pasta não encontrada? Falta o `cd` — volte ao Passo 1. Apareceram só 7 (sem `montagem-higiene-crm` nem `squad-sales-bonus`)? Seu clone é anterior à Aula 2 — rode `git pull`.

**Agora abra:**

| Ferramenta | Como |
|---|---|
| Claude Code (terminal) | digite `claude` e Enter |
| Claude Desktop | abra o app → aba **Code** → abra a pasta `cohort-vendas` |
| Codex | digite `codex` e Enter |
| VS Code | `code .` (ou abra a pasta pelo menu) e use o terminal embutido |

As 11 skills carregam **sozinhas**. Não existe passo de instalação separado.

## Passo 3 — Rodar a primeira skill

Digite:

```
/desenho-processo-comercial
```

Se a sua ferramenta usa `@` no lugar de `/`, use `@desenho-processo-comercial`. No Codex, você também pode pedir em português: *"quero desenhar meu processo comercial"*.

A skill vai se anunciar (*"Você está na Skill 1/7 (Processo Comercial)"*) e começar perguntando se você já tem o offerbook do Cohort de Marketing. Esse `1/7` conta só a Aula 1 — o bônus e as 3 skills da Aula 2 têm numeração própria. Se você já está na Aula 2, a porta de entrada é `/montagem-higiene-crm`, que se anuncia como `1/3`. As respostas que ela vai pedir estão preparadas em [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) — vale abrir antes.

⚠️ **A ordem certa:** baixar → `cd` pra dentro → conferir `ls .claude/skills` → abrir a ferramenta → só então rodar a skill. Trocar a ordem é o que gera 90% dos "não funciona".

## Teste de sucesso

Com a ferramenta aberta, digite `/desenho-processo-comercial` e aperte Enter.

**Funcionou se:** aparece uma mensagem dizendo que você está na **Skill 1/7 (Processo Comercial)** e ela começa a te fazer perguntas (a primeira é sobre o offerbook do Cohort de Marketing).

**Não funcionou se:** aparece `No commands match`, "Unknown skill" ou silêncio. Vá para o `R6` abaixo.

**Veio pelo Passo 1B ou 1C?** Some mais uma checagem, antes de rodar qualquer skill:

```bash
ls .claude/skills .agents/skills templates squads
```

**Passou se:** as quatro respondem. Se `templates` ou `squads` der "pasta não encontrada", a skill até roda — mas a Central de Entregas não vai nascer (`R10`) e a Skill 8 não vai ter o que ler (`R11`). Volte e copie as duas.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| R1 | `git: command not found` / `'git' não é reconhecido` | git não instalado | 1) instale em [git-scm.com](https://git-scm.com) 2) feche o terminal e abra de novo 3) `git --version` 4) se não quiser instalar, use o **Passo 1C** (ZIP) |
| R2 | `fatal: destination path 'cohort-vendas' already exists and is not an empty directory` | Você já clonou antes, ou já existe uma pasta com esse nome ali | 1) `ls cohort-vendas` pra ver o que tem dentro 2) se for o projeto de antes e você só quer atualizar: `cd cohort-vendas` e `git pull` 3) se for pasta vazia ou lixo: apague (`rm -rf cohort-vendas` no Mac/Linux, ou pelo Explorador no Windows) e clone de novo 4) alternativa sem apagar nada: `git clone <url> cohort-vendas-2` |
| R3 | Clonei, mas o `ls` não mostra o projeto | Você clonou numa pasta e está olhando outra | 1) `pwd` 2) `ls` 3) se a pasta `cohort-vendas` aparecer, rode `cd cohort-vendas` — o clone **não** te coloca dentro dela automaticamente |
| R4 | O clone pede usuário e senha do GitHub | Você digitou a URL errada (`git@github.com:...`) ou o repositório é privado pra você | 1) confira que a URL começa com `https://` 2) se pedir senha mesmo assim, o GitHub não aceita mais senha comum — use o **Passo 1C** (ZIP) |
| R5 | Baixei o ZIP mas não vejo as pastas `.claude` e `.agents` | São pastas ocultas (começam com ponto) | Windows: aba **Exibir** → **Itens ocultos**. Mac: **Command + Shift + .** no Finder |
| R6 | `No commands match` / "Unknown skill" ao digitar `/desenho-processo-comercial` | **Causa quase certa:** a ferramenta foi aberta um nível acima da pasta certa | 1) saia da ferramenta 2) rode `ls .claude/skills` — se der erro, falta o `cd` 3) `cd cohort-vendas` (ou a pasta do seu projeto) 4) confira o `ls` de novo 5) abra a ferramenta e tente outra vez 6) se as pastas aparecem no `ls` e mesmo assim não funciona, digite o nome completo e aperte Enter mesmo sem autocompletar ([issue conhecida](https://github.com/anthropics/claude-code/issues/58556)) 7) atualize a ferramenta pra última versão |
| R7 | Clonei dentro da pasta errada (ex.: na raiz do disco, ou dentro de outro projeto) | Faltou o `pwd` antes do clone | 1) `cd` até onde ela foi parar 2) mova a pasta pelo Explorador/Finder pro lugar certo 3) ou simplesmente apague e refaça o Passo 1A com o `pwd` antes |
| R8 | Copiei as skills pro meu projeto (Cenário 2) mas o Codex não as encontra | O `AGENTS.md` do repo não foi copiado, ou seu `AGENTS.md` foi sobrescrito | copie o `AGENTS.md` deste repo e cole o conteúdo **no final** do seu, sem apagar o que já estava lá |
| R9 | No Passo 1B o PowerShell reclamou: `mkdir : Não é possível localizar um parâmetro` / `cp` ou `rm` não reconhecido / `/tmp` não existe | Você colou o bloco de Mac/Linux dentro do PowerShell | use o **bloco PowerShell** do Passo 1B (`New-Item`, `Copy-Item`, `Remove-Item`, `$env:TEMP`). Se preferir os comandos de Mac/Linux no Windows, rode-os dentro do **Git Bash** (instalado junto com o [Git for Windows](https://git-scm.com/downloads/win)), não no PowerShell |
| R10 | Rodei a skill até o fim, ela disse que atualizou a Central de Entregas, mas **não existe nenhum `central-de-entregas.html`** na raiz do meu projeto | No Passo 1B/1C você copiou só as pastas de skills e **esqueceu a pasta `templates/`**. Nenhuma skill cria o painel do zero: ela copia de `templates/central-de-entregas.html`. Sem o arquivo de origem, não há o que copiar | 1) `ls templates` — se der erro de pasta não encontrada, é isso mesmo 2) copie a pasta `templates` do repo pra raiz do seu projeto (bloco do Passo 1B) 3) peça pra IA: *"atualize a Central de Entregas com o que eu já rodei"* — ela refaz o painel sem você repetir as skills 4) no Cenário 1 (projeto novo) isso não acontece: o clone já traz tudo |
| R11 | Digitei `/squad-sales-bonus` e a skill respondeu que **não encontrou os arquivos das mentes** / entregou conselho genérico sem citar framework nenhum | Falta a pasta `squads/`. Essa skill não tem os frameworks dentro dela — lê em tempo de execução de `squads/squad-sales/agents/` e `squads/squad-sales/tasks/` | 1) `ls squads/squad-sales/agents` — se der erro, é isso 2) copie a pasta `squads` do repo pra raiz do seu projeto 3) rode a skill de novo |
| R12 | O `ls .claude/skills` mostra **só 7 pastas** — não vejo `montagem-higiene-crm`, `lead-scoring-ia`, `diagnostico-gargalos-funil` nem `squad-sales-bonus` | Seu clone é anterior à Aula 2 | 1) `cd` pra pasta do projeto 2) `git pull` 3) `ls .claude/skills` de novo — tem que dar 11 4) baixou por ZIP? Baixe o ZIP outra vez, ele não se atualiza sozinho |

**Se nada resolver:** print da tela inteira (terminal com o comando e a resposta) no grupo do cohort, ou cole numa conversa com a IA: *"estou tentando rodar a skill e aparece isto: [print]. Me guie passo a passo a partir daqui."*

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | rode `/desenho-processo-comercial` — mas antes, escolha o modelo e prepare as respostas |
| 📖 Ler | [guia-modelo-e-custo.md](guia-modelo-e-custo.md) — qual modelo usar em cada etapa e o que gasta (leia **antes** de rodar a primeira skill) |
| 📖 Ler | depois: [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) — as 8 perguntas que a Skill 1 vai fazer · e [guia-mapa-das-skills.md](../04-operacao/guia-mapa-das-skills.md) pro mapa da aula inteira |
| 🚑 Se travar | o catálogo R1–R12 acima |
