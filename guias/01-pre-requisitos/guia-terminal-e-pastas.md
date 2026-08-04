# GUIA TERMINAL E PASTAS — a telinha preta, sem medo, em 10 minutos

> **Estou perdido em:** "me mandaram abrir o terminal e digitar um comando… eu não faço ideia do que é isso".
> **O que você vai ter no final:** o terminal aberto **dentro da pasta certa**, sabendo dizer em que pasta você está e como andar entre elas. É o chão de tudo que vem depois.
> **Fontes cruzadas:** o `README.md` deste repo (seção "Setup em 5 minutos", que assume terminal aberto na pasta certa) · a Aula 1 ao vivo, onde a professora errou a pasta duas vezes seguidas e mostrou como percebeu · a página oficial de setup do Claude Code (consultada em 03/08/2026), de onde vem a distinção literal entre PowerShell e CMD pelo prompt (`PS C:\` × `C:\`).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 🧰 Ferramenta | Um computador com Windows, macOS ou Linux | Nenhum — este é um guia de entrada |

Nenhum outro. **Este é um guia de entrada:** se você nunca abriu um terminal na vida, é aqui que se começa.

## O que é isso tudo, em 3 analogias

| Coisa | O que é de verdade |
|---|---|
| **Pasta** (ou "diretório") | Igual à pasta do Windows Explorer / Finder. A mesma coisa, só que vista por texto. |
| **Caminho** (ex.: `C:\Users\Ana\Documentos\cohort-vendas`) | O endereço completo da pasta. Como CEP + rua + número. |
| **Terminal** | Uma janela onde você conversa com o computador digitando, em vez de clicando. Ele está **sempre parado dentro de uma pasta** — e é isso que quase todo mundo esquece. |

⚠️ **A regra que resolve a maior parte dos problemas:** o terminal só enxerga o que está na pasta em que ele está parado. Se você pedir uma coisa que está em outra pasta, ele responde "não achei" — e não é bug, é endereço errado.

## Passo 1 — Abrir o terminal

**No Windows:**
1. Aperte a tecla **Windows**.
2. Digite `powershell`.
3. Clique em **Windows PowerShell**.

Vai abrir uma janela azul ou preta com uma linha tipo `PS C:\Users\SeuNome>`. Essa linha final (`C:\Users\SeuNome`) é a pasta onde você está agora.

**No macOS:**
1. Aperte **Command (⌘) + Espaço**.
2. Digite `terminal`.
3. Aperte **Enter**.

Vai abrir uma janela com algo como `SeuNome@MacBook ~ %`. O `~` significa "minha pasta pessoal".

**No Linux:** **Ctrl + Alt + T** na maioria das distribuições.

## Passo 2 — Descobrir em que pasta você está

Digite e aperte Enter:

```bash
pwd
```

Ele responde o caminho completo. Exemplo de resposta:

```
C:\Users\Ana
```

Guarde esse hábito: **sempre que algo der errado, o primeiro comando é `pwd`.** Metade das vezes o problema é só que você está na pasta errada.

## Passo 3 — Ver o que tem na pasta

```bash
ls
```

Ele lista o que existe ali (pastas e arquivos). No PowerShell antigo, se `ls` não funcionar, use `dir` — faz a mesma coisa.

## Passo 4 — Andar entre as pastas (`cd`)

`cd` quer dizer *change directory*, "mudar de pasta".

| Quero… | Digite |
|---|---|
| Entrar na pasta `Documentos` | `cd Documentos` |
| Voltar uma pasta pra trás | `cd ..` |
| Ir direto pra um endereço completo | `cd "C:\Users\Ana\Documentos"` |
| Voltar pra minha pasta pessoal | `cd ~` (Mac/Linux) ou `cd $HOME` (Windows) |

**Sempre use aspas quando o caminho tiver espaço ou acento.** `cd "Meus Documentos"` funciona; `cd Meus Documentos` não.

## Passo 5 — O atalho que evita digitar caminho na mão

Digitar caminho longo é onde todo mundo erra. Faça assim:

**Windows:**
1. Abra o Explorador de Arquivos e navegue até a pasta que você quer.
2. Clique na barra de endereço lá em cima e copie o caminho (**Ctrl + C**).
3. No terminal, digite `cd ` (com o espaço), cole (**Ctrl + V**) e aperte Enter.

Atalho ainda melhor: com a pasta aberta no Explorador, digite `powershell` na barra de endereço e aperte Enter — abre o terminal **já dentro dela**.

**macOS:**
1. Digite `cd ` (com o espaço) no terminal.
2. **Arraste a pasta** do Finder pra dentro da janela do terminal. O caminho aparece sozinho.
3. Enter.

Atalho: clique com o botão direito na pasta no Finder → **Serviços** → **Novo Terminal na Pasta**.

## Passo 6 — Criar uma pasta pro seu projeto

Escolha um lugar que você vai lembrar (Documentos é uma boa) e crie:

```bash
cd Documentos
mkdir projetos-ia
cd projetos-ia
pwd
```

Agora você tem uma pasta sua, está dentro dela, e sabe o endereço dela. É exatamente daqui que o próximo guia continua.

## Teste de sucesso

Rode os dois comandos em sequência:

```bash
pwd
ls
```

**Funcionou se:** o `pwd` mostra um caminho que termina no nome da pasta que você acabou de criar (ex.: `...\Documentos\projetos-ia`), e o `ls` não dá erro (pode não mostrar nada — a pasta está vazia mesmo, isso está certo).

**Não funcionou se:** o `pwd` mostra outro lugar. Volte ao Passo 4.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| W1 | `cd: no such file or directory` / `Não foi possível localizar o caminho` | O nome está errado, ou você não está na pasta que contém aquela subpasta | 1) rode `pwd` pra ver onde está 2) rode `ls` pra ver os nomes reais 3) copie o nome exato da listagem (maiúscula/minúscula importam no Mac e Linux) 4) se o caminho tem espaço ou acento, ponha entre aspas |
| W2 | Digitei o caminho com espaço e ele reclamou | Terminal quebra o comando no espaço | use aspas: `cd "Meus Documentos"` |
| W3 | Digitei a senha e não aparece nada na tela | Comportamento normal e proposital do terminal (senha nunca aparece) | digite normalmente, mesmo sem ver, e aperte Enter |
| W4 | O terminal "travou" e não aceita mais nada | Algum comando ainda está rodando | 1) espere (comandos de download demoram) 2) se realmente travou, aperte **Ctrl + C** pra cancelar 3) em último caso, feche a janela e abra de novo |
| W5 | Fechei o terminal sem querer e perdi tudo | Nada foi perdido: o que você faz fica **nos arquivos**, não na janela | abra o terminal de novo, rode `cd` até a pasta do projeto e continue de onde parou |
| W6 | Estou com 5 janelas/abas abertas e não sei mais qual é qual | O problema mais comum de todos (levantado ao vivo na Aula 1) | 1) rode `pwd` em cada uma pra identificar 2) feche as que não são a do projeto 3) trabalhe com UMA aba só — se quiser ver as pastas ao mesmo tempo, o Claude Desktop resolve isso melhor (veja o próximo guia) |
| W7 | `'ls' não é reconhecido como um comando interno ou externo` | Você está no **Prompt de Comando (CMD)**, não no PowerShell — no PowerShell o `ls` funciona normalmente | 1) confira o prompt: PowerShell começa com `PS C:\`, o CMD é só `C:\` 2) abra o **PowerShell** (tecla Windows → digite `powershell`) 3) ou, se quiser continuar no CMD, use `dir` no lugar de `ls` |

**Se nada resolver:** tire um print da janela inteira (com a mensagem de erro visível) e mande no grupo do cohort, ou cole o print numa conversa com o Claude/Codex pedindo *"me guie passo a passo a partir daqui"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | crie a pasta do projeto (Passo 6) e deixe o terminal aberto nela |
| 📖 Ler | [guia-instalar-e-escolher-ferramenta.md](guia-instalar-e-escolher-ferramenta.md) — escolher entre Claude Code no terminal, Claude Desktop ou Codex |
| 🚑 Se travar | o catálogo W1–W7 acima |
