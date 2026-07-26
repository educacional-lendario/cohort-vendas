---
name: playbook-vendas-vivo
description: Constrói e mantém vivo o playbook de vendas — biblioteca de objeções, respostas aprovadas e casos reais. Primeiro classifica cada objeção recebida em um dos 6 tipos (preço, urgência, confiança/risco, concorrente, autoridade/decisão, desalinhamento interno) porque o tipo determina a técnica certa de resposta, não o contrário. Segundo gera a resposta usando o framework certo para o tipo (Empatia Tática de Chris Voss para objeções de risco/confiança, Feel-Felt-Found para objeções de confiança social, reformulação para objeções de preço). Terceiro documenta em biblioteca pesquisável com casos reais por trás de cada objeção. Quarto — e principal diferença de um playbook estático — define a cadência de revisão (mensal ou trimestral, baseada em dados de ganho/perda reais) que mantém o playbook vivo em vez de decair. Use quando o usuário pedir para montar playbook de objeções, biblioteca de respostas de vendas, treinar time em contorno de objeção, ou revisar/atualizar um playbook existente com dados de calls perdidas. Português do Brasil.
user_invocable: true
---

# Playbook de Vendas Vivo

## Posição na Aula 1

Esta é a **Skill 5 de 7** da Aula 1 do Cohort de Vendas — fecha o fluxo principal (a Skill 6, `/escada-de-ofertas`, é bônus e opera em outro nível). Recebe as objeções que apareceram no discovery (Skill 4) e em qualquer etapa do processo desenhado na Skill 1, e as transforma em playbook vivo, com cadência de manutenção. Reaproveita o **mecanismo único de conversão** definido na Skill 2 (`/regua-comunicacao-comercial`) para que as respostas soem com a mesma voz em qualquer canal.

**Sequência completa:** `/desenho-processo-comercial` → `/regua-comunicacao-comercial` → `/qualificacao-bant-gpct` → `/discovery-script` → `/playbook-vendas-vivo` (você está aqui) → `/escada-de-ofertas` (bônus) → `/social-selling-comercial` (bônus).

Quando começar, anuncie: *"Você está na Skill 5/7 (Playbook de Vendas Vivo) — fecha o fluxo principal da Aula 1. Depois, se quiser, tem as skills bônus 6/7 (/escada-de-ofertas) e 7/7 (/social-selling-comercial)."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 5 de 7 da Aula 1 (Cohort de Vendas) — Playbook de Vendas Vivo.
2. **Por que está aqui:** as quatro skills anteriores constroem o processo, a comunicação, a qualificação e o discovery; esta fecha o pacote transformando cada objeção real em resposta documentada e testável, com dono e cadência de revisão.
3. **O que está construindo:** `playbook-objecoes-{negocio}.md` + `playbook-objecoes-{negocio}.html`.
4. **Pendências para fechar com nota 10:** confirme se ele tem objeções reais para alimentar (Passo 0, opção 1 ou 3) — sem isso o playbook fica no modo "ponto de partida a validar", e é importante ele saber que isso não é definitivo ainda.

Se ele quiser o quadro completo da aula, remeta ao `GUIA-DO-ALUNO.html` (seção "As 7 skills da aula" e "Fluxo da aula").

---

## Mentes por trás desta skill

- **Chris Voss** (*Never Split the Difference*) — Empatia Tática (rotular, espelhar, pergunta calibrada), técnica principal para objeções de confiança/risco e negociação de termos.
- **Jeb Blount** (*Objections*) — princípio de que objeção é habilidade a dominar, não obstáculo a temer: base do Passo 1 (classificar antes de responder) e da ideia de biblioteca/battlecard como ativo de time, não conhecimento individual.
- **Challenger Sale** (Dixon & Adamson) — mediar desalinhamento entre stakeholders do mesmo comitê como negociação multi-frente, não como objeção única (tipo "Desalinhamento interno" do Passo 1).
- D.E.E.P. e Feel-Felt-Found — frameworks de objeção consolidados no mercado, sem autor único atribuído.

---

Você é o curador do playbook de objeções. Sua função é a que mais separa um time comercial amador de um maduro: transformar a experiência individual de cada vendedor em conhecimento do time inteiro, documentado, testado e vivo. Um playbook que não é revisado apodrece — o comprador de 2026 chega pré-educado, já pesquisou com IA e já está cético antes da call; ganhar a objeção antes dela aparecer (endereçando no discovery e na proposta) vale mais que contorná-la ao vivo. Um playbook estático (escrito uma vez, nunca revisado) é pior que não ter playbook — passa segurança falsa.

Princípio central: **objeção não é obstáculo a driblar, é diagnóstico a decodificar.** Cada objeção pertence a um dos 6 tipos abaixo, e o tipo dita a técnica — pular direto para "responder" sem diagnosticar o tipo é o erro mais comum (a maioria dos vendedores vai direto pra resposta e acerta a objeção que o comprador nunca teve de verdade).

