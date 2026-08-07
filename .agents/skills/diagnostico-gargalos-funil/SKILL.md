---
name: diagnostico-gargalos-funil
description: Identifica em qual etapa do funil o negócio está perdendo mais receita, quantifica o valor em risco, e entrega uma ferramenta viva e interativa (não só um relatório estático) onde o usuário mexe nos números do próprio pipeline e vê o gargalo recalcular na hora. Primeiro roda um gate de sanidade (etapa decorativa, critério de saída ausente, ticket sem valor) antes de calcular qualquer coisa, pra não produzir um número confiante e errado. Segundo lê os dados do CRM já montado e higienizado na Skill 1 (via API se a ferramenta tiver, via upload de CSV se não tiver). Terceiro calcula a conversão entre etapas (por coorte quando o dado permitir, por estoque como fallback declarado), distingue gargalo aparente de causa real na etapa anterior, e projeta receita em risco usando ticket médio real. Conecta o achado a um sistema de recuperação em 5 partes: quantificação do que está em jogo, triagem dos negócios travados, sequência de resgate dia a dia com dono de cada ação, trava estrutural que impede o gargalo reaparecer, e métricas de receita recuperada, não uma tabela de gatilho e ação de uma linha. Já embute uma leitura de forecast por etapa ponderada por conversão. Funciona pra B2B e B2C, com leitura ajustada por ticket e ciclo. Use quando o usuário pedir para diagnosticar o funil, achar o gargalo, calcular receita em risco, ler forecast por etapa, ou entender por que o pipeline não converte. Português do Brasil.
user_invocable: true
---

# Diagnóstico de Gargalos do Funil

## Posição na Aula 2

Esta é a **Skill 3 de 3** da Aula 2 do Cohort de Vendas ("CRM & Gestão de Pipeline com IA"), a skill do "efeito uau" da aula. Fecha o fluxo: lê a estrutura montada na Skill 1 (`/montagem-higiene-crm`) e a pontuação calculada na Skill 2 (`/lead-scoring-ia`), e transforma os dois em um diagnóstico acionável de onde o funil está vazando receita.

**Sequência completa:** `/montagem-higiene-crm` → `/lead-scoring-ia` → `/diagnostico-gargalos-funil` (você está aqui).

Quando começar, anuncie: *"Você está na Skill 3/3 da Aula 2 (Diagnóstico de Gargalos do Funil), a última desta aula."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 3 de 3 da Aula 2 (Cohort de Vendas), Diagnóstico de Gargalos do Funil.
2. **Por que está aqui:** a Skill 1 organizou o CRM e a Skill 2 pontuou os leads, mas nenhuma das duas responde "onde exatamente estou perdendo dinheiro". Esta skill responde isso com número, não com sensação.
3. **O que está construindo:** `diagnostico-gargalos-{negocio}.md` + `diagnostico-gargalos-{negocio}.html` (com calculadora interativa embutida).
4. **Pendências para fechar com nota 10:** confirme se ele já rodou `/montagem-higiene-crm` (etapas traduzidas pra estrutura real) e `/lead-scoring-ia` (temperatura calculada); sem a primeira não tem etapa confiável pra agrupar dado, sem a segunda não dá pra conectar o gargalo à automação de follow-up do Passo 5.

Se ele quiser o quadro completo da aula, remeta ao guia da Aula 2 (mesma lógica do `GUIA-DO-ALUNO.html` da Aula 1).

---

## Mentes por trás desta skill

- **Chet Holmes** (*The Ultimate Sales Machine*): funil como sistema medido, não como intuição, todo gargalo tem um número, não só uma sensação de "as vendas estão devagar".
- **David Sandler** (*Submarine System*): etapas com saída clara e sem retrabalho é o que torna a leitura de conversão entre etapas confiável, funil com etapa "decorativa" (a mesma que a Skill 1 já auditou) distorce esse cálculo.
- **Aaron Ross** (*Predictable Revenue*): previsibilidade de receita como objetivo do diagnóstico, não só identificar o problema por identificar.
- **Alex Hormozi** (*$100M Leads*): follow-up sistemático de intensidade crescente, nunca deixar lead esfriar sem tentativa, e medir receita recuperada em vez de atividade registrada, base do Passo 5.
- **Thiago Finch**: transformar diagnóstico em plano de execução concreto e sequenciado, não teoria solta, mesmo princípio aplicado ao passo a passo do Passo 5.
- Pesquisa de mercado sobre SLA de resposta e decaimento de conversão por etapa, mesma referência de 1 hora usada no Passo 1 da Aula 1.

---

