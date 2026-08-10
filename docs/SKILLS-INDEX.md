# Índice de Skills, Aula 1 (Cohort de Vendas)

Mapa de nomes canônicos e aliases comuns, para suporte responder rápido quando o aluno digitar algo parecido mas não exato.

| # | Skill canônica | Aliases que o aluno pode tentar | O que faz em 1 frase |
|---|---|---|---|
| 1 | `/desenho-processo-comercial` | `/processo-comercial`, `/funil-de-vendas` (cuidado: aluno pode confundir com a Skill 6), `/desenhar-funil`, `/etapas-de-venda` | Diagnostica o modelo de venda e desenha as etapas do funil com critério de saída verificável |
| 2 | `/regua-comunicacao-comercial` | `/regua-de-comunicacao`, `/cadencia-de-mensagens`, `/follow-up`, `/quem-fala-em-cada-etapa` | Define quem fala, o que fala e por qual canal em cada etapa, com funil de reforço e mecanismo único |
| 3 | `/qualificacao-bant-gpct` | `/bant`, `/gpct`, `/qualificacao`, `/icp`, `/qualificar-leads` | Escolhe o mix BANT/GPCT certo, monta o ICP e gera o roteiro de qualificação |
| 4 | `/discovery-script` | `/discovery`, `/script-de-discovery`, `/roteiro-de-descoberta` | Gera ou refina o script de discovery em 6 blocos (SPIN + Funil de Dor + Gap) |
| 5 | `/playbook-vendas-vivo` | `/playbook`, `/objecoes`, `/playbook-de-objecoes`, `/biblioteca-de-objecoes` | Classifica objeções em 6 tipos e monta a biblioteca de respostas multi-canal com cadência de revisão |
| 6 (bônus) | `/escada-de-ofertas` | `/escada-de-produtos`, `/value-ladder`, `/jornada-de-produtos`, `/funil-de-vendas` (o nome que mais confunde com a Skill 1) | Desenha a jornada de ascensão entre produtos/ofertas, nível de portfólio, não de pipeline |
| 7 (bônus) | `/social-selling-comercial` | `/social-selling`, `/prospeccao-redes-sociais`, `/vender-por-dm`, `/linkedin-outreach` | Monta a sequência de prospecção por rede social (LinkedIn ou Instagram/TikTok) antes do lead entrar no funil comercial |
| 8 (bônus) | `/squad-sales-bonus` | `/squad-sales`, `/squad-de-vendas`, `/sales-chief`, `/mais-mentes-de-venda` | Dá acesso guiado ao Squad Sales completo (14 mentes de pré e pós-venda produzidas por Fran Martins), sempre contextualizado ao negócio do aluno antes de aplicar qualquer framework |

## Cuidado com a confusão "funil comercial" x "funil de vendas"

O aluno vai perguntar isso. Responda sempre assim: **funil comercial** (Skill 1, `/desenho-processo-comercial`) é o pipeline que acompanha o status de UM deal específico. **Escada de ofertas** (Skill 6, `/escada-de-ofertas`) é o funil de vendas do PORTFÓLIO inteiro, como o cliente sobe entre produtos diferentes ao longo do tempo. São documentos diferentes, resolvendo problemas diferentes.

## Ordem de dependência

`/desenho-processo-comercial` não depende de nenhuma outra. As demais funcionam standalone, mas rendem mais quando rodadas em sequência (cada uma puxa contexto da anterior, se existir):

```
desenho-processo-comercial → regua-comunicacao-comercial → qualificacao-bant-gpct → discovery-script → playbook-vendas-vivo → escada-de-ofertas (bônus, independente das demais) → social-selling-comercial (bônus, independente das demais, na verdade acontece ANTES da Skill 1 na prática, mas é ensinada por último) → squad-sales-bonus (bônus, o mais avançado, faz mais sentido depois de pelo menos a Skill 1 estar pronta)
```

## Perguntas frequentes de suporte

**"A skill pediu meu ticket/ciclo e eu não sei responder com precisão":** normal, oriente o aluno a chutar uma faixa; todas as skills recalibram o resto da conversa a partir disso, não travam esperando precisão.

**"Preciso ter gravação de call pra rodar o /discovery-script?":** não. O Passo 0 da skill oferece 3 modos: criar do zero, refinar com call real, ou os dois. Sem call real, ela cria do zero.

**"O playbook vai ficar genérico se eu não tiver objeções reais ainda?":** a skill avisa quando está no modo "ponto de partida a validar" (objeções típicas do nicho, não do negócio específico do aluno), force o aluno a validar com a experiência real do time antes de tratar como definitivo.

**"A /escada-de-ofertas não fez sentido pro meu caso":** normal, é bônus e só se aplica a quem tem mais de um produto/oferta em níveis diferentes. Se o aluno só tem um produto, oriente a pular esta skill.

