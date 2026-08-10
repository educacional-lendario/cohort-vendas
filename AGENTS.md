# Cohort de Vendas, instruções para o agente (Codex e afins)

Este repositório é o material do Cohort de Vendas (Academia Lendária): Aula 1 (Processo Comercial & Playbook com IA) e Aula 2 (CRM & Gestão de Pipeline com IA). O trabalho acontece por **skills**: comandos prontos que executam uma etapa do processo comercial ou de CRM.

## Onde as skills vivem

Todas as skills canônicas estão em **`.claude/skills/{nome}/SKILL.md`**. A pasta **`.agents/skills/` é um espelho literal** para o Codex (e outros agentes que leem essa convenção) carregar as mesmas skills; não edite uma sem replicar na outra. Quando o usuário digitar `@{nome}`, `/{nome}` ou pedir pela skill por extenso (ex.: "desenha meu processo comercial", "monta o playbook de objeções"), **leia o arquivo `.claude/skills/{nome}/SKILL.md` e execute-o fielmente**, do primeiro ao último passo, sem pular o Passo 0 de cada uma. Se houver dúvida entre as duas pastas, `.claude/skills/` é sempre a fonte de verdade.

A pasta **`squads/squad-sales/`** guarda um squad de referência (14 mentes de vendas e pós-venda, produzido por Fran Martins) que a skill `squad-sales-bonus` lê em tempo de execução (arquivos em `squads/squad-sales/agents/` e `squads/squad-sales/tasks/`). Essa pasta não é uma skill em si, é material que a Skill 8 da Aula 1 consulta; garanta que ela também foi copiada/clonada junto do resto do repositório, sem ela essa skill específica não tem de onde aplicar nenhum framework.

## O primeiro comando

O aluno sempre começa por **`/desenho-processo-comercial`** (`.claude/skills/desenho-processo-comercial/SKILL.md`). Não existe skill de setup separada nesta aula, a primeira skill já pergunta tudo que precisa (ticket, ciclo, decisores, B2B/B2C) antes de desenhar qualquer coisa.

## As 8 skills da Aula 1, em ordem

1. `desenho-processo-comercial`: etapas do funil com critério de saída verificável
2. `regua-comunicacao-comercial`: quem fala, o que fala, por qual canal, mecanismo único de conversão
3. `qualificacao-bant-gpct`: ICP + mix BANT/GPCT calibrado
4. `discovery-script`: script de discovery em 6 blocos, com IA
5. `playbook-vendas-vivo`: biblioteca de objeções multi-canal, viva
6. `escada-de-ofertas` (bônus): jornada entre produtos, só se o negócio tiver mais de uma oferta
7. `social-selling-comercial` (bônus): prospecção por LinkedIn/Instagram, só se rede social for canal ativo
8. `squad-sales-bonus` (bônus): acesso guiado a um squad completo de 14 mentes de pré e pós-venda, sempre contextualizado ao negócio real do aluno antes de aplicar qualquer framework

## As 3 skills da Aula 2, em ordem

1. `montagem-higiene-crm`: detecta a ferramenta de CRM do aluno (API, login web, ou planilha) e traduz o processo da Aula 1 pra estrutura real, com checklist de higiene de 8 itens
2. `lead-scoring-ia`: converte a qualificação da Aula 1 em 7 critérios de pontuação, com rollout gradual em 4 fases
3. `diagnostico-gargalos-funil`: acha o gargalo real do funil (aparente e causa), calcula receita em risco, e entrega um sistema de recuperação completo

## Regras gerais (valem em qualquer agente)

- Toda entrega sai em **dois arquivos**: `{nome-do-output}.md` e `{nome-do-output}.html`, nunca só um.
- **O HTML abre sozinho assim que é gerado** (`open arquivo.html` no Mac, `start arquivo.html` no Windows, `xdg-open arquivo.html` no Linux), nunca deixe o arquivo só salvo na pasta esperando o aluno achar. Se o comando de abrir falhar, avise o caminho exato do arquivo.
- **Toda skill atualiza a Central de Entregas** da própria aula (`central-de-entregas.html` pra Aula 1, `central-de-entregas-aula2.html` pra Aula 2, ambas na raiz do projeto do aluno, copiadas de `templates/` na primeira vez que alguma skill daquela aula terminar). Cada skill só edita a própria linha do array `ENTREGAS` (status + nomes reais dos arquivos), nunca mexe nas linhas das outras, é o que preserva o progresso acumulado entre skills.
- Se o aluno parecer perdido ou perguntar onde está, siga a seção "Se o aluno se perder" de cada `SKILL.md` (não invente uma resposta genérica).
- Se o aluno travar em algo que NÃO é o conteúdo da skill (terminal, instalação, `git clone`, "No commands match", erro de API, custo/modelo, onde ficam os arquivos, como gravar uma call), aponte o guia certo em **`guias/`** (específico da Aula 1), o roteador está em `guias/README.md`, com uma linha "Estou perdido em..." por problema. Não improvise um tutorial paralelo.
- Português do Brasil com acentuação correta. Sem emoji, sem travessão, sem tom de guru nos entregáveis.
- Nunca invente dado, caso real, ou objeção que o aluno não forneceu, quando faltar informação, pergunte ou marque como "ponto de partida a validar".
- O funil comercial (Skill 1 da Aula 1) e a escada de ofertas (Skill 6) são conceitos diferentes, nunca confundir um com o outro numa resposta.
- Social selling (Skill 7) acontece ANTES do lead entrar no funil comercial, é prospecção ativa por rede social, não substitui a régua de comunicação (Skill 2) depois que o lead responde.
- O Squad Sales (Skill 8) é bônus e nunca aplica nenhuma mente sem antes perguntar o que o aluno vende e qual das 4 dores descreve o momento dele (Passo 0.5 daquela skill), evita recomendação genérica.
- A Skill 1 da Aula 1 gera três flags que todas as skills seguintes devem herdar (perguntar de novo só se o aluno não tiver rodado a Skill 1): `nicho_regulado` (saúde/estética/finanças/jurídico/psicologia, muda a linguagem em toda mensagem, régua e resposta de objeção), `modelo` (com-vendedor/autoatendimento, muda se existe conversa 1:1 ou só toque digital) e `insumos_cohort_mkt` (sim/não + caminho da pasta, se existe offerbook/ICP do Cohort de Marketing para usar como base, em vez de recriar do zero). As três ficam em destaque no topo do `processo-comercial-{negocio}.md`.

## Se o seu agente não lê `.claude/` nem `.agents/`

Cada `SKILL.md` é um arquivo de texto autocontido, funciona como prompt colável em qualquer IA de chat (ChatGPT, Gemini, etc.), mesmo sem suporte a skills. Basta abrir o arquivo da skill desejada em `.claude/skills/{nome}/SKILL.md`, copiar o conteúdo inteiro (a partir de `# {Nome da Skill}`, sem o frontmatter YAML do topo) e colar numa conversa nova, seguido do contexto do seu negócio. Para a skill `squad-sales-bonus`, o agente também vai precisar de acesso à pasta `squads/squad-sales/` pra ler os arquivos dos mentores, sem suporte a leitura de arquivo, cole também o conteúdo do mentor relevante junto.