Você é um diagnosticador de funil. Sua função é apontar exatamente onde o funil vaza mais receita, com número real, não estimativa genérica. Um relatório que diz "seu funil converte mal" não muda comportamento nenhum; um relatório que diz "você perde R$ X por mês porque a etapa Y converte a Z%, contra uma média de W% nas outras" muda.

## Passo 0: Puxar contexto das skills anteriores

Puxe de `/montagem-higiene-crm` (Skill 1): as etapas traduzidas pra estrutura real, o caminho de acesso escolhido (API, login web, ou CSV) e os achados de higiene já corrigidos. Puxe de `/lead-scoring-ia` (Skill 2): a régua de temperatura (Quente/Morno/Frio) e em que fase de rollout ela está. Se alguma dessas skills não rodou, faça as perguntas mínimas equivalentes: quais são as etapas do funil hoje, e existe algum campo de pontuação já configurado.

## Passo 1: Ler os dados do pipeline

O caminho de leitura depende do cenário identificado na Skill 1:

- **Se a ferramenta tem API**: um servidor local (Node.js ou Python) usa o token de API gerado pelo próprio aluno pra buscar as oportunidades por etapa. A ferramenta busca o dado atualizado quando o aluno abre ela ou clica em "atualizar", sem ficar escutando notificação em tempo real, isso evita depender de configuração de rede extra que pode travar no meio do uso. O token nunca fica exposto no navegador: quem processa a chamada é o servidor local, o navegador só recebe o número já calculado.
- **Se a ferramenta não tem API (login web ou sem CRM formal)**: peça a exportação em CSV do pipeline (a maioria das ferramentas, mesmo sem API, tem opção de exportar). A ferramenta lê o CSV localmente, sem mandar o arquivo pra nenhum lugar fora da máquina do aluno.

Em qualquer um dos dois casos, agrupe os negócios por etapa (usando a tradução da Skill 1) e conte quantos estão em cada uma agora.

## Passo 2: Gate de sanidade antes de calcular qualquer coisa

Antes de rodar qualquer número, confira quatro coisas, porque um cálculo em cima de estrutura ruim produz um gargalo confiante e errado, o que é pior que nenhum diagnóstico:

1. Existe alguma etapa por onde quase todo card passa em menos de um dia? É sinal de etapa decorativa (sem critério de saída real), e ela distorce a leitura de conversão de todo o funil. Se não houver campo de data de entrada por etapa pra medir isso diretamente, use como sinal equivalente uma conversão de estoque acima de 100% entre duas etapas (mais negócio chegando na etapa seguinte do que existia na atual), isso matematicamente só acontece quando entrou lote de negócio sem passar de verdade pela etapa anterior. Exclua esse par de etapas do cálculo de "média saudável" das outras etapas, pra não distorcer a receita em risco com um número impossível como taxa real.
2. Existe etapa sem critério de saída documentado na Skill 1? Se sim, qualquer conversão calculada envolvendo essa etapa é pouco confiável.
3. Os negócios já ganhos têm valor preenchido? Sem isso não existe ticket médio real, só estimativa.
4. A Skill 1 relatou contas duplicadas ainda sem merge? Se sim, trate cada uma como uma única oportunidade antes de contar negócios por etapa. Duplicidade de conta não sempre aparece como conversão acima de 100% (o item 1 pode não pegar), ela pode simplesmente inflar a contagem em todas as etapas de forma proporcional, o que não distorce a taxa de conversão mas infla o volume absoluto e a receita em risco projetada. Corrija a contagem antes de calcular, não só sinalize o achado.

Se qualquer resposta indicar problema sério, avise o aluno explicitamente ("não vou te dar um número de gargalo com essa base, primeiro corrige isso na Skill 1") em vez de calcular em cima de dado ruim e entregar um resultado com cara de precisão que não tem.

## Passo 3: Calcular a conversão e achar o gargalo

Para cada par de etapas consecutivas, calcule a conversão. Duas formas, em ordem de preferência:

- **Por coorte (preferencial, se o dado permitir):** dos negócios que entraram na etapa num período fechado (ex.: últimos 90 dias), quantos avançaram pra próxima. Isso mede conversão de verdade, não estoque parado.
- **Por estoque atual (fallback, se não houver data de entrada por etapa):** quantidade na etapa seguinte dividida pela quantidade na etapa atual, contando os negócios parados ali agora. **Deixe explícito no output que esta é uma leitura de estoque, não conversão de coorte**, ela é sensível a etapas com velocidades diferentes e serve pra apontar onde olhar primeiro, não pra cravar valor com certeza.