**"Meu negócio é 100% autoatendimento, não tenho vendedor":** funciona. A Skill 1 pergunta isso no Passo 0 e trata como perfil próprio: etapas viram toques digitais (visitou, iniciou compra, comprou), gatilhos viram abandono. A Skill 4 (discovery) avisa que não se aplica nesse modelo e sugere pular direto pra Skill 5.

**"É self-service, mas eu respondo no WhatsApp quem abandona o carrinho, sou autoatendimento ou tenho vendedor?":** é a opção (b) da pergunta 5 do Passo 0, e a resposta é **autoatendimento**. A régua: olhe onde a decisão acontece. Conversa que só existe depois que o cliente já decidiu não comprar (carrinho abandonado, cartão recusado, boleto não pago) recupera pagamento, não convence ninguém. A Skill 1 registra `modelo: autoatendimento (com recuperação humana)` e a Skill 2 marca "quem atua = ambos" só no ponto de recuperação. Se o aluno responder "tem vendedor" só porque existe um WhatsApp em algum lugar, a skill desenha discovery e proposta para um produto de checkout direto, etapas que nunca vão acontecer.

**"Meu nicho é saúde/estética/finanças/jurídico/psicologia, isso muda alguma coisa?":** sim. A Skill 1 (Passo 0.5) marca a flag `nicho_regulado: sim` e todas as skills seguintes calibram a linguagem (sem "garantido"/"cura", sem depoimento de paciente/cliente em médico/psicologia/jurídico). O aluno só responde uma vez.

**"Onde eu vejo tudo que já foi entregue até agora?":** no `central-de-entregas.html`, na raiz do projeto do aluno. Aparece sozinho assim que a primeira skill termina; cada skill destrava o próprio card lá (com link pro `.md` e `.html` dela), o que ainda não rodou fica apagado. Se o aluno não encontrar esse arquivo, é sinal de que nenhuma skill terminou ainda, ou de que ele está numa pasta diferente da que rodou as skills.

**"Digitei `/desenho-processo-comercial` e apareceu 'No commands match'":** causa quase certa: o Claude Code foi aberto na pasta errada (um nível acima de onde estão as skills). Peça pro aluno rodar `ls .claude/skills` antes de abrir o `claude`, se der erro de pasta não encontrada, falta o `cd` pra dentro da pasta certa (`cohort-vendas` ou a pasta do projeto dele, se seguiu o Cenário 2 de instalação).

**"Não quero criar um projeto novo, quero usar dentro do meu projeto atual":** funciona. README e GUIA-DO-ALUNO.html (Setup, passo 1B) têm o comando: clonar numa pasta temporária, copiar só `.claude/skills/` e `.agents/skills/` pro projeto do aluno, apagar a temporária. Sem git, o caminho é baixar o ZIP do GitHub e arrastar as pastas manualmente.

**"Eu prospecto pelo Instagram/LinkedIn, tem processo pra isso?":** sim, é a Skill 7 (`/social-selling-comercial`). LinkedIn usa a sequência de Jeb Blount (5 toques em ~2 semanas); Instagram/TikTok usa o Social Selling 2.0 de Torriani (achar lead por palavra-chave, pré-aquecer, abrir sem vender, conduzir até o agendamento). Não confundir com a régua de comunicação (Skill 2), que cobre o pós-contato.

**"O aluno disse que se perdeu no meio de uma skill":** todas as 8 skills têm uma seção "Se o aluno se perder" que responde onde ele está, por que está ali, o que está construindo e o que falta para a entrega ficar 10/10. Se mesmo assim ele continuar confuso, mande abrir o `GUIA-DO-ALUNO.html` do zero.

**"O que é o Squad Sales (Skill 8)? É diferente das outras skills?":** sim, em escala. É um squad inteiro (14 mentes de vendas e pós-venda) produzido por Fran Martins fora deste cohort, trazido como bônus 3. As outras 7 skills constroem UM documento cada; a Skill 8 dá acesso guiado a um conjunto muito maior de mentores, sempre perguntando antes o que o aluno vende e qual das 4 dores ele tem agora, pra nunca aplicar framework genérico. Ela não substitui as skills 1-5, usa o material delas como base.

**"O aluno quer só uma parte do Squad Sales, não o fluxo inteiro":** normal, e a skill já é feita pra isso: o Passo 0.5 pergunta qual das 4 situações (prospecção seca, travado no meio, sangria pós-venda, ou tudo do zero) descreve o momento dele, e só roda o fluxo correspondente, não o squad inteiro de uma vez.

## Saída dupla (regra de todas as skills)

Todas as 8 skills entregam o output em **markdown + HTML** ao final, nunca só um dos dois. O HTML reaproveita os mesmos tokens visuais do `GUIA-DO-ALUNO.html` (fundo escuro, ouro de destaque) para manter consistência visual em todo o material da aula.