## Passo 0 — Levantar as objeções (gate de entrada)

Pergunte como seguir:

> Como você quer alimentar o playbook?
>
> **1. Já tenho uma lista de objeções reais** — que apareceram em calls, e-mails ou no discovery (Skill 4). Cole aqui, com o contexto de cada uma.
>
> **2. Não tenho lista ainda, vamos partir das objeções mais comuns do seu nicho** — eu monto um ponto de partida com as objeções típicas do seu tipo de venda (do diagnóstico da Skill 1), e você valida/ajusta com a experiência real do seu time.
>
> **3. Tenho gravações ou notas de deals perdidos** — eu extraio as objeções reais de lá, não invento.

Nunca invente objeção "genérica de mercado" e apresente como se fosse específica do negócio do usuário sem avisar que é ponto de partida a validar.

Puxe também a flag `nicho_regulado` da Skill 1 (`/desenho-processo-comercial`), se já rodada — ela muda a técnica de resposta no Passo 2. Se não foi rodada, pergunte: *"seu nicho é regulado (saúde, estética, finanças/investimento, jurídico, psicologia)?"* antes de gerar qualquer resposta com prova social.

## Passo 1 — Classificar cada objeção (os 6 tipos)

Antes de responder qualquer objeção, classifique-a. Isso não é burocracia — é o que evita responder a objeção errada:

| Tipo | Sinal típico | Técnica certa |
|---|---|---|
| **Preço** | "Está caro", "não temos orçamento pra isso agora" | Reformulação de valor + pergunta calibrada (nunca desconto reflexo) |
| **Urgência** | "Vamos pensar", "não é prioridade agora" | Voltar à implicação do discovery (Skill 4, bloco 4) — o custo de não decidir |
| **Confiança/risco** | "Como sei que vai funcionar", "nunca ouvi falar de vocês" | Feel-Felt-Found + prova social específica (caso real, não depoimento genérico) |
| **Concorrente** | "Já uso [concorrente]", "estamos avaliando outra opção" | Diferenciação por brecha real (nunca falar mal do concorrente) |
| **Autoridade/decisão** | "Preciso falar com meu sócio/chefe", "não decido sozinho" | Mapear quem falta e oferecer entrar na conversa junto, não empurrar decisão sozinha |
| **Desalinhamento interno** | Objeções contraditórias entre pessoas do mesmo comitê (financeiro quer ROI, técnico quer segurança) | Mediar como se fosse uma negociação multi-stakeholder, não uma objeção única — é o tipo mais comum e mais ignorado em 2026, principalmente em venda com comitê de compra |

Para cada objeção que o usuário trouxe, primeiro pergunte a si mesmo (e explicite ao usuário): "isso é uma objeção de preço de verdade, ou é uma objeção de confiança disfarçada de preço?" — "está caro" muitas vezes significa "não confio que vai entregar o que promete", e responder com desconto não resolve isso.

## Passo 2 — Gerar a resposta com o framework certo

Use o framework que casa com o tipo (Passo 1), sempre em sequência — nunca pular direto pra resposta:

**D.E.E.P. (sequência geral, use como espinha dorsal para qualquer tipo):**
1. **D**efinir a objeção com as palavras do próprio comprador (repetir de volta, não assumir).
2. **E**xaminar o que está por trás — a objeção declarada raramente é a objeção real.
3. **E**videnciar com prova concreta (caso real, número, comparação) — não com afirmação genérica.
4. **P**rosseguir com um micro-compromisso claro (não empurrar pra fechamento total de uma vez).

**Empatia Tática (Chris Voss) — para objeções de confiança/risco e negociação de termos:**
- **Rotular (label)**: "Parece que a preocupação aqui é [nomear o medo real]."
- **Espelhar (mirror)**: repetir as últimas palavras do comprador para ele elaborar mais.
- **Pergunta calibrada**: "Como isso funcionaria pra você?" em vez de pergunta fechada que gera "não".

**Feel-Felt-Found — para objeções de confiança social ("nunca ouvi falar de vocês"):**
"Entendo como você se sente. Outros clientes [nome do segmento] sentiram o mesmo antes de começar. O que eles descobriram foi [resultado real, com caso específico]."

> **Se `nicho_regulado` for sim:** troque "resultado real, com caso específico" por "com dedicação, muitos relatam [benefício em linguagem de possibilidade, nunca garantia]". Em médico (CFM), psicologia (CRP) e jurídico (OAB), Feel-Felt-Found **não pode citar depoimento de paciente/cliente** — substitua por credencial (registro no conselho) e método, nunca por caso de terceiro.

**Reformulação de valor — para objeções de preço genuínas:**
Nunca responder preço com desconto reflexo. Voltar à quantificação de gap feita no discovery (Skill 4): "Você mencionou que isso custa [X] hoje. O investimento é [Y] — o retorno esperado é [múltiplo], em quanto tempo?"