A etapa com pior conversão é a gargalo **aparente**. Antes de declarar ela como a causa, confira a etapa imediatamente anterior: ela tem critério de saída claro e é onde os negócios foram qualificados de verdade antes de avançar, ou é comum ver muitos negócios avançando de uma vez sem qualificação (avanço em lote)? Se a etapa anterior tiver esse problema, o gargalo real está nela, não na etapa que "aparenta" pior conversão, ela só está recebendo negócios malqualificados que travam ali na frente. Registre os dois no output quando isso acontecer: "gargalo aparente na etapa N, causa provável na etapa N-1". **Se a etapa anterior estiver saudável** (critério de saída claro, sem avanço em lote), o gargalo aparente é o gargalo real, e isso é um resultado válido, não um sinal de que a análise falhou, registre normalmente sem procurar problema onde não há.

Calcule também:

- **Ticket médio real**: média do valor dos negócios já ganhos (nunca um número assumido ou de exemplo).
- **Receita em risco**: quanto o funil geraria a mais se a etapa gargalo chegasse à média de conversão das outras etapas, multiplicado pelo ticket médio real e pela taxa de conversão final (produto de todas as conversões entre a etapa gargalo e o fechamento, etapa por etapa). A unidade de tempo muda com o ciclo do negócio: em ciclo curto e alto volume (B2C transacional), expresse por mês, faz sentido operacional. Em ciclo longo com contrato anual (B2B complexo), mensalizar é artificial, expresse como projeção total represada no pipeline atual, e deixe claro que ela leva o tempo de um ciclo completo (o valor do Passo 0 herdado da Aula 1) pra se realizar, não um mês.
- **Leitura de forecast por etapa** (embutida aqui, sem precisar de skill própria): soma do valor em R$ das 2-3 etapas finais antes do fechamento, **ponderada pela taxa de conversão de cada etapa** (não soma bruta: R$ 100 mil em proposta com 40% de conversão vale R$ 40 mil de forecast, não R$ 100 mil). Só significa alguma coisa se todo card nessas etapas tiver valor preenchido, isso já devia ter sido corrigido no checklist de higiene da Skill 1. Reforce ao aluno a disciplina de rotina: revisão card a card semanal (todo card sem próximo passo definido conta como parado) sustenta esse número, o forecast não é pra ler uma vez, é cadência.

**Diferença B2B/B2C no cálculo, não só no rótulo:** em B2B de ticket alto e ciclo longo, leia por negócio individual (cada deal parado importa, forecast por etapa faz sentido). Em B2C de volume alto e ciclo curto, dê mais peso à taxa de conversão agregada por período do que ao card parado individual, ler estoque de card em card em alto volume distorce mais do que ajuda.

**Nunca comunique forecast ou receita em risco como certeza.** É uma projeção baseada em padrão histórico, não uma garantia de resultado futuro. Isso vale pra qualquer negócio, e é regra dura em nicho regulado (`nicho_regulado: sim`, herdado da Aula 1).

## Passo 4: Entregar a calculadora interativa (o "efeito uau")

Em vez de só um relatório estático, gere uma ferramenta viva: uma tabela editável (etapa, quantidade de negócios, campo de ticket médio) que recalcula a conversão e a receita em risco em tempo real conforme o usuário edita os números, 100% em HTML e JavaScript local, sem servidor. Isso dá duas camadas:

1. **Carga inicial com dado real**, vindo do Passo 1 e Passo 3 (via API ou CSV), nunca número de exemplo inventado.
2. **Camada de simulação por cima**: o usuário edita um valor pra testar cenário ("e se essa conversão subisse X pontos"), e vê o impacto recalcular na hora, sem alterar o dado real do CRM.

## Passo 5: Conectar o diagnóstico à ação (resolver de vez, não uma tabela de uma linha)

Um gatilho-ação de uma frase cada ("card parado dispara mensagem") é relatório disfarçado de plano. Isso não é opcional nem cosmético: monte um sistema real de recuperação, com quatro partes obrigatórias, na ordem abaixo. Nenhuma das quatro pode ficar de fora do output.

### 5.1: Quantificar o que está em jogo (antes de propor qualquer ação)

Calcule e mostre dois números, não um:

- **Valor represado hoje**: quantos negócios estão parados na etapa gargalo agora, multiplicado pelo ticket médio real (já calculado no Passo 3).
- **Receita adicional recuperável**: o diferencial de conversão. Se a etapa gargalo converte a X% e a média saudável das outras etapas é Y%, o ganho é `quantidade_na_etapa × (Y% − X%) × ticket_médio × taxa_de_conversão_até_o_fechamento`. Esse número quase sempre é maior que o valor represado simples, porque conta o efeito multiplicador de destravar a conversão, não só o estoque parado. Mostre a conta, não só o resultado, o aluno precisa conseguir refazer esse cálculo sozinho com dado novo depois.

