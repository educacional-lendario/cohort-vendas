# Cohort de Vendas: Aula 1 e Aula 2

> **Academia Lendária · Squad Vendas**
>
> Aula 1: Processo Comercial & Playbook com IA · Aula 2: CRM & Gestão de Pipeline com IA

Bem-vindo ao repositório do Cohort de Vendas. Este repo contém tudo o que você precisa para desenhar o processo comercial ponta a ponta, montar a régua de comunicação por etapa, calibrar a qualificação de leads, construir um playbook de objeções vivo (Aula 1), organizar o CRM em qualquer ferramenta, pontuar leads por critério objetivo e diagnosticar onde o funil vaza receita (Aula 2), com o Claude Code orquestrando a construção. Funciona para qualquer nicho, B2B ou B2C.

---

## Comece por aqui

**Antes de qualquer coisa, abra o guia visual da sua aula no navegador:**

👉 **[`GUIA-DO-ALUNO.html`](./GUIA-DO-ALUNO.html)**: guia da Aula 1, clica e abre.

👉 **[`GUIA-DO-ALUNO-AULA-2.html`](./GUIA-DO-ALUNO-AULA-2.html)**: guia da Aula 2, clica e abre.

Cada guia tem tudo que você precisa saber pra começar aquela aula (5 minutos de leitura).

**Travou em alguma coisa da Aula 1?** A pasta **[`guias/`](./guias/)** tem um guia por problema, do "nunca abri um terminal" até "terminei as skills, e agora?". Abra o [roteador](./guias/README.md), ache a linha "Estou perdido em..." mais parecida com o seu caso e siga.

**Se você se perder no meio de uma skill**, não sabe mais onde está, por que está fazendo aquilo, ou o que falta pra fechar o material, peça pra qualquer skill *"me mostra onde eu estou"*. Todas as 10 têm essa resposta pronta, com base no guia da aula correspondente.

Se preferir markdown puro, o conteúdo está abaixo.

---

## O que você ganha na Aula 1

7 skills para o Claude Code que constroem, em sequência, o esqueleto comercial do seu negócio (as 5 primeiras compõem o fluxo principal; as 2 últimas são bônus, para quem já tem mais de uma oferta ou prospecta por rede social):

| # | Skill | O que faz | Output |
|---|---|---|---|
| 1 | `/desenho-processo-comercial` | Diagnostica seu modelo de venda (ticket, ciclo, decisores, B2B/B2C, com vendedor ou autoatendimento, origem dos leads, nicho regulado ou não) e desenha as etapas do funil com critério de saída verificável (VCA) e gatilhos de risco em 2 níveis | `processo-comercial-{negocio}.md` + `.html` |
| 2 | `/regua-comunicacao-comercial` | Define quem fala (humano, IA ou os dois), o que dizer e por qual canal em cada etapa, com funil de reforço por tempo parado e o mecanismo único de conversão do seu negócio | `regua-comunicacao-{negocio}.md` + `.html` |
| 3 | `/qualificacao-bant-gpct` | Escolhe o mix certo entre BANT e GPCT para o seu tipo de venda, monta o ICP nas dimensões certas (B2B ou B2C) e gera o roteiro de qualificação com escala de pontuação consistente | `qualificacao-{negocio}.md` + `.html` |
| 4 | `/discovery-script` | Gera o script de discovery em 6 blocos modulares (SPIN + Funil de Dor + quantificação de gap), ou refina um script existente comparando com calls reais gravadas/transcritas | `discovery-script-{negocio}.md` + `.html` |
| 5 | `/playbook-vendas-vivo` | Classifica objeções em 6 tipos, gera resposta com o framework certo por tipo (D.E.E.P., Empatia Tática, Feel-Felt-Found) em todos os canais, e define a cadência que mantém o playbook vivo | `playbook-objecoes-{negocio}.md` + `.html` |
| 6 · bônus | `/escada-de-ofertas` | Desenha a jornada de ascensão entre produtos/ofertas diferentes (não confundir com o funil comercial, este é o funil de vendas do portfólio inteiro) | `escada-de-ofertas-{negocio}.md` + `.html` |
| 7 · bônus | `/social-selling-comercial` | Monta a sequência de prospecção direto pela rede social (LinkedIn para B2B, Instagram/TikTok para B2C/alto ticket pessoal), antes do lead entrar no funil comercial | `social-selling-{negocio}.md` + `.html` |

