# GUIA E DEPOIS — os documentos estão prontos. E agora?

> **Estou perdido em:** "rodei as 7 skills, tenho os documentos… e agora? O que eu faço na segunda-feira de manhã?".
> **O que você vai ter no final:** o plano dos primeiros 30 dias — quem executa, o que automatizar (e o que não), quando rodar de novo, e o que levar pra Aula 2.
> **Fontes cruzadas:** o `SKILL.md` da `/qualificacao-bant-gpct` (Passo 5, o protocolo de validação humana antes de automação) e da `/playbook-vendas-vivo` (Passo 4, cadência de manutenção com dono nomeado) e da `/desenho-processo-comercial` (Passo 2, revisão trimestral e gatilhos de processo) · o `docs/workflow.md` (o que a Aula 1 NÃO faz) · a Aula 1 ao vivo, onde a professora fechou explicando o que é da Aula 3 e por que não automatizar agora · pesquisa sobre por que processo comercial documentado não pega no time (consultada em 03/08/2026).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📄 Artefato | Os entregáveis do fluxo principal (Skills 1 a 5) | veja [guia-mapa-das-skills.md](../04-operacao/guia-mapa-das-skills.md) |
| 📖 Conhecimento | Ter revisado os documentos, não só gerado | leia [guia-revisar-e-corrigir.md](../04-operacao/guia-revisar-e-corrigir.md) |

## O objetivo real da aula (que não é "ter documentos")

Fala de fechamento da Aula 1:

> *"O principal objetivo aqui é tirar o processo comercial da sua cabeça, ou da cabeça do seu principal vendedor, e começar a mapear os processos."*
>
> *"É você ter o seu processo comercial desenhado ao nível de que, se você parar sete dias, quinze dias, o comercial não pare."*

Documento na pasta não faz isso sozinho. Os passos abaixo é que fazem.

## Semana 1 — Tirar do papel

### Passo 1 — Nomeie o dono de cada documento

Sem dono, nada é atualizado. Mesmo se for você em todos:

| Documento | Dono | O que ele faz |
|---|---|---|
| Processo comercial | | garante que as etapas usadas batem com as desenhadas |
| Régua de comunicação | | garante que ninguém manda mensagem fora da régua |
| Qualificação | | audita as notas dadas (é o Passo 5 da Skill 3) |
| Playbook de objeções | | recolhe objeção nova e atualiza a biblioteca |

A Skill 5 exige isso explicitamente: *"nomear uma pessoa responsável pela cadência — sem dono, ninguém atualiza."*

### Passo 2 — Coloque as etapas onde o trabalho acontece

Hoje, provavelmente numa planilha ou num quadro. Está tudo bem — **o CRM é a Aula 2**. Por enquanto, o mínimo viável:

- uma coluna por etapa do seu processo;
- para cada card: valor em R$, data da última movimentação, e o contrato de dados que a Skill 1 definiu (resumo da conversa, objeções);
- a etapa **Perdido** com **motivo categorizado** — este é o campo mais importante da planilha inteira.

⚠️ **Sem valor preenchido em todo card das etapas finais, o forecast é ficção.** É a condição que a Skill 1 registra: só faz sentido somar se todo mundo tem valor.

### Passo 3 — Ligue a gravação de todas as calls

A partir de hoje, sem exceção. É o insumo que vai melhorar tudo daqui pra frente — veja [guia-insumos-reais.md](../03-insumos/guia-insumos-reais.md).

### Passo 4 — Mande os HTMLs pra quem precisa

Os `.html` foram feitos pra isso: *"o aluno consegue mandar esse HTML para o time dele sem precisar explicar nada — o documento se explica sozinho."*

## Semanas 2 a 4 — Validar antes de escalar

### O protocolo de validação humana (regra inegociável)

Direto do `SKILL.md` da Skill 3, e repetido na Skill 5:

