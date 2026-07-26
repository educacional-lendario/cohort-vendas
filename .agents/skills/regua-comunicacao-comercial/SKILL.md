---
name: regua-comunicacao-comercial
description: Monta a régua de comunicação por etapa do processo comercial — o que dizer, em qual canal e quando, para cada etapa desenhada na Skill 1. Primeiro define, para cada etapa, quem atua (vendedor humano, automação/IA, ou os dois) e o canal certo (WhatsApp, e-mail, ligação, DM). Segundo constrói o funil de reforço por tempo parado — mensagens que variam de texto conforme os dias sem resposta, nunca repetindo a mesma mensagem. Terceiro ajuda o negócio a nomear e documentar o próprio mecanismo único de conversão: o método ou abordagem distintiva que atravessa todas as etapas e canais, dando consistência de voz ao invés de scripts soltos. Use quando o usuário pedir para montar régua de comunicação, cadência de mensagens por etapa do funil, follow-up estruturado, ou definir quem (humano ou IA) fala com o lead em cada momento do pipeline. Português do Brasil.
user_invocable: true
---

# Régua de Comunicação por Etapa

## Posição na Aula 1

Esta é a **Skill 2 de 6** da Aula 1 do Cohort de Vendas. Recebe as etapas e critérios de saída desenhados na Skill 1 (`/desenho-processo-comercial`) e define, para cada uma, o que dizer, por qual canal e com que cadência — a voz que dá vida ao esqueleto desenhado ali.

**Sequência completa:** `/desenho-processo-comercial` → `/regua-comunicacao-comercial` (você está aqui) → `/qualificacao-bant-gpct` → `/discovery-script` → `/playbook-vendas-vivo` → `/escada-de-ofertas` (bônus).

Quando começar, anuncie: *"Você está na Skill 2/6 (Régua de Comunicação). Próxima vai ser /qualificacao-bant-gpct."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 2 de 6 da Aula 1 (Cohort de Vendas) — Régua de Comunicação por Etapa.
2. **Por que está aqui:** o processo (Skill 1) define QUANDO um deal muda de etapa; esta skill define O QUE DIZER e POR ONDE em cada etapa — sem ela, o vendedor sabe onde o deal está mas não sabe o que fazer com ele.
3. **O que está construindo:** `regua-comunicacao-{negocio}.md` + `regua-comunicacao-{negocio}.html`.
4. **Pendências para fechar com nota 10:** confirme se ele já rodou a Skill 1 (etapas do processo) — sem isso, peça pelo menos a lista de etapas antes de montar a régua; confirme também quais canais o negócio realmente usa hoje (não invente canal que ele não opera).

Se ele quiser o quadro completo da aula, remeta ao `GUIA-DO-ALUNO.html` (seção "As 6 skills da aula" e "Fluxo da aula").

---

## Mentes por trás desta skill

- **Jeb Blount** (*Fanatical Prospecting*) — o princípio "pipeline vazio é o erro nº 1, e a causa nº 1 do pipeline vazio é parar de prospectar": base do funil de reforço por tempo parado — régua que para de disparar é pipeline que morre em silêncio.
- **Aaron Ross** (*Predictable Revenue*) — especialização de papéis (quem prospecta, quem qualifica, quem fecha, quem retém) usada no Passo 1 para definir quem atua em cada etapa.

---

Você é o arquiteto da régua de comunicação comercial. Sua função é responder, para cada etapa do funil, três perguntas que a maioria dos times comerciais nunca formaliza: **quem fala** (vendedor, automação, ou os dois), **o que fala** (mensagem certa pro momento certo) e **por onde fala** (canal certo pro contexto). Régua de comunicação mal desenhada tem dois sintomas opostos: ou o lead recebe silêncio (etapa "esquecida", ninguém sabe que é responsabilidade de alguém) ou recebe barulho (mensagem repetida, dois canais batendo a mesma coisa, automação e humano se atropelando).

Princípio central: **nunca repita a mensagem idêntica.** Mensagem igual em D+1 e D+2 é ignorada com frequência cada vez maior — cada toque de reforço precisa de ângulo diferente (pergunta, oferta de valor, urgência), não de reenvio do mesmo texto. Segundo princípio: **automação nunca fala por cima de humano ativo.** Se o vendedor já está numa etapa negociando ativamente com o lead, nenhuma régua automática deve disparar mensagem concorrente na mesma janela — quem está com a mão no deal tem prioridade.

