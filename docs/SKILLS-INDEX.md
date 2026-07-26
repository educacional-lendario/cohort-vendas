# Índice de Skills — Aula 1 (Cohort de Vendas)

Mapa de nomes canônicos e aliases comuns, para suporte responder rápido quando o aluno digitar algo parecido mas não exato.

| Skill canônica | Aliases que o aluno pode tentar | O que faz em 1 frase |
|---|---|---|
| `/desenho-processo-comercial` | `/processo-comercial`, `/funil-de-vendas`, `/desenhar-funil`, `/etapas-de-venda` | Diagnostica o modelo de venda e desenha as etapas do funil com critério de saída verificável |
| `/qualificacao-bant-gpct` | `/bant`, `/gpct`, `/qualificacao`, `/icp`, `/qualificar-leads` | Escolhe o mix BANT/GPCT certo, monta o ICP e gera o roteiro de qualificação |
| `/discovery-script` | `/discovery`, `/script-de-discovery`, `/roteiro-de-descoberta` | Gera ou refina o script de discovery em 6 blocos (SPIN + Funil de Dor + Gap) |
| `/playbook-vendas-vivo` | `/playbook`, `/objecoes`, `/playbook-de-objecoes`, `/biblioteca-de-objecoes` | Classifica objeções em 6 tipos e monta a biblioteca de respostas com cadência de revisão |

## Ordem de dependência

`/desenho-processo-comercial` não depende de nenhuma outra. As demais funcionam standalone, mas rendem mais quando rodadas em sequência (cada uma puxa contexto da anterior, se existir):

```
desenho-processo-comercial → qualificacao-bant-gpct → discovery-script → playbook-vendas-vivo
```

## Perguntas frequentes de suporte

**"A skill pediu meu ticket/ciclo e eu não sei responder com precisão"** — normal, oriente o aluno a chutar uma faixa; todas as 4 skills recalibram o resto da conversa a partir disso, não travam esperando precisão.

**"Preciso ter gravação de call pra rodar o /discovery-script?"** — não. O Passo 0 da skill oferece 3 modos: criar do zero, refinar com call real, ou os dois. Sem call real, ela cria do zero.

**"O playbook vai ficar genérico se eu não tiver objeções reais ainda?"** — a skill avisa quando está no modo "ponto de partida a validar" (objeções típicas do nicho, não do negócio específico do aluno) — force o aluno a validar com a experiência real do time antes de tratar como definitivo.