1. **Rodar manual primeiro** — aplique o roteiro de qualificação em **10 a 15 conversas reais**, com um humano pontuando.
2. **Auditar a régua** — duas pessoas diferentes pontuam as mesmas conversas (ou as mesmas gravações). Se as notas divergirem muito, a pergunta ou a escala precisa de ajuste **antes** de escalar.
3. **Só depois automatizar** — e mesmo assim com revisão humana amostral contínua (ex.: 1 em cada 10 qualificações automáticas revisada por humano), não só na largada.

> *"Isso não é burocracia extra: é a diferença entre um scorecard que funciona e um que parece funcionar até o primeiro lead grande cair na régua errada."*

**Trabalha sozinho?** O passo 2 vira: pontue as mesmas 5 conversas de novo, uma semana depois, sem olhar as notas antigas. Se você mesmo dá notas diferentes, a régua está frouxa.

## O que automatizar (e o que nunca)

Este foi o tema que mais voltou na Aula 1:

> *"A partir do momento em que a gente quer montar alguma coisa do zero, já quer automatizando tudo. E isso não é bem o caminho. O caminho ideal é mapear o processo, entender… e aí sim, depois, a gente vai conseguir automatizar, colocar um agente onde achar interessante — mas aí a gente já tem a régua de comunicação que aquele agente vai trabalhar."*

O mapa que a Skill 2 já entregou dentro da sua régua (a coluna "quem atua"):

| Etapa típica | Quem atua | Por quê |
|---|---|---|
| Primeiro contato, reforço sem resposta | **automação ou ambos** | é disparo por regra de tempo, alto volume, baixo risco |
| Confirmação de reunião, lembrete | **automação** | mecânico e previsível |
| Qualificação | **ambos** — IA sugere, humano decide | a nota precisa ser auditada (protocolo acima) |
| Discovery | **humano** | é onde a dor vira número; não delegável |
| Proposta e negociação | **humano** | conversa 1:1, sem template. A Skill 2 registra: *"sem régua automática"* |
| Nutrição de quem não respondeu | **automação** | cadência longa, conteúdo de valor |
| Onboarding pós-venda | **humano** (ou ambos) | fechar sem kickoff é adiar o churn |

⚠️ **A regra transversal que protege tudo:** *"automação nunca fala por cima de humano ativo."* Se o vendedor está com a mão no deal, nenhuma régua automática dispara mensagem concorrente naquela janela.

### O que fica pras próximas aulas

O `docs/workflow.md` é explícito sobre o que **não** é da Aula 1:

| Assunto | Aula | Professor |
|---|---|---|
| Configurar CRM, integrar ferramentas, higienizar pipeline | **Aula 2** | Bruno |
| Cadência de prospecção outbound fria, FUPs, SDR | **Aula 3** | Adávio |
| Automação e fechamento com IA | **Aula 4** | Marcondes |

Da aula: *"vocês podem sentir falta — ah, mas eu queria automatizar mais. Então, só pra deixar vocês mais calmos: vai ser [na Aula 3]."*

## Quando rodar as skills de novo

Não é "rodou uma vez, acabou". A ordem de prioridade:

| Quando | Rode de novo | Por quê |
|---|---|---|
| **Depois das 3-5 primeiras reuniões gravadas** | `/discovery-script` e `/playbook-vendas-vivo` | o maior salto de qualidade de todos: sai da teoria e entra na sua realidade |
| **Se você conseguiu o offerbook do Cohort de Marketing depois** | Skills 3, 5, 2 (nesta ordem) | veja [guia-offerbook-do-marketing.md](../03-insumos/guia-offerbook-do-marketing.md) |
| **Quando surgir um segundo produto** | `/escada-de-ofertas` | antes disso ela nem roda |
| **Quando o perfil de rede social estiver pronto** | `/social-selling-comercial` | o checkpoint dela deixa de bloquear |
| **A cada 3 meses, sem gatilho nenhum** | `/desenho-processo-comercial` e `/playbook-vendas-vivo` | *"funil não revisado apodrece silenciosamente"* |

### Os gatilhos que antecipam a revisão

Não espere o trimestre fechar se acontecer qualquer um destes (são os gatilhos de processo da Skill 1):

