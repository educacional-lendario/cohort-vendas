# GUIA ENTREGÁVEIS E CENTRAL — onde ficam os arquivos e como acompanhar o progresso

> **Estou perdido em:** "a skill terminou e disse que entregou dois arquivos… onde eles estão? O HTML não abriu. E o que é essa Central de Entregas?".
> **O que você vai ter no final:** saber exatamente onde cada arquivo mora, como abrir o HTML na mão quando ele não abre sozinho, e como usar a Central de Entregas pra ver em 3 segundos o que já foi feito e o que falta.
> **Fontes cruzadas:** o `templates/central-de-entregas.html` deste repo (o array `ENTREGAS` e como cada skill edita só a própria linha) · o `AGENTS.md` (regra da saída dupla e do comando de abrir por sistema operacional) · o Passo final de cada um dos 7 `SKILL.md` · a Aula 1 ao vivo, onde a Central nasceu na tela e a professora fechou dizendo *"está tudo aqui"* · documentação de suporte da Microsoft e da Apple sobre trocar o aplicativo padrão de um tipo de arquivo (consultada em 03/08/2026).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📄 Artefato | Pelo menos uma skill rodada até o fim | rode `/desenho-processo-comercial` — veja [guia-mapa-das-skills.md](guia-mapa-das-skills.md) |
| 📖 Conhecimento | Saber usar `ls` e `pwd` no terminal | leia [guia-terminal-e-pastas.md](../01-pre-requisitos/guia-terminal-e-pastas.md) |

## A regra da saída dupla

Toda skill desta aula entrega **dois arquivos com o mesmo conteúdo**, nunca só um:

| Extensão | Pra quem | Serve pra |
|---|---|---|
| `.md` | pra IA (e pra você editar) | as skills seguintes leem daqui; é texto puro, abre em qualquer editor |
| `.html` | pra humano | você abre no navegador e **manda pro seu time sem precisar explicar nada** |

Regra do `AGENTS.md`: *"Toda entrega sai em dois arquivos — nunca só um."*

## Os 7 pares de arquivos

Todos ficam na **raiz da pasta do projeto** (a mesma em que você abriu a ferramenta), não em subpasta:

| Skill | Arquivos |
|---|---|
| 1 · Processo Comercial | `processo-comercial-{negocio}.md` + `.html` |
| 2 · Régua de Comunicação | `regua-comunicacao-{negocio}.md` + `.html` |
| 3 · Qualificação | `qualificacao-{negocio}.md` + `.html` |
| 4 · Discovery Script | `discovery-script-{negocio}.md` + `.html` |
| 5 · Playbook de Objeções | `playbook-objecoes-{negocio}.md` + `.html` |
| 6 · Escada de Ofertas (bônus) | `escada-de-ofertas-{negocio}.md` + `.html` |
| 7 · Social Selling (bônus) | `social-selling-{negocio}.md` + `.html` |
| — | `central-de-entregas.html` (nasce sozinho na primeira skill) |

`{negocio}` é substituído pelo nome do seu negócio. Pra listar tudo:

```bash
ls *.md *.html
```

## A Central de Entregas

### O que é

Um painel que nasce sozinho na raiz do seu projeto assim que a **primeira** skill termina. Ele mostra 7 cards — um por skill — com barra de progresso.

| Card | Significa |
|---|---|
| **Aceso**, badge "Pronto", com dois links (Abrir HTML / Abrir MD) | aquela skill já entregou |
| **Apagado**, badge "Pendente", "Aguardando /comando" | ainda não rodou |

Da Aula 1, quando ela apareceu na tela:

> *"Como a gente vai rodar sete skills, ele está nutrindo uma central de entregas… Eu fiz essa central que vai facilitar pra gente entender o que a gente está fazendo."*

### Como abrir

```bash
open central-de-entregas.html      # macOS
start central-de-entregas.html     # Windows
xdg-open central-de-entregas.html  # Linux
```

Ou simplesmente dê dois cliques no arquivo pelo Explorador/Finder.

