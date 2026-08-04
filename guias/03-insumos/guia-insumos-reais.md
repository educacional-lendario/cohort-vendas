# GUIA INSUMOS REAIS — gravar calls, levantar objeções e usar o que você já tem

> **Estou perdido em:** "a skill pediu gravação de call, objeções reais e o processo que eu já uso. Eu não tenho nada disso organizado — e não sei nem como gravar uma reunião".
> **O que você vai ter no final:** as calls sendo gravadas e transcritas a partir de hoje, uma lista de objeções reais levantada em 20 minutos, e o material que você já tem no formato que as skills conseguem ler.
> **Fontes cruzadas:** os `SKILL.md` da `/discovery-script` (Passo 1B, refino com calls reais) e da `/playbook-vendas-vivo` (Passo 0, os 3 modos de alimentar o playbook) · o `.gitignore` deste repo, que já bloqueia gravações de aluno (`*.vtt`, `*.mp3`, `*.mp4`, `/calls-privadas/`) · a Aula 1 ao vivo (a história do vendedor que não gravou 10 reuniões) · a documentação oficial de transcrição do Google Meet e alternativas gratuitas.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber o que é discovery, objeção e os 6 tipos | leia [guia-bant-gpct-spin.md](../02-conhecimento-minimo/guia-bant-gpct-spin.md) |
| 🔑 Conta/acesso | Uma ferramenta de reunião (Meet, Zoom, Teams) ou o WhatsApp | qualquer uma serve — o Passo 1 cobre as três |

## Por que isso é o segundo insumo mais importante da aula

As três skills que mais dependem de material real:

| Skill | Sem material real | Com material real |
|---|---|---|
| `/discovery-script` (4) | monta o script do zero, pela teoria | **compara** o que o roteiro previa com o que a call teve: aponta qual bloco você pulou, se a dor virou número, e quem falou mais |
| `/playbook-vendas-vivo` (5) | rotula o resultado como *"ponto de partida a validar"* — objeções típicas do nicho, não as suas | usa as objeções que apareceram de verdade, nas palavras do cliente |
| `/regua-comunicacao-comercial` (2) | monta a régua pelo modelo de referência | adapta as mensagens que você **já usa e já convertem** |

Fala da aula, sobre rodar o playbook sem objeções reais:

> *"Se você usar as gravações das reuniões em que você conseguiu quebrar essas objeções, isso vai fazer com que fique uma resposta mil vezes melhor do que está aqui, porque ele está usando uma dor real, uma objeção real."*

## Parte 1 — Gravar e transcrever as calls

### A história que virou regra

> *"Eu tive um vendedor uma vez que ele simplesmente não gravou a reunião, e ele tinha feito umas dez reuniões. Era uma contratação nova, não falei o básico para ele. Eu quase tive um pequeno infarto."*
>
> *"Acreditem ou não, mas hoje ainda tem que falar o básico: meu querido vendedor, quando você for fazer uma reunião de vendas, coloque a IA pra gravar."*

⚠️ **Antes de qualquer coisa: avise que está gravando.** É exigência legal e ética em qualquer canal, e a maioria das ferramentas já avisa sozinha. Uma frase resolve: *"vou gravar nossa conversa só pra eu não perder nada e não ficar anotando, tudo bem pra você?"*.

### Passo 1.1 — Escolha como gravar

| Ferramenta | Como | Custo |
|---|---|---|
| **Google Meet** (nativo) | Durante a reunião: **Atividades** → **Transcrições** → **Iniciar transcrição**. O arquivo cai no Google Drive do organizador ao final | grátis, mas exige conta Workspace elegível e espaço no Drive |
| **Zoom** (nativo) | **Record** → **Record to the Cloud** (transcrição automática) ou **Record to this Computer** (só o áudio/vídeo) | transcrição na nuvem exige plano pago |
| **Extensão de navegador** (Tactiq, Scribbl) | Instale no Chrome, ela transcreve Meet/Zoom/Teams e salva num Google Doc ao final | plano gratuito costuma cobrir o essencial |
| **Só o celular** | Grave o áudio com o gravador do próprio telefone e transcreva depois | grátis, e funciona sem depender de plataforma nenhuma |

**Não tem nenhuma dessas?** Papel e caneta ainda vale. Da própria aula:

> *"Eu anotava, papel e caneta mesmo. Hoje eu sei que tem IA que pode assistir a sua reunião, mas é uma ferramenta cara pra quem está começando. Então papel e caneta também funciona."*

O que anotar, no mínimo: as **frases literais** do cliente sobre a dor, os números que ele citou, e cada objeção com as palavras dele.

### Passo 1.2 — Transcreva (se só tiver o áudio)

Se você gravou só o áudio, jogue o arquivo numa IA que aceite áudio e peça a transcrição, ou use uma ferramenta de transcrição. O formato final que as skills leem é **texto puro** — `.txt`, `.md`, `.vtt` ou `.srt`.

### Passo 1.3 — Guarde no lugar certo (e protegido)

Crie uma pasta na raiz do projeto:

```bash
mkdir calls-privadas
```