- lançou produto ou oferta nova;
- o ciclo de venda ou a taxa de conversão entre etapas mudou de forma consistente por 2+ ciclos;
- entrou concorrente novo relevante;
- o ICP mudou (novo segmento, novo porte de conta);
- mudou o preço;
- uma objeção nova começou a aparecer repetidamente.

## Por que processo documentado não pega (e como evitar)

Esta é a causa nº 1 de o pacote da Aula 1 virar arquivo morto. Os números de mercado, sobre implantações de processo e CRM:

| Fato | Referência |
|---|---|
| Falhas atribuídas a **pessoas** (resistência, papel mal ajustado) | mais de 60% |
| Falhas atribuídas a **processo quebrado** | ~30% |
| Falhas atribuídas à **ferramenta** | apenas 6% a 10% |

⚠️ **Ou seja: quase nada disso é problema de ferramenta.** Não adianta esperar a Aula 2 (CRM) resolver o que é problema de desenho e de adoção.

As três causas concretas, e o antídoto de cada uma:

| Causa | Como se manifesta | Antídoto |
|---|---|---|
| **O preenchimento custa mais do que devolve** | cada campo obrigatório é um pedágio entre o vendedor e a próxima conversa | corte todo campo que não muda uma decisão. É a regra de calibragem de rigor da Skill 1 |
| **É mais difícil fazer certo do que fazer errado** | não é falta de disciplina, é atrito | quando a ação certa é a mais fácil, a adoção acontece sem briga. Simplifique antes de cobrar |
| **A liderança sinaliza que o processo é opcional** | o dono roda a reunião de pipeline por uma planilha paralela | se você tem time: conduza a reunião **pelo** documento e **pelo** quadro. Se você usa outra fonte, todo mundo entende que a oficial não vale |

**A tradução pro aluno que trabalha sozinho:** o "time" é você daqui a três meses. Se preencher for chato demais, você não vai preencher — e vai voltar a operar de cabeça.

## O ciclo que fecha: comercial alimenta marketing e produto

Um ponto que a Aula 1 bateu bastante e quase ninguém opera:

> *"O setor comercial precisa mapear não só o processo de cada etapa, mas também nutrir o marketing e nutrir produto."*

Três fluxos práticos, que saem dos seus documentos:

| O que você coletou | Manda pra | Vira o quê |
|---|---|---|
| **Motivo das perdas** (etapa Perdido) | marketing | correção de ICP — se todo lead chega frio demais, o problema é a captação, não o vendedor |
| **Objeções do playbook** | marketing | conteúdo, e-mail e anúncio que quebram a objeção **antes** da call |
| **"Falta a funcionalidade X"** repetido | produto | roadmap. Da aula: *"o comercial pode trazer visões do produto e de features novas que podem ser lançadas"* |

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Montar o plano dos primeiros 30 dias** | "Leia todos os `.md` que as skills da Aula 1 geraram nesta pasta. Monte meu plano dos primeiros 30 dias: o que eu faço na semana 1, 2, 3 e 4, com no máximo 3 tarefas por semana. Meu contexto: [trabalho sozinho / tenho time de X pessoas]." |
| **Descobrir o que ficou pendente** | "Leia meus entregáveis da Aula 1 e liste tudo que está marcado como 'ponto de partida a validar', 'hipótese' ou 'pendente'. Ordene pelo que mais me atrapalha se continuar não validado." |
| **Traduzir o processo pra planilha** | "Leia meu `processo-comercial-{negocio}.md` e me dê a estrutura da planilha mínima pra operar esse funil: as colunas, os valores possíveis de cada campo, e as categorias fechadas de motivo de perda." |
| **Saber o que levar pra Aula 2** | "Leia meus entregáveis da Aula 1. O que exatamente vira configuração de CRM (estágios, campos, automações) na próxima aula? Monte a lista pra eu chegar lá com a especificação pronta." |
| **Diagnosticar por que ninguém usa** | "Meu processo está documentado mas o time (ou eu mesmo) não está seguindo. Isto é o que exigimos preencher hoje: [liste]. Para cada campo, me diga se ele muda uma decisão ou é burocracia — e corte o que for burocracia." |

