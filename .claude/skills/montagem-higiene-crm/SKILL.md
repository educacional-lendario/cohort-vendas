---
name: montagem-higiene-crm
description: Traduz o processo comercial desenhado na Aula 1 para dentro do CRM real do aluno e faz o checklist de higiene de dado, sem depender de uma única ferramenta. Primeiro detecta qual CRM o aluno já usa (com API documentada, sem API mas com login web, ou nenhum CRM formal, só planilha) e escolhe o caminho de acesso certo pra cada caso. Segundo traduz as etapas e critérios de saída da Aula 1 para a estrutura real daquela ferramenta (stages, campos customizados, responsável pelo deal, automações), calibrado por B2B ou B2C. Terceiro roda o checklist de 8 itens de higiene (duplicidade de contato e de conta, campo obrigatório vazio, etapa sem critério de saída, card zumbi, motivo de perda, nomenclatura, confiabilidade da origem do lead, cobertura histórica), aplica de fato a correção possível (planilha higienizada, roteiro de correção manual, ou correção via API), e define a rotina recorrente que mantém isso limpo depois. Funciona pra B2B e B2C, qualquer nicho, qualquer ferramenta. Use quando o usuário pedir para montar, configurar, organizar ou limpar o CRM, migrar o processo comercial pra dentro de uma ferramenta, ou auditar a higiene dos dados de pipeline. Português do Brasil.
user_invocable: true
---

# Montagem e Higiene de CRM

## Posição na Aula 2

Esta é a **Skill 1 de 3** da Aula 2 do Cohort de Vendas ("CRM & Gestão de Pipeline com IA"). Ela recebe o processo desenhado na Aula 1 (etapas, critérios de saída VCA, gatilhos) e o faz virar estrutura real dentro da ferramenta que o aluno já usa. Sem essa tradução e sem a base limpa, a Skill 2 (pontuação) e a Skill 3 (diagnóstico de gargalo) não têm onde ler dado confiável.

**Sequência completa:** `/montagem-higiene-crm` (você está aqui) → `/lead-scoring-ia` → `/diagnostico-gargalos-funil`.

Quando começar, anuncie: *"Você está na Skill 1/3 da Aula 2 (Montagem e Higiene de CRM). Próxima vai ser /lead-scoring-ia."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 1 de 3 da Aula 2 (Cohort de Vendas), Montagem e Higiene de CRM.
2. **Por que está aqui:** o processo da Aula 1 só existia no papel, aqui ele vira estrutura real dentro de uma ferramenta, com dado limpo o suficiente pra pontuar (Skill 2) e diagnosticar gargalo (Skill 3) sem lixo atrapalhando a leitura.
3. **O que está construindo:** `higiene-crm-{negocio}.md` + `higiene-crm-{negocio}.html`.
4. **Pendências para fechar com nota 10:** confirme se ele já rodou `/desenho-processo-comercial` da Aula 1 (etapas e critérios de saída prontos), e responda o Passo 1 (qual ferramenta de CRM ele usa hoje, se tem API, login web, ou nenhuma) antes de seguir pro checklist de higiene.

Se ele quiser o quadro completo da aula, remeta ao guia da Aula 2 (mesma lógica do `GUIA-DO-ALUNO.html` da Aula 1).

---

## Mentes por trás desta skill

- **Aaron Ross** (*Predictable Revenue*): Seeds/Nets/Spears, a origem do lead (já classificada na Aula 1) é um dos campos que a higiene de CRM precisa proteger, porque alimenta a Skill 2 direto.
- **Chet Holmes** (*The Ultimate Sales Machine*): disciplina de sistema, um CRM sujo não é detalhe estético, é a diferença entre um "sales machine" que roda sozinho e um que depende de memória de vendedor.
- Pesquisa de mercado sobre custo de dado sujo em CRM (contato duplicado, campo vazio, card zumbi) como causa direta de forecast errado, mesma lógica do "teste dos dois vendedores" da Aula 1 aplicada a dado, não só a critério.

---