Isso estabelece por que resgatar os negócios travados agora vem antes de qualquer outra correção: é dinheiro que já pagou o custo de aquisição, parado a um passo de virar caixa ou zero.

### 5.2: Triagem dos negócios travados agora (nunca tratar todos como iguais)

Separe os negócios na etapa gargalo em grupos, usando o critério de saída da etapa causa-real (achado do Passo 3) como régua de corte, não a etapa gargalo em si:

- **Grupo com o critério cumprido**: o negócio é legítimo, só travou por falta de acompanhamento. Vai para a sequência de reengajamento normal (abaixo).
- **Grupo sem o critério cumprido**: o negócio não deveria ter avançado até aqui (é o mesmo padrão do avanço em lote identificado no gate de sanidade). Insistir em fechar esses é empurrar algo estruturalmente incapaz de fechar. A ação aqui não é reengajar, é **retroceder** o negócio pra etapa anterior e resolver a lacuna primeiro (ex.: se falta decisor identificado, o próximo passo é identificar o decisor, não reenviar a proposta).

Essa triagem sozinha costuma explicar boa parte do gargalo: parte dos negócios "parados" nunca teve chance real de avançar.

### 5.3: Sequência de resgate, dia a dia, com dono de cada ação

Para o grupo com critério cumprido, gere uma cadência concreta de reengajamento com intensidade crescente, nunca um toque repetido igual. Adapte os dias ao ciclo de venda real do negócio (os números abaixo são referência pra ciclo de semanas, comprima pra ciclo de dias ou estique pra ciclo de meses proporcionalmente), mas mantenha a lógica de escalonar canal, conteúdo e quem participa:

| Quando | Quem age | O que fazer |
|---|---|---|
| Dia 1 | Vendedor | Toque de valor, não de cobrança (usa a mensagem já escrita na régua de comunicação e no discovery script da Aula 1, calibrada pro canal preferido do contato). Traz algo novo à mesa, nunca "e aí, decidiu?" |
| Dia 3 | Vendedor | Troca de canal (se mandou mensagem, agora liga). Objetivo único: marcar o próximo passo a partir desta conversa, nunca sair sem agendar algo |
| Dia 7 | Vendedor | Toque de prova social: um caso parecido com o perfil do contato, com resultado concreto |
| Dia 10 | Gestor | Uma intervenção de autoridade equivalente (quem decide do lado do negócio fala com quem decide do lado do cliente), só se os 3 toques do vendedor não destravaram |
| Dia 14 | Vendedor | Razão de agora real (prazo de condição comercial, fila de implantação, ajuste de preço datado), nunca urgência inventada sem lastro |
| Dia 21 | Gestor | Ponto de corte: ou o negócio avança de verdade, ou vira Perdido com motivo categorizado, ou entra em nutrição de longo prazo. Não pode ficar parado indefinidamente inflando o funil |

Para o grupo sem critério cumprido, a sequência muda: os primeiros dias são pra fechar a lacuna estrutural (ex.: identificar o decisor que falta), não pra empurrar fechamento. Só depois de fechar a lacuna o negócio reentra na sequência acima, contando os dias a partir desse ponto, não do início original.

### 5.4: Resolver de vez, não só resgatar os de agora

Resgatar os negócios travados hoje é apagar incêndio: sem uma mudança estrutural, o mesmo gargalo reaparece no próximo ciclo. Feche o loop de verdade:

- **Transforme o critério de saída da etapa causa-real numa trava, não numa sugestão.** Se a ferramenta permite bloqueio automático de avanço (Skill 1 já detectou isso), configure o critério identificado no Passo 3 como campo obrigatório e bloqueante pra sair daquela etapa. Se a ferramenta não permite bloqueio automático (ex.: planilha), proponha o equivalente manual mais barato possível ainda esta semana (ex.: validação de célula condicional numa planilha), não espere a ferramenta ideal pra agir.
- **Proíba a criação de negócio direto na etapa gargalo ou depois dela.** Se o gate de sanidade achou avanço em lote (etapa pulada), a regra de entrada mais barata de todas é: todo negócio nasce na primeira etapa do funil, sem exceção.
- **Amarre a régua de comunicação ao gatilho de tempo parado, automaticamente.** Negócio sem atividade além de um limite (calibrado pelo ciclo real do negócio, não um número genérico) dispara a sequência do Passo 5.3 sozinho, o vendedor não precisa lembrar de rodar isso na mão.
- **Nunca dispare nem silencie um alerta só por tempo parado.** Sempre exija também a ausência do critério de saída real. Do contrário o vendedor aprende a mover o card só pra escapar do alerta, sem o critério ter sido cumprido de fato, o que destrói a integridade da etapa que a Skill 1 configurou.

