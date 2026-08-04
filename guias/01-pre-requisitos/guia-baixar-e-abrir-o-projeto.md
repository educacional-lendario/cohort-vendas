# GUIA BAIXAR E ABRIR O PROJETO — do `git clone` até a primeira skill respondendo

> **Estou perdido em:** "baixei o projeto (acho), abri a ferramenta, digitei `/desenho-processo-comercial` e apareceu **No commands match**".
> **O que você vai ter no final:** o projeto na sua máquina, a ferramenta aberta **dentro da pasta certa**, e a Skill 1 rodando de verdade.
> **Fontes cruzadas:** o `README.md` deste repo (Cenário 1 e Cenário 2 de instalação) · o `docs/SKILLS-INDEX.md` (FAQ de suporte: *"Digitei `/desenho-processo-comercial` e apareceu 'No commands match'"*) · a Aula 1 ao vivo, onde o clone falhou por pasta duplicada e depois por falta de `cd` · pesquisa web sobre o erro `destination path already exists`.

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
| Já tenho um projeto rodando e quero **só as 7 skills** dentro dele | **Passo 1B** |
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
   O `pwd` tem que terminar em `cohort-vendas`, e o `ls` tem que mostrar `README.md`, `AGENTS.md`, `GUIA-DO-ALUNO.html`, `docs`, `templates`, `exemplos`.

Vá para o **Passo 2**.

## Passo 1B — Já tenho um projeto, quero só as skills dentro dele

Não clone o repositório inteiro por cima do seu projeto. Clone numa pasta temporária, copie só as skills, e apague a temporária:

```bash
cd /caminho/do/seu/projeto
git clone https://github.com/marketingLendario/cohort-vendas.git /tmp/cohort-vendas-temp
mkdir -p .claude/skills .agents/skills
cp -R /tmp/cohort-vendas-temp/.claude/skills/. .claude/skills/
cp -R /tmp/cohort-vendas-temp/.agents/skills/. .agents/skills/
rm -rf /tmp/cohort-vendas-temp
```

⚠️ **Se você já tiver uma skill com o mesmo nome de alguma das 7, o comando sobrescreve só ela.** Revise antes se isso for um problema.

**Usa Codex?** Copie também o `AGENTS.md` deste repo e cole o conteúdo dele **no final** do seu `AGENTS.md` — não substitua o seu inteiro.

Depois disso, no Passo 2 você abre a ferramenta **na pasta do seu projeto**, não numa pasta `cohort-vendas`.

## Passo 1C — Sem git (caminho do ZIP)