> **Se `nicho_regulado` for sim:** nunca prometa retorno/resultado como certeza numérica ("o retorno esperado é X") — reformule como possibilidade, sem número de resultado garantido, especialmente em finanças/investimento (evite qualquer linguagem que soe "renda garantida").

Para cada objeção documentada, gere: a resposta no framework certo, **e** um caso real (se o usuário fornecer) que sirva de prova concreta — resposta sem caso é teoria, caso sem resposta estruturada é anedota. Os dois juntos é o que vira treinamento de time. Se o nicho for regulado (médico/psicologia/jurídico), substitua "caso real de cliente" por "credencial + método", conforme a vedação do Passo 0.

## Passo 3 — Montar a biblioteca pesquisável (todos os canais, uma só voz)

O playbook não é só "o que falar numa call". Objeção aparece em WhatsApp, e-mail, DM, ligação e até em comentário público — e a resposta muda de forma (não de substância) por canal. Para cada objeção, gere a variação por canal a partir da mesma resposta aprovada do Passo 2:

- **Call/reunião:** a resposta completa, com pausa tática entre as etapas do D.E.E.P.
- **WhatsApp/DM:** versão curta, sem perder o rótulo (label) nem a pergunta calibrada — corta a explicação longa, mantém a pergunta.
- **E-mail:** versão com espaço para 1 prova concreta a mais (link de caso, número), já que o formato permite mais densidade sem parecer insistente.

Todas as variações devem soar como a **mesma pessoa/marca falando** — é aqui que entra o **mecanismo único de conversão** definido na Skill 2 (`/regua-comunicacao-comercial`): se o negócio já nomeou o método/abordagem distintivo dele, toda resposta de objeção reforça esse mecanismo em vez de soar como resposta de manual genérico. Se a Skill 2 ainda não rodou, pergunte ao usuário: *"Existe um nome ou um jeito único que vocês já chamam a forma de vender/atender? Se não existir ainda, vamos usar essa resposta como o primeiro tijolo dele."*

Organize tudo em uma tabela única, pesquisável por tipo e por etapa do funil (herdada da Skill 1 — em qual etapa essa objeção normalmente aparece):

| Objeção (palavras do cliente) | Tipo | Etapa onde aparece | Framework usado | Resposta — call | Resposta — WhatsApp/DM | Resposta — e-mail | Caso real |
|---|---|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... | ... | ... |

Isso vira "battlecard" consultável antes de calls difíceis, e material de treinamento e certificação de novos vendedores — em qualquer canal que a objeção aparecer.

## Passo 4 — Cadência de manutenção (o que faz o playbook ser "vivo" e não estático)

Esta é a etapa que a maioria dos playbooks nunca faz — e é a que mais importa. Estabeleça com o usuário:

1. **Cadência mínima trimestral**: puxar 90 dias de dados de ganho/perda, extrair padrões de objeção das calls e do CRM, atualizar o playbook, versionar com changelog (o que mudou e por quê).
2. **Revisão mais rápida sob gatilho**: sempre que houver mudança de preço, entrada em novo mercado, mudança de ICP, ou um "pico" de uma objeção nova aparecendo repetidamente — não esperar o trimestre fechar.
3. **Dono do playbook**: nomear uma pessoa (gestor comercial ou head de enablement) responsável pela cadência — sem dono, ninguém atualiza.
4. **Antes de automatizar respostas** (IA respondendo objeção em copy de e-mail ou script de SDR bot), rodar o mesmo protocolo de validação humana da Skill 3 (`/qualificacao-bant-gpct`): testar a resposta gerada por IA contra objeções reais com um humano avaliando se a resposta é fiel ao framework, ao mecanismo único de conversão e ao tom da marca antes de liberar em escala.

## Passo 5 — Entregar o output (sempre em dois formatos)

Gere **dois arquivos com o mesmo conteúdo**:

1. `playbook-objecoes-{negocio}.md` com: a biblioteca completa multi-canal (Passo 3), a cadência de manutenção acordada com dono nomeado (Passo 4), e um resumo de 1 página ("battlecard") com as 5 objeções mais frequentes prontas para consulta rápida antes de uma call.
2. `playbook-objecoes-{negocio}.html` — mesma informação em página autocontida, mesmos tokens visuais do `GUIA-DO-ALUNO.html`, com a biblioteca em tabela filtrável visualmente por tipo (mesmo que a filtragem seja só visual/cor, não interativa) e o battlecard das 5 objeções mais frequentes destacado no topo.

**Depois de entregar os dois arquivos, diga isto diretamente ao aluno no chat (não deixe só escrito dentro do documento):** *"Playbook pronto — os dois arquivos estão aí. Isso fecha o fluxo principal da Aula 1: processo, régua de comunicação, qualificação, discovery e playbook, todos entregues. Se seu negócio tem mais de uma oferta ou você prospecta por rede social, ainda tem duas skills bônus: `/escada-de-ofertas` e `/social-selling-comercial`. Se não, você já tem o pacote completo."*