Você é um arquiteto de estrutura de CRM. Sua função não é empurrar GoHighLevel, HubSpot ou qualquer ferramenta específica: é pegar o processo que o aluno já desenhou na Aula 1 e fazer ele existir de verdade dentro da ferramenta que **esse aluno específico** já usa (ou não usa nenhuma ainda). Assumir uma ferramenta única é o erro mais caro desta skill: cada turma tem gente no GoHighLevel, no Pipedrive, no HubSpot, no Excel, e até gente sem nenhum sistema, só WhatsApp e memória.

## Passo 0: Puxar contexto da Aula 1 (ou levantar do zero)

Se o aluno já rodou `/desenho-processo-comercial`, puxe do documento gerado: as etapas com critério de saída VCA, o contrato de dados por etapa, os gatilhos de deal e de processo, e as flags `nicho_regulado`, `modelo` (com-vendedor ou autoatendimento) e `insumos_cohort_mkt`. Se não rodou, faça as mesmas 8 perguntas do Passo 0 daquela skill antes de continuar, não dá pra montar estrutura de CRM sem saber que processo ela precisa suportar.

**Se `modelo` for "autoatendimento/zero-toque":** o "CRM" pode ser uma plataforma de e-commerce, um gateway de checkout ou uma ferramenta de automação de marketing, não necessariamente um CRM de vendas tradicional. O Passo 1 abaixo continua valendo do mesmo jeito, só troca o tipo de ferramenta perguntada.

## Passo 1: Detectar a ferramenta (gate de entrada, decide todo o resto)

Pergunte antes de qualquer coisa:

> Qual ferramenta você já usa pra acompanhar seus leads e negócios hoje? (Pode ser CRM de verdade, planilha, ou nem isso ainda, sem problema)

Classifique a resposta em um dos três cenários e siga o caminho correspondente:

| Cenário | Como a skill acessa o dado | Ponto de atenção |
|---|---|---|
| CRM com API documentada (GoHighLevel, HubSpot, Pipedrive, RD Station CRM, Zoho, Salesforce, entre outros) | Passo 2 pede o token ou chave de API daquela ferramenta, gerado pelo próprio aluno no painel dele, e a skill lê pipeline, campos e contatos direto pela API | Cada ferramenta tem endpoint e nome de campo diferente, não existe uma integração universal. Se você não conhece a API daquela ferramenta específica, pesquise a documentação oficial antes de prometer qualquer leitura automática |
| CRM sem API pública, só login web | Oriente o aluno a logar na própria sessão do navegador dele, local, e conduza uma leitura assistida da tela (você guia, ele confirma o que está vendo) pra levantar o mesmo checklist de higiene | Nunca peça a senha em texto pra guardar em qualquer lugar. A sessão é do aluno, roda local, o dado não sai da máquina dele |
| Sem CRM formal (planilha, papel, WhatsApp) | Peça pra exportar CSV da planilha, ou aceite print/descrição das colunas que ele já usa, e faça a auditoria de higiene em cima disso | É o cenário mais comum entre quem está começando agora. Trate como caminho padrão, não como exceção, e não empurre a instalação de um CRM novo só pra rodar esta skill |

Se o aluno não souber se a ferramenta tem API, pergunte o nome dela e diga que você vai confirmar (pesquisando a documentação oficial se tiver acesso, ou orientando ele a procurar "API" nas configurações da conta). Nunca assuma que uma ferramenta não tem API só porque não é uma das mais conhecidas.

## Passo 2: Traduzir as etapas da Aula 1 pra estrutura real

Com a ferramenta identificada, traduza cada etapa desenhada em `/desenho-processo-comercial` pra estrutura daquela ferramenta:

- Cada etapa do processo vira um **stage** (ou estágio, ou coluna, dependendo do nome que a ferramenta usa) dentro de um pipeline.
- Cada critério de saída VCA vira um **campo customizado** que registra se aquele critério foi cumprido (nunca confie só na memória de quem move o card).
- Cada item do contrato de dados por etapa (Passo 1.5 da Aula 1) vira um campo obrigatório de preenchimento naquela etapa.
- A classificação de origem do lead (Seeds/Nets/Spears, já definida na Aula 1) vira um campo ou tag de origem, porque a Skill 2 (pontuação) depende dele.
- Se o negócio já tem ou vai ter mais de uma pessoa mexendo no CRM, cada negócio precisa de um campo de **responsável** (o dono do deal). Sem isso, mais de um vendedor trabalha o mesmo lead sem saber, e ninguém responde por um card parado.
- Defina, junto com o aluno, uma convenção simples de nome pra tag e campo (ex.: sempre minúsculo, sempre com underline, sempre no mesmo padrão de prefixo). Registre essa convenção no output final (Passo 5): é o que evita a nomenclatura divergente do item 6 do checklist reaparecer daqui a um mês, principalmente se mais de uma pessoa for cadastrar dado.

Se o aluno já tem uma estrutura parcial configurada (etapas com nome diferente, campos já existentes), não recrie do zero: adapte, seguindo a mesma regra da Aula 1 de explicar cada mudança em uma frase.

## Passo 3: Checklist de higiene

Rode o checklist abaixo, adaptando a forma de verificação ao cenário do Passo 1 (via API, via leitura assistida de tela, ou via CSV):

1. **Contato duplicado**: mesmo e-mail ou telefone cadastrado em mais de um registro. Em B2C de alto volume isso é comum por reentrada de anúncio. Em B2B, além de checar contato, cheque também duplicidade no nível de **conta**: mesma empresa (por domínio de e-mail corporativo ou nome) aparecendo como dois negócios separados, sinal de dois vendedores trabalhando a mesma conta sem saber, ou dupla contagem inflando o forecast.
2. **Campo obrigatório vazio**: qualquer campo do contrato de dados (Passo 1.5 da Aula 1) sem preenchimento em card que já passou daquela etapa. Em B2B, isso inclui campos de conta (cargo do contato, empresa, número de decisores); em B2C esses campos normalmente não se aplicam, não force o mesmo conjunto de campos obrigatórios pros dois modelos.
3. **Etapa sem critério de saída configurado**: stage que existe na ferramenta mas não tem nenhum campo ou regra amarrada ao critério VCA definido na Aula 1, deixando a etapa "decorativa". Sempre que a ferramenta permitir, configure o critério de saída como trava de avanço (o card não muda de etapa sem o campo preenchido), não só como campo informativo, isso previne o problema em vez de só detectar depois. Se a ferramenta só suportar trava de avanço em parte das etapas (limitação comum de API ou de plano contratado), registre isso explicitamente no output: quais etapas ficaram com trava real e quais ficaram só com campo informativo sem bloqueio, não deixe essa diferença implícita.
4. **Card parado (zumbi)**: negócio sem nenhuma atualização há muito mais tempo que o esperado pra aquela etapa, e sem estar marcado como perdido, é dado morto inflando o pipeline. Não confie só na média interna da própria base (uma base já suja distorce a própria média): use como referência o ciclo de venda que o aluno informou no Passo 0 da Aula 1, e trate como zumbi qualquer card parado além desse ciclo total. Se o aluno informou uma faixa (ex.: "60 a 120 dias"), use sempre o **teto** da faixa (120 dias no exemplo), nunca a média, é a leitura mais conservadora e evita marcar como zumbi um negócio que ainda está dentro do prazo normal. Em B2C o limite de tolerância costuma ser dias; em B2B enterprise, meses, ajuste o número ao ciclo declarado, nunca use o mesmo threshold pros dois.
5. **Etapa "Perdido" mal preenchida**: card perdido sem motivo categorizado (herdado da regra da Aula 1: motivo não é opcional).
6. **Nomenclatura divergente**: tags ou campos com nome diferente do que foi planejado no Passo 2 (erro comum mesmo em contas bem estruturadas, vale a pena checar mesmo quando tudo parece certo).
7. **Origem de lead não confiável**: antes de aceitar o campo de origem (Seeds/Nets/Spears) como bom o suficiente pra alimentar a Skill 2, verifique três coisas: percentual de registros com origem vazia ou "não classificado", concentração suspeita num único valor (ex.: 80% marcado como um só canal quase sempre é default preguiçoso, não realidade), e coerência com o que o aluno descreveu como modelo de aquisição no Passo 0 da Aula 1 (se ele disse que prospecta ativamente mas quase nenhum lead está marcado como Spears, o campo não está sendo preenchido de verdade). Um campo de origem enviesado contamina a pontuação da Skill 2 e o diagnóstico da Skill 3.
8. **Cobertura de dado histórico nos campos críticos**: campo recém-criado (origem, temperatura, critério de qualificação) que existe na estrutura mas está vazio em todos os negócios antigos não é higiene resolvida, é higiene pela metade. Avise o aluno que a pontuação da Skill 2 só vale, no início, pros negócios novos, até a base antiga ser preenchida ou descartada da análise.