## Teste de sucesso

Responda com honestidade:

1. Cada um dos 4 documentos principais tem um **nome de pessoa** como dono?
2. Existe um lugar (planilha, quadro, CRM) onde os deals estão nas etapas que **você desenhou**?
3. A etapa Perdido tem **motivo categorizado** obrigatório?
4. As calls estão sendo gravadas a partir de hoje?
5. Você tem uma data marcada no calendário pra revisar em 3 meses?

**Funcionou se:** as cinco são "sim". Aí sim o processo saiu da sua cabeça e virou processo.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| DP1 | Os documentos estão lindos e ninguém usa | Faltou dono e faltou o processo estar onde o trabalho acontece | 1) nomeie donos (Passo 1) 2) leve as etapas pra planilha/quadro (Passo 2) 3) mande os HTMLs pro time |
| DP2 | Quero automatizar tudo já | Ansiedade natural, e o erro mais caro da aula | rode o protocolo de validação humana primeiro (10-15 casos). Automação é Aula 3. *"A chance de dar ruim é muito grande, e de você gastar muitos dinheiros"* |
| DP3 | O vendedor não segue o processo | Rigor mal calibrado, e quase nunca é falta de disciplina — é atrito | 1) confira se cada campo exigido realmente muda o comportamento dele: *"só exigir informação que muda o comportamento do vendedor ou a qualidade do forecast"* 2) corte o que é burocracia 3) mostre o que ele **ganha** ao preencher, não o que a gestão ganha 4) veja a seção "por que processo documentado não pega" abaixo |
| DP4 | O forecast não bate com a realidade | Cards sem valor preenchido, ou critério de saída frouxo deixando deal avançar cedo demais | 1) exija valor em todo card das etapas finais 2) reaudite os critérios com o teste dos dois vendedores ([guia-revisar-e-corrigir.md](../04-operacao/guia-revisar-e-corrigir.md)) |
| DP5 | Os deals ficam parados e ninguém percebe | Os gatilhos existem no documento mas não em lugar nenhum operacional | crie um lembrete semanal simples: *"quais cards não se moveram há 7 dias?"*. Não precisa de automação pra isso |
| DP6 | O playbook ficou desatualizado em 3 meses | É o destino de todo playbook sem cadência | agende a revisão trimestral **agora**, no calendário, com o dono nomeado. *"Um playbook estático é pior que não ter playbook: passa segurança falsa"* |
| DP7 | Estou perdendo deal pro concorrente e não sei por quê | Motivo da perda não está sendo categorizado | torne o motivo obrigatório na saída. Sem ele, *"80 perdidos, 1 venda"* não tem leitura nenhuma |
| DP8 | Não sei o que levar pra Aula 2 | Falta clareza do handoff | leve os 5 documentos do fluxo principal: as **etapas** viram os estágios do CRM, e a **régua de comunicação** vira a especificação das automações e templates de mensagem |
| DP9 | Rodei tudo mas meu negócio ainda não vende | A Aula 1 resolve o processo, não a aquisição | processo comercial sem lead entrando não vende. A captação é o Cohort de Marketing — veja [guia-os-tres-funis.md](../02-conhecimento-minimo/guia-os-tres-funis.md) |

**Se nada resolver:** leve o caso pro PS de tira-dúvidas do cohort, com o documento em mãos e o ponto específico que travou.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | nomeie os donos, leve as etapas pra uma planilha e ligue a gravação das calls — os três hoje, em menos de 1 hora |
| 📖 Ler | os três guias que detalham a operação do dia a dia: [gatilhos-e-cards-parados](guia-gatilhos-e-cards-parados.md) · [onboarding-e-pos-venda](guia-onboarding-e-pos-venda.md) · [metricas-do-comercial](guia-metricas-do-comercial.md) |
| 📖 Ler | quando tiver 3-5 calls gravadas, volte em [guia-insumos-reais.md](../03-insumos/guia-insumos-reais.md) e re-rode as Skills 4 e 5 |
| 🚑 Se travar | o catálogo DP1–DP9 acima, ou o [roteador de guias](../README.md) |