**Tese-mãe da Aula 1:** desenhar o processo, dar voz a ele com a régua de comunicação, calibrar a qualificação e construir o playbook, para o aluno sair com o problema comercial resolvido, não com mais um framework na cabeça. Toda entrega sai em markdown **e** HTML, organizada o suficiente pra não sobrar dúvida.

### Mentes por trás da aula

Cada skill credita explicitamente de onde tirou o método (ver seção "Mentes por trás desta skill" dentro de cada `SKILL.md`). No total, 9 mentes do squad interno de vendas (`squads/sales/`) e origens de mercado entram nesta aula:

| Mente | Framework | Onde aparece |
|---|---|---|
| Neil Rackham | SPIN Selling | Discovery Script |
| David Sandler | Sandler Selling System (Pain Funnel) | Discovery Script |
| Keenan | Gap Selling | Qualificação, Discovery Script |
| Chris Voss | Empatia Tática (Never Split the Difference) | Playbook de Objeções |
| Chet Holmes | Dream 100 + Stadium Pitch (Ultimate Sales Machine) | Processo Comercial, Escada de Ofertas |
| Jeb Blount | Fanatical Prospecting + Objections | Régua de Comunicação, Playbook de Objeções, Social Selling |
| Aaron Ross | Predictable Revenue (Seeds/Nets/Spears) | Processo Comercial, Régua de Comunicação |
| Challenger Sale (Dixon & Adamson) | Commercial Teaching | Discovery Script, Playbook de Objeções |
| Juliano Torriani | Social Selling 2.0 (funil de DM sem tráfego pago) | Social Selling |

Chet Holmes, Jeb Blount, Aaron Ross, Challenger Sale e Juliano Torriani entram aqui como reforço pontual, a aplicação mais profunda de prospecção e cadência é na **Aula 3 (FUPs, Cadência, SDR e Automação, com Adavio)**.

---

## O que você ganha na Aula 2

3 skills que recebem o pacote da Aula 1 e transformam em CRM real, pontuação de leads e diagnóstico de gargalo. Cada uma depende da anterior estar funcionando: não dá pra pontuar lead num CRM sujo, e não dá pra diagnosticar gargalo antes de organizar a base.

| # | Skill | O que faz | Output |
|---|---|---|---|
| 1 | `/montagem-higiene-crm` | Detecta qual ferramenta de CRM você usa (com API, sem API mas com login web, ou nenhuma formal, só planilha), traduz as etapas da Aula 1 pra estrutura real dela, e roda um checklist de 8 pontos de higiene (duplicidade, campo vazio, etapa sem critério de saída, card zumbi, motivo de perda, nomenclatura, origem não confiável, cobertura histórica) | `higiene-crm-{negocio}.md` + `.html` |
| 2 | `/lead-scoring-ia` | Converte a qualificação BANT/GPCT em 7 critérios de pontuação com pesos fixos por nível, ajustados pelo seu ticket e ciclo de venda, implantados aos poucos numa ordem testada | `lead-scoring-{negocio}.md` + `.html` |
| 3 | `/diagnostico-gargalos-funil` | Lê o CRM já organizado, calcula a conversão entre etapas, distingue o gargalo aparente da causa real, e projeta a receita em risco com uma calculadora interativa que recalcula ao vivo | `diagnostico-gargalos-{negocio}.md` + `.html` |