### Como ela se atualiza

Cada skill, ao terminar, copia o template `templates/central-de-entregas.html` pra raiz do projeto (só na primeira vez) e edita **apenas a própria linha** do array `ENTREGAS` lá dentro — trocando `status: "pendente"` por `status: "pronto"` e preenchendo os nomes reais dos arquivos.

⚠️ **É por isso que o progresso não se perde entre skills:** cada uma mexe só na sua linha.

⚠️ **Não edite esse arquivo na mão.** Se você mexer na estrutura do array, as skills seguintes podem não achar a linha delas.

## Quando o HTML não abre sozinho

As skills tentam abrir (`open` no Mac, `start` no Windows, `xdg-open` no Linux). Quando o comando falha — ambiente sem interface gráfica, sandbox restrito, permissão bloqueada — o `AGENTS.md` manda a skill **avisar o caminho exato** em vez de terminar em silêncio.

Se acontecer com você, três caminhos:

**1. Abrir na mão pelo terminal:**
```bash
open processo-comercial-minhaempresa.html      # Mac
start processo-comercial-minhaempresa.html     # Windows
xdg-open processo-comercial-minhaempresa.html  # Linux
```

**2. Pelo Explorador/Finder:** navegue até a pasta do projeto e dê dois cliques no arquivo. Se ele abrir num editor de código em vez do navegador: botão direito → **Abrir com** → seu navegador.

**3. Arrastar pro navegador:** abra o Chrome/Edge/Safari e arraste o arquivo pra dentro da janela.

**Não sabe o caminho da pasta?** No terminal, na pasta do projeto:
```bash
pwd
```

## O que fazer com os arquivos depois

| Arquivo | O que fazer com ele |
|---|---|
| `.html` de qualquer skill | mande pro seu time / sócio. Ele se explica sozinho, sem você precisar apresentar |
| `discovery-script-*.html` | deixe **aberto durante a call** — ele tem botão "Copiar" em cada mensagem, pra colar direto no WhatsApp/e-mail |
| `playbook-objecoes-*.html` | o battlecard das 5 objeções mais frequentes fica no topo — consulte antes de call difícil |
| `.md` de qualquer skill | é o que as skills seguintes leem. **Não apague, não renomeie** |
| `central-de-entregas.html` | abra a qualquer momento pra ver onde você parou |

## Fazer backup (2 minutos, vale a pena)

Esses documentos são o resultado da aula inteira. Duas formas:

**Simples:** copie a pasta do projeto pro Google Drive / OneDrive / Dropbox.

**Com git** (se você clonou o repo):
```bash
git add .
git commit -m "meus entregáveis da Aula 1"
```
Isso salva localmente. Não faça `git push` no repositório do cohort — os seus documentos são seus.

⚠️ **Gravações de call NÃO vão junto.** O `.gitignore` já bloqueia `*.mp3`, `*.mp4`, `*.vtt`, `*.srt` e a pasta `/calls-privadas/`. Veja [guia-insumos-reais.md](../03-insumos/guia-insumos-reais.md).

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Não acho meus arquivos** | "Liste todos os arquivos `.md` e `.html` desta pasta e me diga quais são entregáveis das 7 skills da Aula 1 e o que está faltando." |
| **A Central sumiu ou está desatualizada** | "Confira quais entregáveis da Aula 1 existem nesta pasta. Se o `central-de-entregas.html` não existir, copie de `templates/central-de-entregas.html` pra raiz. Depois marque como `pronto` só as linhas das skills cujos arquivos realmente existem, com os nomes reais. Não mexa nas outras linhas." |
| **Saiu só o `.md`, faltou o `.html`** | "Gere o `.html` correspondente ao `[nome].md`, com o mesmo conteúdo e os mesmos tokens visuais do `GUIA-DO-ALUNO.html` (fundo `#0A0A0A`, texto `#E5E5E5`, destaque `#C9B298`)." |
| **Editei o `.md` na mão** | "Eu editei o `[nome].md` manualmente. Atualize o `.html` correspondente pra ficar igual, sem mudar mais nada." |