1. Acesse **[github.com/marketingLendario/cohort-vendas](https://github.com/marketingLendario/cohort-vendas)**.
2. Clique no botão verde **Code** → **Download ZIP**.
3. Extraia o arquivo (botão direito → Extrair tudo / Descompactar).
4. Renomeie a pasta extraída de `cohort-vendas-main` para `cohort-vendas` (opcional, mas evita confusão).
5. **Cenário 2 (projeto existente):** arraste as pastas `skills` de dentro de `.claude` e `.agents` pra dentro das pastas `.claude` e `.agents` do seu projeto. Se essas duas pastas não existirem lá, crie primeiro.

⚠️ **`.claude` e `.agents` começam com ponto — são pastas ocultas.** No Windows: aba **Exibir** → marque **Itens ocultos**. No Mac: **Command + Shift + .** (ponto) no Finder.

## Passo 2 — Abrir a ferramenta DENTRO da pasta

Esta é a causa quase certa do erro "No commands match". Faça a checagem antes de abrir qualquer coisa:

```bash
ls .claude/skills
```

**Resposta esperada** — as 7 pastas:
```
desenho-processo-comercial
discovery-script
escada-de-ofertas
playbook-vendas-vivo
qualificacao-bant-gpct
regua-comunicacao-comercial
social-selling-comercial
```

Apareceram? Você está no lugar certo. Deu erro de pasta não encontrada? Falta o `cd` — volte ao Passo 1.

**Agora abra:**

| Ferramenta | Como |
|---|---|
| Claude Code (terminal) | digite `claude` e Enter |
| Claude Desktop | abra o app → aba **Code** → abra a pasta `cohort-vendas` |
| Codex | digite `codex` e Enter |
| VS Code | `code .` (ou abra a pasta pelo menu) e use o terminal embutido |

As 7 skills carregam **sozinhas**. Não existe passo de instalação separado.

## Passo 3 — Rodar a primeira skill

Digite:

```
/desenho-processo-comercial
```

Se a sua ferramenta usa `@` no lugar de `/`, use `@desenho-processo-comercial`. No Codex, você também pode pedir em português: *"quero desenhar meu processo comercial"*.

A skill vai se anunciar (*"Você está na Skill 1/7"*) e começar perguntando se você já tem o offerbook do Cohort de Marketing. As respostas que ela vai pedir estão preparadas em [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) — vale abrir antes.

⚠️ **A ordem certa:** baixar → `cd` pra dentro → conferir `ls .claude/skills` → abrir a ferramenta → só então rodar a skill. Trocar a ordem é o que gera 90% dos "não funciona".

## Teste de sucesso

Com a ferramenta aberta, digite `/desenho-processo-comercial` e aperte Enter.

**Funcionou se:** aparece uma mensagem dizendo que você está na **Skill 1/7 (Processo Comercial)** e ela começa a te fazer perguntas (a primeira é sobre o offerbook do Cohort de Marketing).

**Não funcionou se:** aparece `No commands match`, "Unknown skill" ou silêncio. Vá para o `R6` abaixo.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| R1 | `git: command not found` / `'git' não é reconhecido` | git não instalado | 1) instale em [git-scm.com](https://git-scm.com) 2) feche o terminal e abra de novo 3) `git --version` 4) se não quiser instalar, use o **Passo 1C** (ZIP) |
| R2 | `fatal: destination path 'cohort-vendas' already exists and is not an empty directory` | Você já clonou antes, ou já existe uma pasta com esse nome ali | 1) `ls cohort-vendas` pra ver o que tem dentro 2) se for o projeto de antes e você só quer atualizar: `cd cohort-vendas` e `git pull` 3) se for pasta vazia ou lixo: apague (`rm -rf cohort-vendas` no Mac/Linux, ou pelo Explorador no Windows) e clone de novo 4) alternativa sem apagar nada: `git clone <url> cohort-vendas-2` |
| R3 | Clonei, mas o `ls` não mostra o projeto | Você clonou numa pasta e está olhando outra | 1) `pwd` 2) `ls` 3) se a pasta `cohort-vendas` aparecer, rode `cd cohort-vendas` — o clone **não** te coloca dentro dela automaticamente |
| R4 | O clone pede usuário e senha do GitHub | Você digitou a URL errada (`git@github.com:...`) ou o repositório é privado pra você | 1) confira que a URL começa com `https://` 2) se pedir senha mesmo assim, o GitHub não aceita mais senha comum — use o **Passo 1C** (ZIP) |
| R5 | Baixei o ZIP mas não vejo as pastas `.claude` e `.agents` | São pastas ocultas (começam com ponto) | Windows: aba **Exibir** → **Itens ocultos**. Mac: **Command + Shift + .** no Finder |
| R6 | `No commands match` / "Unknown skill" ao digitar `/desenho-processo-comercial` | **Causa quase certa:** a ferramenta foi aberta um nível acima da pasta certa | 1) saia da ferramenta 2) rode `ls .claude/skills` — se der erro, falta o `cd` 3) `cd cohort-vendas` (ou a pasta do seu projeto) 4) confira o `ls` de novo 5) abra a ferramenta e tente outra vez 6) se as 7 pastas aparecem no `ls` e mesmo assim não funciona, digite o nome completo e aperte Enter mesmo sem autocompletar ([issue conhecida](https://github.com/anthropics/claude-code/issues/58556)) 7) atualize a ferramenta pra última versão |
| R7 | Clonei dentro da pasta errada (ex.: na raiz do disco, ou dentro de outro projeto) | Faltou o `pwd` antes do clone | 1) `cd` até onde ela foi parar 2) mova a pasta pelo Explorador/Finder pro lugar certo 3) ou simplesmente apague e refaça o Passo 1A com o `pwd` antes |
| R8 | Copiei as skills pro meu projeto (Cenário 2) mas o Codex não as encontra | O `AGENTS.md` do repo não foi copiado, ou seu `AGENTS.md` foi sobrescrito | copie o `AGENTS.md` deste repo e cole o conteúdo **no final** do seu, sem apagar o que já estava lá |

**Se nada resolver:** print da tela inteira (terminal com o comando e a resposta) no grupo do cohort, ou cole numa conversa com a IA: *"estou tentando rodar a skill e aparece isto: [print]. Me guie passo a passo a partir daqui."*

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | rode `/desenho-processo-comercial` — mas antes, prepare as respostas |
| 📖 Ler | [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) — as 8 perguntas que a Skill 1 vai fazer · e [guia-mapa-das-skills.md](../04-operacao/guia-mapa-das-skills.md) pro mapa da aula inteira |
| 🚑 Se travar | o catálogo R1–R8 acima |