⚠️ **Esse nome não é aleatório.** O `.gitignore` deste repo já bloqueia, com um comentário explícito (*"Gravações e transcrições de calls reais de alunos — nunca vão pro repo"*):

```
*.vtt
*.srt
*.mp3
*.mp4
/calls-privadas/
```

Ou seja: se você salvar ali, o material do seu cliente **nunca** sobe pro GitHub por acidente.

### Passo 1.4 — Anonimize antes de usar

Antes de entregar a transcrição pra skill, troque o que identifica o cliente:

| Troque | Por |
|---|---|
| Nome da pessoa | `[CLIENTE]` |
| Nome da empresa | `[EMPRESA]` |
| CNPJ, telefone, e-mail | remova |
| Valores de contrato | mantenha se for relevante pro gap — é justamente o número que dá peso à dor |

Atalho: cole a transcrição na IA e peça *"anonimize esta transcrição, trocando nomes de pessoa e empresa por [CLIENTE] e [EMPRESA], mantendo os números de negócio"*.

### Passo 1.5 — Entregue pra skill

Ao rodar `/discovery-script`, ela pergunta como seguir. Escolha a opção 2 ou 3 e aponte o arquivo:

```
Quero refinar com calls reais. As transcrições estão em calls-privadas/call-01.txt e calls-privadas/call-02.txt
```

**Tem mais de uma call?** Melhor ainda. A skill compara e procura padrão: *"padrões que se repetem em 3+ calls são sinal de que o script precisa reforçar aquele bloco, não de que um vendedor específico está errado."*

### O que a skill vai olhar na sua call

Vale saber, porque é um diagnóstico duro e útil:

1. **Cobertura de blocos** — quais dos 6 blocos apareceram e quais você pulou. Pular de Situação direto pra proposta é o erro mais comum e mais caro.
2. **Qualidade da pergunta de implicação** — você perguntou "e daí?" depois do problema, ou aceitou o sintoma e seguiu?
3. **Presença de número** — o gap foi quantificado, ou ficou tudo em "é chato", "atrapalha"?
4. **Quem falou mais** — em discovery bem feito, **o comprador** fala a maior parte do tempo.
5. **Recomendação específica** — a pergunta exata que faltou, não um "aprofunde mais" genérico.

## Parte 2 — Levantar as objeções reais (20 minutos)

A Skill 5 oferece três modos. Este exercício resolve o modo 1 sem você ter gravação nenhuma.

### Passo 2.1 — Varra as suas conversas

Abra o WhatsApp Business, o e-mail e o CRM (se tiver) e procure as conversas com quem **não** comprou. Você está caçando frases literais.

### Passo 2.2 — Copie as frases, não o resumo

⚠️ **A regra que muda tudo:** copie **as palavras do cliente**, não a sua interpretação.

| ❌ Resumo seu | ✅ Frase dele |
|---|---|
| "achou caro" | *"esse valor tá bem acima do que a gente tinha reservado pra esse ano"* |
| "não confiou" | *"nunca ouvi falar de vocês, quem mais usa isso?"* |
| "queria pensar" | *"deixa eu conversar com meu sócio e te retorno na semana que vem"* |

A frase literal é o que permite à Skill 5 classificar o **tipo** certo — e "está caro" muitas vezes é confiança disfarçada de preço.

### Passo 2.3 — Anote o contexto de cada uma

Pra cada objeção, três linhas:

```
Objeção: "[frase literal do cliente]"
Em que momento apareceu: (na primeira conversa / depois da proposta / na hora de assinar)
O que eu respondi: (o que você falou, mesmo que tenha dado errado)
```

Cinco objeções já bastam pra tirar o playbook do modo "ponto de partida a validar".

### Passo 2.4 — Junte também os deals perdidos

Se você tem o registro de quem não fechou, o **motivo da perda** é matéria-prima direta. É por isso que a Skill 1 exige motivo categorizado na etapa Perdido.

## Parte 3 — O material que você já usa hoje

Três skills perguntam explicitamente por isso, e adaptam em vez de recriar. Levante antes:

| A skill pergunta | O que separar | Onde procurar |
|---|---|---|
| Skill 1: *"me manda o que você já tem"* | Os nomes das etapas do seu funil hoje (só os nomes já ajudam) | CRM, planilha, ou de cabeça mesmo |
| Skill 2: *"vocês já têm alguma mensagem ou script que usam hoje?"* | As mensagens que você manda de verdade: primeiro contato, follow-up, confirmação de reunião | WhatsApp (mensagens rápidas), rascunhos de e-mail |
| Skill 7: *"você já tem alguma abordagem que usa pra puxar conversa?"* | A mensagem de DM/LinkedIn que você usa hoje | histórico de DMs enviadas |

⚠️ **Não descarte o que já funciona.** O `SKILL.md` da Skill 2 é explícito: *"nunca descarte um texto que ele já usa só porque não segue o modelo de referência da skill — o modelo é ponto de partida para quem não tem nada, não substituição para quem já tem algo rodando."*