## Passo 0 — Puxar as etapas e as flags (gate de entrada)

Puxe as etapas, critérios de saída, e as flags `nicho_regulado` e `modelo` (com-vendedor/autoatendimento) da Skill 1 (`/desenho-processo-comercial`), se já rodada. Se não, peça pelo menos a lista de etapas do funil e as duas flags antes de continuar — régua de comunicação sem etapa definida não tem onde ancorar, e sem saber se o nicho é regulado você pode sugerir uma mensagem que vira problema legal. Pergunte também:

> Quais canais vocês realmente usam hoje pra falar com lead? (WhatsApp, e-mail, ligação, DM de rede social, outro) — não vou sugerir canal que vocês não operam.

## Passo 1 — Definir quem atua em cada etapa

Para cada etapa do funil (herdada do Passo 0), classifique quem atua:

- **Humano** — só o vendedor dono do deal age; nenhuma automação dispara aqui (normalmente etapas de negociação avançada, onde a conversa já é 1:1 e sem template).
- **Automação/IA** — disparo automático por regra de tempo (ex.: lead sem resposta há X dias); típico em etapas de topo de funil (primeiro contato, reforço de contato sem resposta).
- **Ambos** — automação atua enquanto o humano não estiver engajado ativamente; no momento em que o humano sinaliza que está conduzindo, a automação para de disparar nessa etapa para aquele lead específico.
- **Automação apenas, sem humano** — perfil "autoatendimento/zero-toque" (herdado da Skill 1): todas as etapas são automação (e-mail transacional, remarketing, notificação de carrinho abandonado). Não force uma etapa "humana" que não existe nesse modelo de negócio.

Documente a regra de prioridade explicitamente: *"Automação nunca dispara por cima de humano ativo — é o vendedor quem sinaliza que está com a mão no deal, não a automação que decide parar sozinha."* (Regra não se aplica ao perfil autoatendimento — lá não existe humano disputando prioridade.)

Se o time já tiver mais de uma pessoa no comercial, pergunte se faz sentido especializar por papel (modelo de Aaron Ross: quem prospecta/qualifica no topo do funil não é necessariamente quem fecha, e quem fecha não é necessariamente quem retém/expande depois) — isso muda o "quem atua" de "o vendedor" genérico para o papel certo em cada etapa. Times pequenos (1-2 pessoas) não precisam dessa especialização ainda; não force.

## Passo 1.5 — Calibrar linguagem se o nicho for regulado

Se a flag `nicho_regulado` herdada da Skill 1 for **sim**, toda mensagem da régua (qualquer etapa, qualquer canal) segue estas regras antes de ser escrita:

- Nunca prometer "cura", "garantido", "resultado em X dias", "renda garantida", "sem esforço" — nem em mensagem de reforço, nem em mensagem de "último contato".
- Usar linguagem de possibilidade: "pode ajudar", "muitas pessoas relatam", "com dedicação".
- **Médico (CFM), psicologia (CRP), jurídico (OAB):** nenhuma mensagem da régua pode citar depoimento de paciente/cliente como prova social — nem informal, nem em WhatsApp. Use credencial, método ou conteúdo educativo como gancho de reengajamento em vez de prova social.
- Isso vale inclusive para o "mecanismo único de conversão" do Passo 3 — o nome e a descrição do método não podem prometer o que a regulação proíbe.

Se `nicho_regulado` for não, pule esta etapa sem comentário.

## Passo 2 — Construir a régua de mensagens por etapa

Para cada etapa, defina:

1. **Objetivo da comunicação nesta etapa** — em uma frase (ex.: "gerar curiosidade suficiente pra puxar uma resposta", "reduzir no-show confirmando expectativa antes da call").
2. **Canal principal e canal de reforço** — qual canal abre a etapa, e qual entra se o primeiro não gerar resposta.
3. **Funil de reforço por tempo parado** (para etapas de espera de resposta): monte uma tabela com o texto variando a cada toque.

Modelo de referência (adapte ao seu negócio — nunca copie um texto genérico sem adaptar ao tom da marca):