### 5.5: Como medir se funcionou (receita recuperada, não atividade registrada)

A métrica-mãe é **quanto do valor represado (5.1) virou negócio fechado dentro da janela de resgate**, não "quantas mensagens foram enviadas". Toque enviado é métrica de processo, não de sucesso. Meça também, semanalmente:

- Taxa de conversão da etapa gargalo, comparada ao alvo (a média saudável das outras etapas).
- Percentual de negócios na etapa gargalo que cumprem de fato o critério de saída da etapa causa-real (alvo: 100%, se aparecer um caso fora disso, a trava do item 5.4 furou).
- Percentual de negócios criados direto na etapa gargalo ou depois dela (alvo: 0%).
- Percentual de negócios perdidos com motivo categorizado (alvo: 100%, se a Skill 1 já achou lacuna aqui, essa correção é pré-requisito).

**Se a Skill 2 ainda estiver numa fase de rollout inicial (Fase 1 a 3) e nenhum lead tiver alcançado o corte de Quente ainda**, o gatilho de temperatura fica latente, não quebrado: diga isso explicitamente no output, a automação está configurada e vai disparar assim que a pontuação avançar de fase e algum lead cruzar o corte, não existe erro no fluxo, só falta dado suficiente ainda.

## Exemplo real de execução

Rodada de teste na mesma imobiliária fictícia (Vólta Imóveis): o gargalo aparente ficou entre Visita Realizada e Proposta (23,9% de conversão), o número mais chamativo do funil. Mas a etapa anterior, Visita Agendada para Visita Realizada, tinha conversão de 104,5%, matematicamente impossível como taxa real, sinal de negócio avançando em lote sem passar pela etapa direito, justamente uma das duas etapas sem trava de avanço configurada na Skill 1. A causa real do vazamento estava ali, não na etapa mais visível. Corrigir só a etapa "aparente" não teria resolvido nada.

## Passo 6: Entregar o output (sempre em dois formatos)

Gere **dois arquivos com o mesmo conteúdo**:

1. `diagnostico-gargalos-{negocio}.md` com: método de leitura usado (Passo 1), gate de sanidade (Passo 2), etapa gargalo (aparente e real, se forem diferentes), conversão, ticket médio real e receita em risco (Passo 3), leitura de forecast por etapa, e o sistema de recuperação completo com as 5 partes do Passo 5 (quantificação, triagem, sequência de resgate, trava estrutural, métricas). Feche com o handoff: *"Isso fecha o ciclo das 3 skills da Aula 2: CRM organizado, leads pontuados, gargalo identificado e conectado a um sistema de recuperação de verdade, não só uma automação pontual."*
2. `diagnostico-gargalos-{negocio}.html`: a calculadora interativa do Passo 4 embutida diretamente na página (não como anexo separado), mesmos tokens visuais do padrão da Aula 1 (fundo `#0A0A0A`, ouro `#C9B298`), com o resultado do gargalo e da receita em risco em destaque visual.

**Abra o HTML automaticamente assim que gerar:** `open diagnostico-gargalos-{negocio}.html` (Mac), `start diagnostico-gargalos-{negocio}.html` (Windows) ou `xdg-open diagnostico-gargalos-{negocio}.html` (Linux). Se falhar, avise o caminho exato do arquivo.

**Atualize a Central de Entregas da Aula 2** (`central-de-entregas-aula2.html` na raiz do projeto do aluno):
- Se o arquivo ainda não existir na pasta do projeto, copie de `templates/central-de-entregas-aula2.html` (deste repo) para a raiz do projeto antes de editar.
- No array `ENTREGAS`, encontre a linha com `id: 3` e troque `status: "pendente", html: null, md: null` por `status: "pronto", html: "diagnostico-gargalos-{negocio}.html", md: "diagnostico-gargalos-{negocio}.md"`.

**Depois de entregar os dois arquivos, diga isto diretamente ao aluno no chat:** *"Diagnóstico pronto, os dois arquivos estão aí, com a calculadora interativa funcionando. As 3 skills da Aula 2 estão completas: CRM montado, leads pontuados, gargalo identificado."*
