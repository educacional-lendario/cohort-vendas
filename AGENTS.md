# Cohort de Vendas — instruções para o agente (Codex e afins)

Este repositório é o material da Aula 1 do Cohort de Vendas (Academia Lendária). O trabalho acontece por **skills**: comandos prontos que executam uma etapa do processo comercial.

## Onde as skills vivem

Todas as skills canônicas estão em **`.claude/skills/{nome}/SKILL.md`**. A pasta **`.agents/skills/` é um espelho literal** para o Codex (e outros agentes que leem essa convenção) carregar as mesmas skills; não edite uma sem replicar na outra. Quando o usuário digitar `@{nome}`, `/{nome}` ou pedir pela skill por extenso (ex.: "desenha meu processo comercial", "monta o playbook de objeções"), **leia o arquivo `.claude/skills/{nome}/SKILL.md` e execute-o fielmente**, do primeiro ao último passo, sem pular o Passo 0 de cada uma. Se houver dúvida entre as duas pastas, `.claude/skills/` é sempre a fonte de verdade.

## O primeiro comando

O aluno sempre começa por **`/desenho-processo-comercial`** (`.claude/skills/desenho-processo-comercial/SKILL.md`). Não existe skill de setup separada nesta aula — a primeira skill já pergunta tudo que precisa (ticket, ciclo, decisores, B2B/B2C) antes de desenhar qualquer coisa.

## As 7 skills, em ordem

1. `desenho-processo-comercial` — etapas do funil com critério de saída verificável
2. `regua-comunicacao-comercial` — quem fala, o que fala, por qual canal, mecanismo único de conversão
3. `qualificacao-bant-gpct` — ICP + mix BANT/GPCT calibrado
4. `discovery-script` — script de discovery em 6 blocos, com IA
5. `playbook-vendas-vivo` — biblioteca de objeções multi-canal, viva
6. `escada-de-ofertas` (bônus) — jornada entre produtos, só se o negócio tiver mais de uma oferta
7. `social-selling-comercial` (bônus) — prospecção por LinkedIn/Instagram, só se rede social for canal ativo

## Regras gerais (valem em qualquer agente)

- Toda entrega sai em **dois arquivos**: `{nome-do-output}.md` e `{nome-do-output}.html` — nunca só um.
- **O HTML abre sozinho assim que é gerado** (`open arquivo.html` no Mac, `start arquivo.html` no Windows, `xdg-open arquivo.html` no Linux) — nunca deixe o arquivo só salvo na pasta esperando o aluno achar. Se o comando de abrir falhar, avise o caminho exato do arquivo.
- Se o aluno parecer perdido ou perguntar onde está, siga a seção "Se o aluno se perder" de cada `SKILL.md` (não invente uma resposta genérica).
- Português do Brasil com acentuação correta. Sem emoji, sem travessão, sem tom de guru nos entregáveis.
- Nunca invente dado, caso real, ou objeção que o aluno não forneceu — quando faltar informação, pergunte ou marque como "ponto de partida a validar".
- O funil comercial (Skill 1) e a escada de ofertas (Skill 6) são conceitos diferentes — nunca confundir um com o outro numa resposta.
- Social selling (Skill 7) acontece ANTES do lead entrar no funil comercial — é prospecção ativa por rede social, não substitui a régua de comunicação (Skill 2) depois que o lead responde.
- A Skill 1 gera duas flags que todas as skills seguintes devem herdar (perguntar de novo só se o aluno não tiver rodado a Skill 1): `nicho_regulado` (saúde/estética/finanças/jurídico/psicologia — muda a linguagem em toda mensagem, régua e resposta de objeção) e `modelo` (com-vendedor/autoatendimento — muda se existe conversa 1:1 ou só toque digital).

## Se o seu agente não lê `.claude/` nem `.agents/`

Cada `SKILL.md` é um arquivo de texto autocontido — funciona como prompt colável em qualquer IA de chat (ChatGPT, Gemini, etc.), mesmo sem suporte a skills. Basta abrir o arquivo da skill desejada em `.claude/skills/{nome}/SKILL.md`, copiar o conteúdo inteiro (a partir de `# {Nome da Skill}`, sem o frontmatter YAML do topo) e colar numa conversa nova, seguido do contexto do seu negócio.