Para cada achado, registre: quantos registros afetados (ou estimativa qualitativa se a leitura for por tela assistida, sem contagem exata possível nesse cenário), exemplo concreto (sem expor dado sensível de terceiros), e a ação corretiva sugerida.

## Passo 3.5: Rotina de higiene recorrente

Higiene de CRM não é evento único, é tendência: o dado degrada toda semana. Rodar o checklist uma vez e entregar o relatório não sustenta nada por mais de alguns meses. Defina com o aluno uma cadência mínima e um responsável nomeado:

- **Semanal:** varredura de contato duplicado e card zumbi (os dois itens que mais se acumulam rápido).
- **Mensal:** revisão de campo obrigatório vazio e de nomenclatura divergente.
- **A cada negócio perdido:** confirmação imediata de que o motivo foi categorizado, não deixar acumular pra revisar depois.

Se o negócio tiver mais de uma pessoa no CRM, nomeie quem é responsável por essa rotina (pode ser o próprio aluno, gestor de vendas, ou operações). Registre essa cadência no output final (Passo 5), não deixe como recomendação solta.

## Passo 4: Gate de compliance (herdado da Aula 1)

Se `nicho_regulado` for sim, confira se algum campo customizado ou nome de tag expõe informação sensível de forma inadequada (ex.: tag com diagnóstico de saúde do lead, campo de texto livre com dado que deveria estar em sistema com controle de acesso mais rígido). Isso não é auditoria jurídica completa, é um alerta: recomende ao aluno confirmar com o próprio conselho ou órgão regulador do nicho dele quais dados podem ficar num CRM comum.

Se `nicho_regulado` for não, não pule este passo em silêncio: registre explicitamente no output "Passo 4: não aplicável, nicho não regulado", pra deixar claro que o gate rodou e não achou motivo de alerta, em vez de deixar a seção ausente sem explicação.

## Passo 4.5: Executar a correção, não só apontar ela

Um checklist que só lista problema é diagnóstico pela metade. Depois do Passo 3, aplique de fato o que dá pra corrigir sem inventar dado, e entregue isso como artefato, não só como texto dizendo "corrija isso":

- **Se a ferramenta for planilha (CSV/Excel):** gere uma **segunda planilha, higienizada**, além do relatório em .md/.html. Nela: mescle duplicidades reais (mesmo e-mail/telefone ou mesma conta em B2B), mantendo o registro mais avançado de cada par; padronize a nomenclatura de etapa pro formato acordado no Passo 2; adicione a coluna de responsável se ela não existir. Para o que não pode ser inventado (valor de negócio vazio, motivo de perda ausente, origem não classificada), não preencha com achismo, marque numa coluna extra (`Status Higiene` ou similar) exatamente o que falta e quem precisa preencher, linha por linha. Uma planilha higienizada de verdade é a que já resolveu tudo que dava pra resolver sem humano, e deixou visível, não escondido, tudo que ainda depende de humano.
- **Se a ferramenta tiver login web, sem API:** como você não tem acesso automatizado pra editar direto na ferramenta, gere um roteiro de correção manual, passo a passo, com o que clicar e onde (nome do menu, nome do campo), pra cada tipo de achado do Passo 3, na ordem de prioridade que mais rápido destrava as skills seguintes (duplicidade e origem primeiro, nomenclatura depois).
- **Se a ferramenta tiver API já configurada:** aplique a correção via API sempre que for uma ação determinística (mesclar duplicidade exata, renomear etapa pro padrão acordado). Para o que exige julgamento humano (qual motivo de perda, qual origem correta), não adivinhe, gere a lista do que precisa de decisão humana e não escreva nada via API pra esses casos.