**Tese-mãe da Aula 2:** processo desenhado no papel não adianta nada se não vira estrutura real numa ferramenta, com dado limpo o suficiente pra confiar, pontuação objetiva pra priorizar quem atender primeiro, e um número real (não estimativa) de onde a receita está vazando. As 3 skills funcionam pra B2B e B2C, e nenhuma delas depende de uma ferramenta de CRM específica.

### Mentes por trás da Aula 2

As mesmas 6 mentes do squad interno de vendas, agora aplicadas a dado de CRM em vez de conversa de vendas:

| Mente | Framework | Onde aparece na Aula 2 |
|---|---|---|
| Aaron Ross | Predictable Revenue (Seeds/Nets/Spears) | Higiene de CRM, Lead Scoring |
| Chet Holmes | The Ultimate Sales Machine | Higiene de CRM, Diagnóstico de Gargalos |
| Neil Rackham | SPIN Selling (necessidade implícita vs explícita) | Lead Scoring |
| Keenan | Gap Selling | Lead Scoring |
| Jeb Blount | Sales EQ | Lead Scoring |
| David Sandler | Submarine System | Diagnóstico de Gargalos |

---

## Setup em 5 minutos

Primeira pergunta, antes de qualquer comando: **você vai começar um projeto do zero só pra isso, ou já tem um projeto rodando (Claude Code/Codex) e só quer as skills dentro dele?**

### Cenário 1: projeto novo (do zero)

```bash
git clone https://github.com/marketingLendario/cohort-vendas.git
cd cohort-vendas
```

Isso cria a pasta `cohort-vendas` com tudo dentro (as duas aulas). Vá direto pra "Qual ferramenta você usa?" abaixo.

### Cenário 2: já tenho um projeto, quero só as skills dentro dele

Não clone o repo inteiro por cima do seu projeto, clone numa pasta temporária, copie as pastas de skills e a pasta de templates, e apague a temporária:

```bash
cd /caminho/do/seu/projeto
git clone https://github.com/marketingLendario/cohort-vendas.git /tmp/cohort-vendas-temp
mkdir -p .claude/skills .agents/skills templates
cp -R /tmp/cohort-vendas-temp/.claude/skills/. .claude/skills/
cp -R /tmp/cohort-vendas-temp/.agents/skills/. .agents/skills/
cp -R /tmp/cohort-vendas-temp/templates/. templates/
rm -rf /tmp/cohort-vendas-temp
```

**Atenção pra esse detalhe, é o erro mais comum de quem segue esse caminho:** copiar só `.claude/skills` e `.agents/skills` e esquecer a pasta `templates/` faz a Central de Entregas nunca aparecer. É de dentro de `templates/central-de-entregas.html` e `templates/central-de-entregas-aula2.html` que a primeira skill de cada aula copia o painel pra raiz do seu projeto, sem esse passo o comando de "atualizar a Central de Entregas" não encontra o arquivo de onde copiar, e o painel simplesmente nunca nasce.

Isso adiciona as 10 skills (7 da Aula 1 + 3 da Aula 2) ao lado do que você já tem, sem mexer no resto do projeto. Se você já tiver uma skill com o mesmo nome de alguma dessas 10, o comando sobrescreve só ela, revise antes se isso for um problema pra você.

**Sem terminal/git?** No GitHub, clique no botão verde **Code → Download ZIP**, extraia o arquivo, e arraste as pastas `skills` de dentro de `.claude` e `.agents`, mais a pasta `templates` inteira, pra dentro do seu projeto (crie as pastas `.claude` e `.agents` primeiro se elas não existirem).

Depois de copiar, vá direto pra "Qual ferramenta você usa?" abaixo, só que, em vez de abrir a ferramenta "na pasta do repo", você abre **na pasta do seu próprio projeto** (onde acabou de colar as skills).

---

### Qual ferramenta você usa?

### Opção A: Claude Code (recomendado)