| Tempo parado | Ângulo da mensagem | Exemplo de estrutura (adapte, não copie literal) |
|---|---|---|
| D+1 | Reforço curto, ângulo diferente do primeiro contato | Pergunta nova, não repetição da primeira |
| D+2 a D+3 | Oferta de valor gratuito (material, aula, diagnóstico) | Reengaja sem parecer insistência de venda |
| Penúltimo toque | Tom direto, sinaliza que a janela está fechando | Sem ameaça, mas com clareza de prazo |
| Sem resposta após o último toque | Etapa muda para "sem resposta" (não "perdido para sempre") | Lead entra em fluxo de nutrição de longo prazo, não é descartado |

4. **Saída esperada da etapa** — para onde o lead vai quando responde, e para onde vai quando esgota a régua sem resposta.

Alerte o usuário: régua de mensagens não é fim de linha quando esgota. Lead que não respondeu a etapa inteira normalmente entra num fluxo de nutrição separado (conteúdo de valor, cadência mais espaçada) em vez de ser descartado — reengajamento futuro reabre o funil no ponto certo, não do zero.

## Passo 3 — Nomear o mecanismo único de conversão

Esta é a etapa que dá identidade à régua inteira. Pergunte ao usuário:

> Existe um nome, um método ou um jeito de vender que já é característico do seu negócio — algo que, se um concorrente tentasse copiar a mensagem sem entender o método por trás, não funcionaria igual? Se não existe ainda, vamos criar um nome pra isso agora, a partir do que já funciona na prática de vocês.

Um mecanismo único de conversão não é um script — é o **porquê** por trás da sequência de mensagens que faz ela funcionar (ex.: "sempre entender o momento do lead antes de falar de produto", "nunca empurrar reunião sem confirmar expectativa primeiro", "toda objeção de preço volta pro número da dor, nunca pro desconto"). Dê um nome curto e memorável a esse método (2-4 palavras) — isso vira a assinatura que atravessa a régua inteira, o discovery (Skill 4) e o playbook de objeções (Skill 5), garantindo que humano e IA falem com a mesma voz em qualquer canal.

Se o usuário não conseguir articular um mecanismo único ainda, não invente um genérico por ele — documente as 2-3 práticas que já funcionam na régua desenhada nos Passos 1-2 como "primeiro rascunho do mecanismo", e marque como pendência para validar com mais dados de call real.

## Passo 4 — Regras transversais (valem para toda a régua)

Feche com as regras que atravessam todas as etapas:

1. Nunca repetir mensagem idêntica em toques consecutivos.
2. Automação nunca fala por cima de humano ativo.
3. Toda saída por "sem resposta" ou "perdido" precisa de motivo registrado — sem isso, a métrica de conversão da régua fica furada.
4. Revisão da régua junto com a revisão trimestral do processo (Skill 1) — régua de mensagens desatualizada (preço mudou, oferta mudou) é tão grave quanto etapa de processo desatualizada.
5. **A régua nunca para sozinha** (princípio de Jeb Blount): um dia sem disparo na etapa de topo de funil é um dia de pipeline morrendo em silêncio — se a régua parar, alguém decidiu isso, não foi esquecimento.

## Passo 5 — Entregar o output (sempre em dois formatos)

Gere **dois arquivos com o mesmo conteúdo**:

1. `regua-comunicacao-{negocio}.md` com: quem atua por etapa (Passo 1), a régua de mensagens completa com funil de reforço por tempo parado (Passo 2), o mecanismo único de conversão nomeado e documentado (Passo 3), e as regras transversais (Passo 4). Feche com o handoff: *"Esta régua alimenta a Skill 4 (/discovery-script), que usa o canal e o tom definidos aqui para a etapa de discovery, e a Skill 5 (/playbook-vendas-vivo), que usa o mecanismo único para dar consistência às respostas de objeção em qualquer canal."*
2. `regua-comunicacao-{negocio}.html` — mesma informação em página autocontida, mesmos tokens visuais do `GUIA-DO-ALUNO.html` (fundo `#0A0A0A`, ouro `#C9B298`), com uma linha do tempo visual por etapa (quem atua, canal, régua de reforço) e o mecanismo único de conversão destacado em card próprio no topo, como a "marca registrada" do negócio.
