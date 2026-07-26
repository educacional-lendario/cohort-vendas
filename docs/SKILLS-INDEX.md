# Índice de Skills — Aula 1 (Cohort de Vendas)

Mapa de nomes canônicos e aliases comuns, para suporte responder rápido quando o aluno digitar algo parecido mas não exato.

| # | Skill canônica | Aliases que o aluno pode tentar | O que faz em 1 frase |
|---|---|---|---|
| 1 | `/desenho-processo-comercial` | `/processo-comercial`, `/funil-de-vendas` (cuidado: aluno pode confundir com a Skill 6), `/desenhar-funil`, `/etapas-de-venda` | Diagnostica o modelo de venda e desenha as etapas do funil com critério de saída verificável |
| 2 | `/regua-comunicacao-comercial` | `/regua-de-comunicacao`, `/cadencia-de-mensagens`, `/follow-up`, `/quem-fala-em-cada-etapa` | Define quem fala, o que fala e por qual canal em cada etapa, com funil de reforço e mecanismo único |
| 3 | `/qualificacao-bant-gpct` | `/bant`, `/gpct`, `/qualificacao`, `/icp`, `/qualificar-leads` | Escolhe o mix BANT/GPCT certo, monta o ICP e gera o roteiro de qualificação |
| 4 | `/discovery-script` | `/discovery`, `/script-de-discovery`, `/roteiro-de-descoberta` | Gera ou refina o script de discovery em 6 blocos (SPIN + Funil de Dor + Gap) |
| 5 | `/playbook-vendas-vivo` | `/playbook`, `/objecoes`, `/playbook-de-objecoes`, `/biblioteca-de-objecoes` | Classifica objeções em 6 tipos e monta a biblioteca de respostas multi-canal com cadência de revisão |
| 6 (bônus) | `/escada-de-ofertas` | `/escada-de-produtos`, `/value-ladder`, `/jornada-de-produtos`, `/funil-de-vendas` (o nome que mais confunde com a Skill 1) | Desenha a jornada de ascensão entre produtos/ofertas — nível de portfólio, não de pipeline |
| 7 (bônus) | `/social-selling-comercial` | `/social-selling`, `/prospeccao-redes-sociais`, `/vender-por-dm`, `/linkedin-outreach` | Monta a sequência de prospecção por rede social (LinkedIn ou Instagram/TikTok) antes do lead entrar no funil comercial |

## Cuidado com a confusão "funil comercial" x "funil de vendas"

O aluno vai perguntar isso. Responda sempre assim: **funil comercial** (Skill 1, `/desenho-processo-comercial`) é o pipeline que acompanha o status de UM deal específico. **Escada de ofertas** (Skill 6, `/escada-de-ofertas`) é o funil de vendas do PORTFÓLIO inteiro — como o cliente sobe entre produtos diferentes ao longo do tempo. São documentos diferentes, resolvendo problemas diferentes.

## Ordem de dependência

`/desenho-processo-comercial` não depende de nenhuma outra. As demais funcionam standalone, mas rendem mais quando rodadas em sequência (cada uma puxa contexto da anterior, se existir):

```
desenho-processo-comercial → regua-comunicacao-comercial → qualificacao-bant-gpct → discovery-script → playbook-vendas-vivo → escada-de-ofertas (bônus, independente das demais) → social-selling-comercial (bônus, independente das demais — na verdade acontece ANTES da Skill 1 na prática, mas é ensinada por último)
```

## Perguntas frequentes de suporte

**"A skill pediu meu ticket/ciclo e eu não sei responder com precisão"** — normal, oriente o aluno a chutar uma faixa; todas as skills recalibram o resto da conversa a partir disso, não travam esperando precisão.

**"Preciso ter gravação de call pra rodar o /discovery-script?"** — não. O Passo 0 da skill oferece 3 modos: criar do zero, refinar com call real, ou os dois. Sem call real, ela cria do zero.

**"O playbook vai ficar genérico se eu não tiver objeções reais ainda?"** — a skill avisa quando está no modo "ponto de partida a validar" (objeções típicas do nicho, não do negócio específico do aluno) — force o aluno a validar com a experiência real do time antes de tratar como definitivo.

**"A /escada-de-ofertas não fez sentido pro meu caso"** — normal, é bônus e só se aplica a quem tem mais de um produto/oferta em níveis diferentes. Se o aluno só tem um produto, oriente a pular esta skill.

**"Meu negócio é 100% autoatendimento, não tenho vendedor"** — funciona. A Skill 1 pergunta isso no Passo 0 e trata como perfil próprio: etapas viram toques digitais (visitou, iniciou compra, comprou), gatilhos viram abandono. A Skill 4 (discovery) avisa que não se aplica nesse modelo e sugere pular direto pra Skill 5.

**"Meu nicho é saúde/estética/finanças/jurídico/psicologia, isso muda alguma coisa?"** — sim. A Skill 1 (Passo 0.5) marca a flag `nicho_regulado: sim` e todas as skills seguintes calibram a linguagem (sem "garantido"/"cura", sem depoimento de paciente/cliente em médico/psicologia/jurídico). O aluno só responde uma vez.

**"Eu prospecto pelo Instagram/LinkedIn, tem processo pra isso?"** — sim, é a Skill 7 (`/social-selling-comercial`). LinkedIn usa a sequência de Jeb Blount (5 toques em ~2 semanas); Instagram/TikTok usa o Social Selling 2.0 de Torriani (achar lead por palavra-chave, pré-aquecer, abrir sem vender, conduzir até o agendamento). Não confundir com a régua de comunicação (Skill 2), que cobre o pós-contato.

**"O aluno disse que se perdeu no meio de uma skill"** — todas as 6 skills têm uma seção "Se o aluno se perder" que responde onde ele está, por que está ali, o que está construindo e o que falta para a entrega ficar 10/10. Se mesmo assim ele continuar confuso, mande abrir o `GUIA-DO-ALUNO.html` do zero.

## Saída dupla (regra de todas as skills)

Todas as 7 skills entregam o output em **markdown + HTML** ao final, nunca só um dos dois. O HTML reaproveita os mesmos tokens visuais do `GUIA-DO-ALUNO.html` (fundo escuro, ouro de destaque) para manter consistência visual em todo o material da aula.