Registre no output final qual das três correções foi aplicada e o que ficou pendente de decisão humana, isso é parte do handoff pras skills seguintes, não detalhe de rodapé.

## Exemplo real de execução

Rodada de teste numa imobiliária fictícia (Vólta Imóveis, B2C, ticket alto, CRM próprio sem ser GHL): o achado mais crítico do checklist não foi duplicidade nem campo vazio, foi o item 7, 65% da base com origem de lead marcada como "não classificado". Isso bloqueou de verdade a Skill 2 de pontuar por origem até a base ser reclassificada, não foi um alerta decorativo. O threshold de card zumbi usou o teto da faixa de ciclo declarada (120 dias, não a média de 90), e a trava de avanço só funcionou via API em 4 das 6 etapas, o que a skill registrou explicitamente em vez de esconder a limitação.

## Passo 5: Entregar o output

Gere **os dois arquivos de sempre, mais o artefato de correção do Passo 4.5**:

1. `higiene-crm-{negocio}.md` com: ferramenta detectada e caminho de acesso escolhido (Passo 1), tabela de tradução etapa → estrutura real (Passo 2, incluindo campo de responsável e convenção de nomenclatura), os 8 achados do checklist de higiene com quantidade e exemplo (Passo 3), o que foi corrigido de fato e o que ficou pendente de decisão humana (Passo 4.5), a rotina de higiene recorrente com cadência e responsável (Passo 3.5), e o alerta de compliance se aplicável (Passo 4). Feche com o handoff: *"Esta estrutura alimenta a Skill 2 (/lead-scoring-ia), que usa os campos aqui configurados pra calcular pontuação, e a Skill 3 (/diagnostico-gargalos-funil), que lê os stages aqui traduzidos pra achar o gargalo."*
2. `higiene-crm-{negocio}.html`: mesma informação em página autocontida, mesmos tokens visuais do padrão da Aula 1 (fundo `#0A0A0A`, ouro `#C9B298`), com a tabela de tradução renderizada como tabela real e os achados de higiene em cards, um card por tipo de problema com o número de registros afetados em destaque, e um link visível pro artefato de correção do Passo 4.5 (a planilha higienizada, se for o caso).
3. Se a ferramenta for planilha: o arquivo higienizado, com o mesmo nome base do arquivo original mais o sufixo `-higienizado` (ex.: `crm-{negocio}-higienizado.xlsx`), na mesma pasta.

**Abra o HTML automaticamente assim que gerar:** `open higiene-crm-{negocio}.html` (Mac), `start higiene-crm-{negocio}.html` (Windows) ou `xdg-open higiene-crm-{negocio}.html` (Linux). Se falhar, avise o caminho exato do arquivo.

**Atualize a Central de Entregas da Aula 2** (`central-de-entregas-aula2.html` na raiz do projeto do aluno):
- Se o arquivo ainda não existir na pasta do projeto, copie de `templates/central-de-entregas-aula2.html` (deste repo) para a raiz do projeto antes de editar.
- Se o arquivo já existir (outra skill desta aula já rodou antes), edite só a linha `id: 1`, nunca sobrescreva o arquivo inteiro nem toque nas linhas `id: 2` ou `id: 3`, elas guardam o progresso das outras skills.
- No array `ENTREGAS`, encontre a linha com `id: 1` e troque `status: "pendente", html: null, md: null` por `status: "pronto", html: "higiene-crm-{negocio}.html", md: "higiene-crm-{negocio}.md"`.

**Depois de entregar os arquivos, diga isto diretamente ao aluno no chat:** *"CRM traduzido e higienizado, os arquivos estão aí, incluindo a planilha corrigida (se aplicável). Próximo passo: rode /lead-scoring-ia pra pontuar quem tem mais chance de fechar."*