## Teste de sucesso

No terminal, na pasta do projeto:

```bash
ls *.html
```

**Funcionou se:** aparece o `central-de-entregas.html` **mais** um `.html` para cada skill que você rodou. Abra a Central: a barra de progresso e o texto "X de 7 entregues" devem bater com a quantidade de skills que você rodou de verdade.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| EN1 | A skill disse que entregou, mas eu não acho os arquivos | Você está olhando outra pasta | 1) no terminal, `pwd` 2) `ls *.md` 3) se não aparecer, você abriu a ferramenta numa pasta e está procurando em outra — veja `R6` do [guia-baixar-e-abrir-o-projeto.md](../01-pre-requisitos/guia-baixar-e-abrir-o-projeto.md) |
| EN2 | O HTML não abriu sozinho | Comando de abrir falhou no seu ambiente (comportamento previsto) | abra na mão pelos 3 caminhos da seção acima. Não é sinal de que a entrega falhou |
| EN3 | O HTML abriu num editor de código, todo cheio de `<div>` | Associação de arquivo do sistema aponta pro editor, não pro navegador | **Windows:** botão direito → **Abrir com** → **Escolher outro aplicativo** → seu navegador → marque *"Sempre usar este aplicativo"*. Ou: **Configurações → Aplicativos → Aplicativos padrão**. · **macOS:** botão direito → **Abrir Com** → **Outro…** → escolha o navegador (marque *Sempre Abrir Com*). · **Solução de 2 segundos, sem mexer em configuração:** abra o navegador e **arraste o arquivo** pra dentro da janela |
| EN4 | O `central-de-entregas.html` não existe | Nenhuma skill terminou ainda, **ou** você está na pasta errada | 1) `ls` 2) se nenhum entregável está lá, nenhuma skill completou 3) se os `.md` estão lá mas a central não, peça: *"copie `templates/central-de-entregas.html` pra raiz e marque as skills já entregues"* |
| EN5 | A Central mostra "0 de 7" mesmo eu tendo rodado 3 skills | O arquivo foi copiado mas as linhas não foram atualizadas, ou você tem duas cópias em pastas diferentes | 1) confirme com `ls *.md` quais entregas existem 2) peça: *"atualize o `central-de-entregas.html` marcando como pronto as skills cujos arquivos existem nesta pasta"* |
| EN6 | Os links da Central não abrem os documentos | Os arquivos foram renomeados ou movidos depois | os links usam o nome que estava lá quando a skill terminou. Se renomeou, peça pra corrigir a linha da Central — ou renomeie de volta |
| EN7 | Só saiu o `.md`, o `.html` não foi gerado | A skill foi interrompida (erro de API, ou você fechou no meio) | peça: *"gere o `.html` correspondente ao `x.md`, com os mesmos tokens visuais do `GUIA-DO-ALUNO.html`"* |
| EN8 | Apaguei um `.md` sem querer e a próxima skill não acha o contexto | O `.md` é o que as skills seguintes leem | 1) veja se está na lixeira 2) se você tinha commitado: `git checkout -- arquivo.md` 3) senão, rode aquela skill de novo |
| EN9 | Editei a Central na mão e agora ela não carrega nada | A estrutura do array `ENTREGAS` foi quebrada | 1) apague o `central-de-entregas.html` da raiz 2) peça a qualquer skill pra recriar a partir de `templates/central-de-entregas.html` 3) não edite mais na mão |

**Se nada resolver:** rode `ls -la` na pasta e cole o resultado numa conversa com a IA, perguntando *"quais entregáveis da Aula 1 existem aqui e o que está faltando?"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | abra o `central-de-entregas.html` e rode a próxima skill que estiver apagada |
| 📖 Ler | [guia-e-depois.md](../05-depois/guia-e-depois.md) — o que fazer com esse pacote na segunda-feira |
| 🚑 Se travar | o catálogo EN1–EN9 acima |