Pré-requisito: [Claude Code](https://docs.claude.com/claude-code) instalado.

1. **Antes de rodar `claude`, confirme que você está DENTRO da pasta certa** (`cohort-vendas` no Cenário 1, ou a pasta do seu projeto no Cenário 2). O erro mais comum é abrir o Claude Code um nível acima, na pasta errada, e aí nenhum comando funciona:
   ```bash
   ls .claude/skills
   ```
   Apareceram as 10 pastas (`desenho-processo-comercial`, `regua-comunicacao-comercial`, `montagem-higiene-crm`...)? Está no lugar certo. Deu erro de pasta não encontrada? Falta o `cd` pra dentro da pasta certa.
2. Abra o Claude Code:
   ```bash
   claude
   ```
3. As 10 skills em `.claude/skills/` carregam **sozinhas**, não tem passo de instalação separado.
4. Teste digitando `/desenho-processo-comercial` (Aula 1) ou `/montagem-higiene-crm` (Aula 2). Se aparecer o menu da skill, está funcionando. Se aparecer "No commands match", saia do Claude Code, confira a pasta com o comando do passo 1, e abra de novo já no lugar certo.

### Opção B: Codex CLI

Pré-requisito: [Codex CLI](https://developers.openai.com/codex/cli) instalado e autenticado (`codex login`).

1. Abra o Codex na pasta do repo ou na pasta do seu projeto (`codex`).
2. O Codex lê o `AGENTS.md` da raiz automaticamente, ele já sabe onde estão as skills (espelhadas em `.agents/skills/`) e qual é a primeira a rodar em cada aula. **Cenário 2:** se o seu projeto já tem um `AGENTS.md` próprio, copie também o `AGENTS.md` deste repo e cole o conteúdo dele no final do seu (não sobrescreva o seu inteiro).
3. Peça naturalmente: *"quero desenhar meu processo comercial"* (Aula 1) ou *"quero montar meu CRM e higienizar o pipeline"* (Aula 2), ou use `@desenho-processo-comercial` / `@montagem-higiene-crm` se a sua interface usar esse prefixo.

### Opção C: sem instalar nada (qualquer IA de chat)

Não usa Claude Code nem Codex? Cada skill é um arquivo de texto autocontido:

1. Abra `.claude/skills/{nome-da-skill}/SKILL.md` (comece por `desenho-processo-comercial` na Aula 1, ou `montagem-higiene-crm` na Aula 2).
2. Copie o conteúdo a partir do título (pule o bloco `---` do topo).
3. Cole numa conversa nova em qualquer IA de chat (ChatGPT, Gemini, etc.) e responda as perguntas que ela fizer.

Funciona pior que com skills nativas (a IA não sabe automaticamente qual arquivo vem depois), mas resolve o problema comercial igual, só exige que você abra o próximo arquivo manualmente ao final de cada etapa.

---

## Fluxo da aula (5 blocos principais + 2 bônus, ~50 min cada)

### Bloco 1: Processo Comercial com `/desenho-processo-comercial`

```
/desenho-processo-comercial [seu negócio]
```

Diagnostica ticket, ciclo, número de decisores e B2B/B2C, depois desenha as etapas do funil com critério de saída verificável (ação do cliente, nunca atividade do vendedor) e os gatilhos de risco em dois níveis: deal travado e processo desatualizado.

### Bloco 2: Régua de Comunicação com `/regua-comunicacao-comercial`

```
/regua-comunicacao-comercial
```

Puxa as etapas do Bloco 1 e define quem fala (humano/IA/ambos), o que dizer e por qual canal em cada uma, com funil de reforço por tempo parado, e ajuda a nomear o mecanismo único de conversão do seu negócio.

### Bloco 3: ICP e Qualificação com `/qualificacao-bant-gpct`

```
/qualificacao-bant-gpct
```

Puxa o perfil e a régua dos blocos anteriores e decide o mix certo entre BANT e GPCT, nunca aplicando o mesmo checklist para todo tipo de venda. Monta o ICP e gera o roteiro de qualificação com escala de pontuação objetiva.

### Bloco 4: Discovery Script com `/discovery-script`

```
/discovery-script
```

Gera o script em 6 blocos (abertura, situação, problema, implicação + gap, pessoal, fechamento parcial) ou refina um script existente comparando com calls reais, a IA aponta o que o roteiro previa versus o que aconteceu de fato.

### Bloco 5: Playbook de Vendas Vivo com `/playbook-vendas-vivo`

```
/playbook-vendas-vivo
```

Classifica cada objeção em um dos 6 tipos (preço, urgência, confiança, concorrente, autoridade, desalinhamento interno), gera a resposta com o framework certo em call/WhatsApp/e-mail, e define a cadência de revisão que mantém o playbook vivo.

### Bônus 1: Escada de Ofertas com `/escada-de-ofertas`

```
/escada-de-ofertas
```

Só se aplica se você tem mais de um produto/oferta. Desenha a jornada de ascensão entre eles, um problema de portfólio, diferente do funil comercial dos blocos anteriores.

### Bônus 2: Social Selling com `/social-selling-comercial`

```
/social-selling-comercial
```

Só se aplica se rede social é (ou vai ser) canal de prospecção ativa. Monta a sequência de LinkedIn (B2B) ou Instagram/TikTok (B2C/alto ticket) que aquece o lead antes dele entrar no funil comercial.

**Output final:** pacote comercial completo, processo, régua de comunicação, qualificação, discovery e playbook (+ escada de ofertas e social selling, se aplicáveis), pronto para rodar e para alimentar a Aula 2 (CRM e Gestão de Pipeline com IA).

---

## Fluxo da Aula 2 (abertura + 3 blocos, ~2h30 no total)

### Abertura: Cold Call para Captação de Clientes (60 min, convidado)

Bloco conduzido por João Paulo Ferreira: canal de aquisição por prospecção ativa, ferramentas de geração de lista e discagem, modelo de cold call, gravações reais do time de vendas dele, e sessão de perguntas e respostas. Você sai com um mapa mental do processo de prospecção dele e as gravações do time usando o modelo.

### Bloco 1: Montagem e Higiene de CRM com `/montagem-higiene-crm`

```
/montagem-higiene-crm [seu negócio]
```

Detecta qual ferramenta você usa hoje (com API, sem API mas com login web, ou nenhuma formal), traduz as etapas da Aula 1 pra estrutura real dela, e roda o checklist de 8 pontos de higiene.

### Bloco 2: Lead Scoring com IA com `/lead-scoring-ia`

```
/lead-scoring-ia
```

Converte a qualificação BANT/GPCT em 7 critérios de pontuação com pesos fixos, ajustados pelo seu ticket e ciclo de venda, implantados aos poucos numa ordem testada, calibrados pelo teste dos dois vendedores.

### Bloco 3: Diagnóstico de Gargalos do Funil com `/diagnostico-gargalos-funil`

```
/diagnostico-gargalos-funil
```

Lê o CRM já organizado, calcula a conversão entre etapas, distingue o gargalo aparente da causa real, e projeta a receita em risco com uma calculadora interativa que recalcula ao vivo. Fecha o loop conectando o achado a uma automação de follow-up.

**Output final:** CRM organizado, leads pontuados por critério objetivo, e o gargalo do funil identificado com valor real em risco, pronto para alimentar a Aula 3 (FUPs, Cadência e SDR).

---

## Estrutura do repo

```
.
├── README.md                       este arquivo
├── AGENTS.md                       instruções pro Codex e outros agentes
├── GUIA-DO-ALUNO.html              guia visual da Aula 1 (leia primeiro)
├── GUIA-DO-ALUNO-AULA-2.html       guia visual da Aula 2
├── .env.example                    template de variáveis (opcional)
├── .claude/
│   └── skills/                     as 10 skills, fonte canônica (Claude Code carrega automático)
│       ├── desenho-processo-comercial/      Aula 1
│       ├── regua-comunicacao-comercial/     Aula 1
│       ├── qualificacao-bant-gpct/          Aula 1
│       ├── discovery-script/                Aula 1
│       ├── playbook-vendas-vivo/            Aula 1
│       ├── escada-de-ofertas/               Aula 1, bônus
│       ├── social-selling-comercial/        Aula 1, bônus
│       ├── montagem-higiene-crm/            Aula 2
│       ├── lead-scoring-ia/                 Aula 2
│       └── diagnostico-gargalos-funil/      Aula 2
├── .agents/
│   └── skills/                     espelho literal para Codex e outros agentes
├── guias/                          um guia por problema ("estou perdido em X"), específico da Aula 1
│   ├── README.md                   o roteador: ache seu problema aqui
│   ├── 01-pre-requisitos/          terminal, instalar, baixar o projeto, custo, como ser guiado
│   ├── 02-conhecimento-minimo/     conceitos, os três funis, BANT/GPCT/SPIN, a conversa de
│   │                               venda, diferencial × concorrência, o diagnóstico
│   ├── 03-insumos/                 offerbook do marketing, calls gravadas e objeções reais
│   ├── 04-operacao/                as 7 skills, revisar e corrigir, entregáveis e central
│   └── 05-depois/                  pôr em prática, cards parados, onboarding, métricas,
│                                   vender isso como serviço, ponte pra Aula 2
├── templates/                      templates em branco dos outputs, central-de-entregas.html (Aula 1) e central-de-entregas-aula2.html (Aula 2)
├── exemplos/                       exemplos preenchidos
└── docs/
    ├── workflow.md                 fluxo completo da Aula 1
    └── SKILLS-INDEX.md             mapa de nomes (aliases para canônico) para suporte
```

> **Nota de manutenção:** `.claude/skills/` é a fonte de verdade. Se editar uma skill, replique a mudança em `.agents/skills/`, são cópias literais, não symlinks (por compatibilidade com Windows).

---

## Onde você está no cohort

```
VOCÊ
 |
 v
 Squad Vendas
 |
 +-- AULA 1: Processo Comercial & Playbook com IA        concluída
 +-- AULA 2: CRM & Gestão de Pipeline com IA             <- você está aqui
 +-- AULA 3: FUPs, Cadência, SDR e Automação             próxima
 +-- AULA 4: Proposta e Fechamento                       final
```

---

## Regras de ouro

### Critério de saída é ação do cliente, nunca do vendedor

"Enviei a proposta" não é critério de avanço de etapa. "O comprador econômico revisou e deu sinal verbal de preferência" é. Rode o teste dos dois vendedores: se dois vendedores diferentes chegassem a conclusões diferentes sobre o mesmo deal, o critério está fraco.

### Nunca repita a mensagem idêntica

Cada toque de reforço na régua de comunicação precisa de ângulo diferente, mensagem igual em dois dias seguidos é ignorada com frequência cada vez maior.

### Framework é guia de conversa, nunca checklist mecânico

BANT e GPCT existem para orientar a conversa, não para engessar. Se a pergunta soa interrogatório, o framework virou muleta.

### Sem número não é dor, é sentimento

Quantifique o gap entre estado atual e estado desejado nas próprias palavras do cliente. "É chato" não justifica preço, "custa R$40 mil por mês" justifica.

### Objeção é diagnóstico, não obstáculo

Classifique o tipo (preço, urgência, confiança, concorrente, autoridade, desalinhamento interno) antes de responder. Responder "preço" quando a objeção real é "confiança" nunca fecha o deal.

### Nenhuma automação de IA entra sem validação humana primeiro

Rode manual em 10-15 casos reais, audite a consistência entre pessoas diferentes pontuando o mesmo caso, só depois escale com IA, e continue revisando por amostragem, não só na largada. Consistência de resultado vem de régua auditada, não de IA sozinha.

### Funil comercial e funil de vendas (escada de ofertas) são coisas diferentes

O funil comercial acompanha o status de um deal específico. A escada de ofertas mapeia como o cliente sobe entre produtos diferentes ao longo do tempo. Não confunda os dois documentos.

### Nicho regulado muda a linguagem, não o processo

Saúde, estética, finanças/investimento, jurídico e psicologia têm restrição de conselho profissional (nada de "garantido", "cura" ou depoimento de paciente/cliente como prova em médico/psicologia/jurídico). O Passo 0.5 da Skill 1 detecta isso uma vez e as skills seguintes de ambas as aulas herdam a flag, você não precisa repetir a explicação a cada skill.

### Sem vendedor não é motivo pra pular o processo

Negócio 100% autoatendimento (e-commerce, app, assinatura sem humano no meio) também tem funil, só que as etapas são toques digitais (visitou, iniciou compra, comprou) e os gatilhos são de abandono, não de vendedor parado. A Skill 1 já pergunta isso no Passo 0.

### Social selling amplifica, nunca substitui os outros canais

Se você prospecta por LinkedIn ou Instagram/TikTok, a sequência de rede social (Skill 7) serve pra abrir a conversa. A partir do primeiro "sim" do lead, ele entra na régua de comunicação normal (Skill 2), não fica preso à sequência de DM pra sempre, e social selling nunca substitui WhatsApp/e-mail/ligação como canal de qualificação.

### Se você já tem algo rodando, a skill pergunta antes de recriar do zero

Processo em planilha/CRM, mensagens que já usa, objeções reais, call gravada, toda skill pede esse material primeiro e adapta em cima dele, em vez de gerar um exemplo genérico e ignorar o que você já construiu. Isso é o que garante consistência de resultado: a IA parte do que já funciona no seu negócio, não de um template solto.

### Sua ferramenta de CRM não precisa ser nenhuma em especial (Aula 2)

Com API, sem API mas com login web, ou nenhuma formal, ainda só planilha, a Skill 1 da Aula 2 detecta o seu cenário antes de montar qualquer estrutura. Nenhuma das 3 skills depende de uma ferramenta específica.

### O gargalo mais visível nem sempre é a causa real (Aula 2)

Antes de mexer na etapa com pior conversão, a `/diagnostico-gargalos-funil` confere a etapa anterior. Se ela deixa negócio malqualificado passar, o problema está lá, não na etapa que "aparenta" pior número.

### O HTML sempre abre sozinho, você nunca precisa procurar o arquivo

Assim que uma skill termina, o `.html` correspondente abre automaticamente no navegador (`open` no Mac, `start` no Windows, `xdg-open` no Linux). Se isso não acontecer (comando de abrir falhou no seu ambiente), a skill avisa o caminho exato do arquivo, nunca termina em silêncio deixando você achar sozinho.

### Você tem uma Central de Entregas acompanhando cada aula

Assim que a primeira skill de uma aula termina, aparece o painel correspondente na raiz do seu projeto: `central-de-entregas.html` pra Aula 1 (7 skills) e `central-de-entregas-aula2.html` pra Aula 2 (3 skills). Cada skill destrava o próprio card (com link pro `.md` e `.html` dela) assim que termina. O que ainda não rodou fica apagado e sem link. **Se o painel nunca aparecer**, o motivo quase sempre é a pasta `templates/` não ter sido copiada no Cenário 2 do setup (ver aviso na seção de Setup acima), sem o arquivo de origem pra copiar, a skill não tem de onde tirar o painel.

---

## Suporte

- **Dúvidas técnicas:** abra issue neste repo
- **Dúvidas de conteúdo:** canal do cohort
- **Bug ou melhoria:** PR direto neste repo

---

## Próxima aula

**Aula 3, FUPs, Cadência e SDR:** transformar o CRM organizado e os leads pontuados da Aula 2 em uma máquina de follow-up e prospecção ativa, usando o gargalo diagnosticado aqui como ponto de partida.

---

**Construído com:** Academia Lendária + Claude Code