Se você não tem nada escrito, **descreva de cabeça**. Descrição verbal conta como fonte válida.

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Anonimizar antes de usar** | "Anonimize esta transcrição: troque nomes de pessoa por [CLIENTE] e nomes de empresa por [EMPRESA], remova telefone, e-mail e CNPJ, e **mantenha todos os números de negócio** (valores, quantidades, prazos). Devolva o texto limpo: [cole]" |
| **Extrair as objeções de uma conversa** | "Nesta conversa de WhatsApp/call, liste todas as objeções que o cliente levantou, usando **as palavras literais dele**. Para cada uma, diga em que momento apareceu e o que eu respondi: [cole]" |
| **Transformar áudio bagunçado em material usável** | "Esta transcrição está com nomes errados e frases picadas. Não corrija a ortografia — só me devolva: (1) as frases da dor, literais; (2) os números que ele citou; (3) as objeções; (4) quem mais decide. [cole]" |
| **Varrer meu WhatsApp atrás de objeção** | "Vou colar várias conversas com clientes que não fecharam. Extraia as objeções recorrentes, agrupe por tipo (preço, urgência, confiança, concorrente, autoridade, desalinhamento) e me diga qual aparece mais: [cole]" |
| **Levantar o que eu já uso hoje** | "Vou descrever de cabeça como eu vendo hoje e as mensagens que costumo mandar: [descreva de corrido]. Organize isso no formato que a skill `/regua-comunicacao-comercial` espera receber, pra eu colar lá sem ela ter que recriar do zero." |

## Teste de sucesso

Rode `/discovery-script` e escolha a opção **2 (refinar com calls reais)** apontando pelo menos uma transcrição.

**Funcionou se:** a análise dela cita **trechos reais da sua call** e diz coisas específicas do tipo *"o bloco 4 (implicação) não apareceu"* ou *"o gap não foi quantificado em nenhum momento"*. Se a análise for genérica, sem citar nada da sua conversa, ela não leu o arquivo — confira o caminho.

**Não tem call ainda?** O teste é a Parte 2: você tem 5 objeções escritas **com as palavras do cliente**, cada uma com momento e resposta? Então está pronto pra Skill 5.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| IR1 | "Não tenho call gravada nenhuma, sou obrigado a pular a Skill 4?" | Achar que é pré-requisito | não é. O Passo 0 da skill oferece 3 modos, e o modo 1 cria do zero. Rode agora e **rode de novo depois das primeiras reuniões** |
| IR2 | A transcrição está uma bagunça, com nomes trocados e frases picadas | Transcrição automática sempre erra nomes próprios | 1) não perca tempo corrigindo tudo 2) corrija só os nomes de produto/empresa que aparecem muito 3) o que importa pra skill é a **estrutura da conversa**, não a ortografia |
| IR3 | Dei o arquivo e a skill respondeu genérico, sem citar a call | Ela não leu — caminho errado, ou arquivo fora da pasta aberta | 1) confirme com `ls calls-privadas/` 2) dê o caminho relativo exato 3) em último caso, **cole o texto da transcrição direto na conversa** |
| IR4 | Medo de expor dado do cliente | Preocupação legítima | 1) anonimize (Passo 1.4) 2) salve em `calls-privadas/`, que o `.gitignore` já bloqueia 3) nunca commite gravação: `*.mp3`, `*.mp4`, `*.vtt`, `*.srt` já estão bloqueados |
| IR5 | Gravei mas o cliente não sabia | Problema legal e de confiança, não técnico | não use essa gravação como material. Avise a partir da próxima: *"vou gravar só pra eu não perder nada, tudo bem?"* |
| IR6 | A transcrição do Meet não apareceu no Drive | Sem espaço no Drive, ou a conta não tem o recurso liberado | 1) confira o espaço no Drive do organizador 2) se não tiver o recurso, use uma extensão de navegador (Tactiq/Scribbl) ou grave o áudio pelo celular |
| IR7 | Minhas objeções ficaram todas "está caro" | Você resumiu em vez de copiar a frase literal | volte às conversas e copie as palavras dele. "Está caro" pode ser preço, confiança **ou** urgência — só a frase inteira revela |
| IR8 | O playbook saiu marcado como "ponto de partida a validar" | Você rodou sem objeções reais (modo 2) | comportamento correto: é um aviso, não um erro. Levante 5 objeções reais (Parte 2) e rode de novo |
| IR9 | Rodei a Skill 2 e ela ignorou as mensagens que eu já uso | Você não colou o material quando ela perguntou | rode de novo colando as mensagens. Ela adapta em cima do que já converte, em vez de reescrever |

**Se nada resolver:** cole a transcrição direto na conversa (sem arquivo) e peça *"use este texto como a call real e rode a análise do Passo 1B"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | ligue a gravação na próxima reunião de vendas, e faça a varredura de objeções da Parte 2 (20 min) |
| 📖 Ler | [guia-mapa-das-skills.md](../04-operacao/guia-mapa-das-skills.md) — o mapa de todas as skills, na ordem |
| 🚑 Se travar | o catálogo IR1–IR9 acima |
