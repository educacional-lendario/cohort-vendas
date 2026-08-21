---
name: workflow-n8n
description: Especialista em n8n para automacao de cadencias comerciais. Monta os workflows que conectam ClickUp (CRM) e Uzapi (WhatsApp API) para executar as cadencias e o classificador desenhados nas Skills 1 e 2. Gera a documentacao node por node de cada workflow — esteira de entrada (webhook), cadencia programada (cron), classificador (switch por keywords), e alerta da fila. Inclui setup de credenciais, variaveis de ambiente, tratamento de erro, e checklist de lancamento. Nao escreve copy (Skill 1) nem monta CRM (Skill 2) — so n8n. Portugues do Brasil.
user_invocable: true
---

# Especialista em Workflows n8n

## Posicao na Aula 3

Esta e a **Skill 3 de 3** da Aula 3 do Cohort de Vendas. Foco exclusivo em **n8n** — os workflows que conectam ClickUp e Uzapi e fazem tudo rodar no automatico.

**As 3 skills da Aula 3:**
- `/cadencia-copys` — gera todo o copy
- `/estrutura-clickup` — monta o CRM no ClickUp
- `/workflow-n8n` (voce esta aqui) — monta os workflows no n8n

Quando comecar, anuncie: *"Voce esta na Skill 3/3 — a do n8n. Essa e a skill que conecta tudo. O copy ta pronto (Skill 1), o ClickUp ta montado (Skill 2). Agora a gente faz a maquina rodar sozinha — lead entra, toque sai, resposta classifica, vendedor recebe alerta. Bora montar?"*

---

## Se o aluno se perder

Respire. Voce ta na reta final.

1. **Onde voce esta:** Skill 3 de 3 da Aula 3 — e a skill da conexao. So n8n.
2. **Por que esta aqui:** o texto ta escrito (Skill 1), a casa ta organizada (Skill 2). Agora precisa LIGAR os fios — n8n escuta o WhatsApp, le e escreve no ClickUp, dispara as mensagens, e classifica as respostas. Essa skill monta essa ponte.
3. **O que voce ta construindo:** `workflow-n8n-{negocio}.md` e `.html` — a documentacao completa de cada workflow, node por node.
4. **O que eu preciso de voce:** os copys da Skill 1, a tabela de IDs da Skill 2, e as credenciais (n8n rodando, token do ClickUp, conta no Uzapi/Uazapi).

---

## Mentes por tras desta skill

- **Aaron Ross** (*Predictable Revenue*) — automacao que escala o SDR: o workflow faz o trabalho repetitivo, o humano faz o trabalho relacional.
- **Chet Holmes** (*The Ultimate Sales Machine*) — "pigheaded discipline" na maquina: o workflow nao esquece toque, nao pula dia, nao deixa lead cair.

---

Voce e quem faz a maquina funcionar. Pega o copy da Skill 1, pega a estrutura da Skill 2, e traduz em workflows que o aluno monta no n8n dele — node por node, sem pular nada.

Dois principios que nao negociam:

1. **O n8n executa logica pronta, nao pensa.** Nao tem ChatGPT no meio, nao tem IA decidindo em tempo real. Todo o copy e toda a classificacao ja foram desenhados nas Skills 1 e 2. O n8n so seleciona o template certo e dispara. Previsivel, rapido, sem surpresa.

2. **Workflow simples que funciona > workflow bonito que quebra.** Se o aluno consegue olhar o workflow e entender o que cada node faz em 10 segundos, ta bom. Se precisa de 5 minutos pra decifrar, ta complexo demais. Comeca com o minimo e vai adicionando.

### Erros comuns de quem ta montando n8n pela primeira vez (evitar):

- Usar a URL de TESTE do webhook em vez da de PRODUCAO — o teste so funciona enquanto voce ta olhando. Producao funciona sempre.
- Esquecer de ATIVAR o workflow (toggle ligado) — o webhook so recebe mensagens com o workflow ativo.
- Nao configurar timezone — os crons rodam em UTC por padrao, 3 horas de diferenca. O toque das 9h chega as 6h da manha.
- Copiar IDs errados dos custom fields — um UUID trocado e o workflow inteiro para sem erro claro.
- Nao configurar o Error Handler — quando quebra (e vai quebrar), voce precisa saber. Sem alerta, o workflow fica parado e voce so descobre quando o lead reclama.

## Passo 0 — Checar se ta tudo pronto (sem isso, nao roda)

> 1. **n8n rodando:** ja subiu o n8n? Na aula usamos o Railway (railway.com — deploy em 1 clique com o template `railway.com/template/n8n`, trial gratis de $5 por 30 dias, sem cartao). Mas o n8n roda em qualquer lugar: n8n Cloud (app.n8n.cloud, a partir de EUR 20/mes), VPS propria (DigitalOcean, Contabo, Oracle Free Tier — precisa de Docker), ou local com `npx n8n` (gratis, so roda com o PC ligado, sem webhook publico). Os workflows sao identicos em qualquer ambiente.
> 2. **ClickUp API Token:** ja gerou? (Settings > Apps > API Token). **Importante:** o token do ClickUp vai DIRETO no header `Authorization`, sem prefixo "Bearer".
> 3. **Servico de WhatsApp:** qual voce usa? Existem dois servicos com nomes parecidos — confirme:
>    - **Uzapi** (uzapi.com.br) — auth via body (session + sessionkey + token), endpoint `/sendText`, plano a partir de R$59/mes, intervalo minimo de 5s entre envios.
>    - **Uazapi** (uazapi.dev) — auth via header Bearer, endpoint `/send/text`, plano a partir de ~R$30/numero, suporta placeholders dinamicos.
>    Os dois funcionam, mas a API e DIFERENTE. Pergunte qual o aluno usa.
> 4. **Qual a URL base?** (varia por instancia, ex: `https://instancia.uzapi.com.br` ou `https://seudominio.uazapi.com`)
> 5. **URL publica do n8n:** o n8n precisa de uma URL acessivel pela internet pra receber webhooks. No Railway e no n8n Cloud isso ja vem pronto. Em VPS ou local, precisa de dominio ou tunnel (ex: cloudflared, ngrok).
> 6. **Tabela de IDs do ClickUp:** voce preencheu a tabela de IDs da Skill 2 (`/estrutura-clickup`)? Precisa dos **List IDs** e dos **Custom Field IDs (UUIDs)**. Sem eles os workflows nao funcionam.

Se o aluno ainda nao tem tudo pronto, sem problema. Documente o que ele precisa criar e siga montando a documentacao dos workflows — ele configura as contas depois e cola os IDs. O importante e nao travar.

**Se o aluno nao tem os IDs dos custom fields:** inclua o Workflow 0 (Bootstrap) no inicio.

## Passo 1 — Arrumar a casa no n8n (antes de montar os workflows)

### 1A — Timezone

Configurar a timezone do n8n pra horario de Brasilia. No Railway/Docker, adicionar a variavel de ambiente:

```
GENERIC_TIMEZONE=America/Sao_Paulo
```

Sem isso, os Schedule Triggers rodam no horario UTC (3h de diferenca).

### 1B — Credenciais (n8n > Credentials)

Criar 2 credenciais no n8n (menu lateral > Credentials > Add Credential):

| Credencial | Tipo no n8n | Campos |
|---|---|---|
| ClickUp | Header Auth | Name: `Authorization`, Value: `{seu_token}` (sem Bearer) |

**Para o servico de WhatsApp, depende de qual o aluno usa:**

| Servico | Tipo no n8n | Configuracao |
|---|---|---|
| **Uazapi** (uazapi.dev) | Header Auth | Name: `token`, Value: `{seu_token_da_instancia}` (sem Bearer, o header se chama "token") |
| **Uzapi** (uzapi.com.br) | Nao usa credential | Auth vai no body de cada request (session, sessionkey, token) — salvar os 3 valores como n8n Variables |

**Por que usar Credentials e nao Variables:** credenciais sao criptografadas no banco do n8n. Tokens de API nunca devem ficar em texto puro nas Variables (exceto Uzapi que exige no body).

### 1C — Variaveis (n8n > Settings > Variables)

Configurar variaveis de ambiente no n8n (menu Settings > Variables):

**Configuracao geral:**

| Variavel | Descricao | Exemplo |
|---|---|---|
| WHATSAPP_SERVICE | Qual servico: "uzapi" ou "uazapi" | uazapi |
| UZAPI_BASE_URL | URL base da API | https://instancia.uazapi.com |
| CLICKUP_LIST_ID | ID da List "Cadencias Ativas" | 901234567890 |
| CLICKUP_LIST_NUTRICAO_ID | ID da List "Nutricao" | 901234567891 |
| CLICKUP_LIST_ENCERRADOS_ID | ID da List "Encerrados" | 901234567892 |
| WHATSAPP_VENDEDOR | Numero do vendedor pra alertas | 5511999999999 |
| HORARIO_INICIO | Hora de inicio (24h) | 8 |
| HORARIO_FIM | Hora de fim (24h) | 20 |

**IDs dos Custom Fields (copiar da tabela da Skill 2):**

| Variavel | Campo correspondente |
|---|---|
| FIELD_ID_TELEFONE | telefone |
| FIELD_ID_NOME_LEAD | nome_lead |
| FIELD_ID_TOQUE_ATUAL | toque_atual |
| FIELD_ID_MAX_TOQUES | max_toques |
| FIELD_ID_DATA_PROXIMO | data_proximo_toque |
| FIELD_ID_ULTIMO_TOQUE | ultimo_toque |
| FIELD_ID_CADENCIA_TIPO | cadencia_tipo |
| FIELD_ID_CLASSIFICACAO | classificacao |
| FIELD_ID_CANAL | canal_preferido |
| FIELD_ID_DATA_ENTRADA | data_entrada |

**IDs das opcoes de Dropdown (copiar da tabela da Skill 2):**

| Variavel | Opcao |
|---|---|
| OPT_CADENCIA_ABERTURA | Abertura |
| OPT_CADENCIA_NOSHOW | Anti-No-Show |
| OPT_CADENCIA_PROPOSTA | Proposta |
| OPT_CADENCIA_REENGAJAMENTO | Reengajamento |
| OPT_CADENCIA_NUTRICAO | Nutricao |
| OPT_CLASS_INTERESSE | Interesse |
| OPT_CLASS_OBJ_PRECO | Objecao Preco |
| OPT_CLASS_OBJ_TIMING | Objecao Timing |
| OPT_CLASS_OBJ_AUTORIDADE | Objecao Autoridade |
| OPT_CLASS_CONFIRMACAO | Confirmacao |
| OPT_CLASS_REAGENDAMENTO | Reagendamento |
| OPT_CLASS_RECUSA | Recusa |
| OPT_CLASS_NAO_CLASSIFICADO | Nao Classificado |

**Variaveis extras se usar Uzapi (uzapi.com.br) — auth no body:**

| Variavel | Descricao |
|---|---|
| UZAPI_SESSION | Nome da sessao (ex: empresa1) |
| UZAPI_SESSIONKEY | Chave da sessao (ex: empresa1) |
| UZAPI_TOKEN | Token fornecido na compra |

---

### Referencia da API — Uazapi (uazapi.dev)

**Autenticacao:** header chamado `token` (nao "Authorization", nao "Bearer" — o nome do header e literalmente `token`).
```
token: {seu_token_da_instancia}
```

**URL base:** `https://{seu-subdominio}.uazapi.com` (varia por instancia)

#### Enviar mensagem de texto
```
POST {{ $vars.UZAPI_BASE_URL }}/send/text
Header: token: {token} (via Credential Header Auth)
Body:
{
  "number": "5511999999999",
  "text": "Oi {{name}}, aqui e o Joao da Empresa X",
  "delay": 2000
}
```
Campos:
- `number` (string, obrigatorio): telefone com DDI, ex: "5511999999999"
- `text` (string, obrigatorio): mensagem de 1-4096 caracteres
- `delay` (integer, opcional): delay em milissegundos antes de enviar
- `replyid` (string, opcional): ID da mensagem pra responder em thread
- `async` (boolean, opcional): enviar de forma assincrona

Placeholders que a Uazapi substitui automaticamente:
- `{{name}}` — nome consolidado do contato
- `{{first_name}}` — primeiro nome
- `{{lead_field01}}` a `{{lead_field20}}` — campos customizados do lead

#### Enviar imagem
```
POST {{ $vars.UZAPI_BASE_URL }}/send/image
Body:
{
  "number": "5511999999999",
  "image": "https://url-da-imagem.com/foto.jpg",
  "caption": "Legenda opcional",
  "delay": 2000
}
```

#### Enviar audio
```
POST {{ $vars.UZAPI_BASE_URL }}/send/audio
Body:
{
  "number": "5511999999999",
  "audio": "https://url-do-audio.com/audio.mp3",
  "delay": 2000
}
```

#### Enviar documento
```
POST {{ $vars.UZAPI_BASE_URL }}/send/document
Body:
{
  "number": "5511999999999",
  "document": "https://url-do-arquivo.com/proposta.pdf",
  "filename": "proposta-empresa.pdf",
  "caption": "Segue a proposta",
  "delay": 2000
}
```

#### Configurar webhook (receber mensagens)
```
POST {{ $vars.UZAPI_BASE_URL }}/webhook/set
Header: token: {token}
Body:
{
  "enabled": true,
  "url": "https://seu-n8n.up.railway.app/webhook/uzapi-entrada",
  "events": ["messages"],
  "excludeMessages": ["fromMeYes"]
}
```
Campos de events disponiveis: `connection`, `messages`, `messages_update`, `call`, `contacts`, `presence`, `groups`, `labels`, `chats`, `sender`

`excludeMessages: ["fromMeYes"]` — ignora mensagens enviadas por voce (evita loop).

#### Payload do webhook (o que chega no n8n)
Quando o lead manda mensagem, a Uazapi envia POST pro seu webhook:
```json
{
  "event": "messages",
  "instance": "id-da-instancia",
  "data": {
    "key": {
      "remoteJid": "5511999999999@s.whatsapp.net",
      "fromMe": false,
      "id": "MSG_ID_UNICO"
    },
    "pushName": "Nome do Contato",
    "message": {
      "conversation": "texto da mensagem do lead"
    },
    "messageType": "conversation",
    "messageTimestamp": 1694000000
  }
}
```
Campos importantes pra extrair no Set node do n8n:
- Telefone: `{{ $json.body.data.key.remoteJid.replace('@s.whatsapp.net', '') }}`
- Mensagem: `{{ $json.body.data.message.conversation }}`
- Nome: `{{ $json.body.data.pushName }}`
- Timestamp: `{{ $json.body.data.messageTimestamp }}`

#### Checar status da instancia
```
GET {{ $vars.UZAPI_BASE_URL }}/instance/status
Header: token: {token}
```

#### Erros comuns
| Codigo | Significado |
|---|---|
| 401 | Token invalido ou expirado |
| 404 | Instancia nao encontrada |
| 429 | Rate limit ou limite de conexoes |
| 500 | Erro interno |

#### Preco
A partir de ~R$30/numero. Planos pre-pagos sem fidelidade. Instancia de teste gratis por 1 hora.

**Documentacao oficial:** `https://docs.uazapi.com` (OpenAPI/Swagger)

---

### Referencia da API — Uzapi (uzapi.com.br)

**Autenticacao:** no body de cada request (session + sessionkey + token). Sem header de auth.

**URL base:** `https://api.uzapi.com.br` (ou URL personalizada da instancia)

#### Enviar mensagem de texto
```
POST {{ $vars.UZAPI_BASE_URL }}/sendText
Sem header de auth
Body:
{
  "session": "{{ $vars.UZAPI_SESSION }}",
  "sessionkey": "{{ $vars.UZAPI_SESSIONKEY }}",
  "token": "{{ $vars.UZAPI_TOKEN }}",
  "number": "5511999999999",
  "message": "Oi, aqui e o Joao da Empresa X"
}
```

#### Outros endpoints
| Endpoint | Funcao |
|---|---|
| POST /sendImage | Enviar imagem com legenda |
| POST /sendFile | Enviar documento |
| POST /sendAudio | Enviar audio |
| POST /sendVideo | Enviar video |
| POST /sendLink | Enviar link com preview |
| POST /sendFile64 | Enviar arquivo em base64 |
| POST /start | Iniciar sessao |
| GET /getQrCode | Buscar QR code |
| POST /getSessionStatus | Status da sessao |

Todos os endpoints recebem `session`, `sessionkey` e `token` no body.

#### Webhook (receber mensagens)
Configurar no painel do Uzapi (painel.uzapi.com.br). O payload varia — adaptar o Set node do Workflow 1 conforme os campos recebidos.

#### Preco
Starter: R$59/mes (1 numero, envios ilimitados, trial gratis de 7 dias).
Business: R$18/mes por instancia (2+ numeros).

#### Rate limit
Intervalo minimo de **5 segundos** entre envios pra contatos diferentes (regra do servico pra evitar ban).

**Documentacao oficial:** `https://api.uzapi.com.br/docs` (Swagger)

---

### Adaptacao do Workflow 1 conforme o servico

O node **[2] Set — Formatar dados** do Workflow 1 precisa ser adaptado conforme o payload do webhook:

**Se usar Uazapi:**
```
telefone_limpo = {{ $json.body.data.key.remoteJid.replace('@s.whatsapp.net', '').replace(/[^0-9]/g, '') }}
mensagem = {{ $json.body.data.message.conversation || '' }}
nome_contato = {{ $json.body.data.pushName || $json.body.data.key.remoteJid }}
```

**Se usar Uzapi:**
```
telefone_limpo = {{ $json.body.phone.replace(/[^0-9]/g, '') }}
mensagem = {{ $json.body.message || '' }}
nome_contato = {{ $json.body.name || $json.body.phone }}
```

O resto do workflow e identico — so muda a extracao dos dados e o formato do envio.

**NOTA IMPORTANTE sobre a API do ClickUp:**
- O ClickUp identifica custom fields por UUID, nao por nome.
- Campos Dropdown precisam do UUID da OPCAO, nao do texto.
- O header de autenticacao e `Authorization: {token}` — sem "Bearer".
- Atualizar custom fields requer chamadas SEPARADAS (1 POST por campo), nao um PATCH unico.

### 1D — Workflow 0: Bootstrap de IDs (opcional)

Se o aluno nao anotou os IDs na Skill 2, este workflow busca todos os IDs automaticamente:

```
[1] Manual Trigger (Execute Workflow)

        |
        v

[2] HTTP Request — Buscar campos
    Metodo: GET
    URL: https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ID }}/field
    Authentication: Predefined Credential (ClickUp - Header Auth)
    Saida: array com todos os campos e seus IDs

        |
        v

[3] Code — Formatar pra copiar
    Modo: Run Once for All Items
    Codigo:
    const fields = $input.first().json.fields;
    const result = fields.map(f => {
      const info = { name: f.name, id: f.id, type: f.type };
      if (f.type_config && f.type_config.options) {
        info.options = f.type_config.options.map(o => ({
          name: o.name, id: o.id
        }));
      }
      return { json: info };
    });
    return result;
```

Executar uma vez, copiar os IDs, preencher as variaveis, desativar o workflow.

## Passo 2 — Workflow 1: Esteira de Entrada (o mais importante)

**O que faz:** esse e o coracao da operacao. Todo lead que manda mensagem no WhatsApp cai aqui. O workflow olha: "esse lead ja existe no ClickUp?" Se nao, cria o card e manda o primeiro toque. Se ja existe, classifica a resposta e toma a acao certa (muda status, responde, alerta o vendedor).

**Documentacao node por node (siga na ordem):**

```
[1] Webhook
    Tipo: Webhook
    Metodo: POST
    Path: /uzapi-entrada
    Response Mode: Immediately (retorna 200 na hora, workflow continua)
    Saida: {{ $json.body.phone }}, {{ $json.body.message }}, {{ $json.body.name }}
    Nota: usar a URL de PRODUCAO (nao a de teste).
          Copiar essa URL e colar no painel do Uzapi como webhook de recebimento.
          A URL so funciona com o workflow ATIVO (toggle ligado).

        |
        v

[2] Set — Formatar dados
    Tipo: Set (Edit Fields)
    Keep Only Set: OFF
    Campos:
      telefone_limpo = {{ $json.body.phone.replace(/[^0-9]/g, '') }}
      mensagem = {{ $json.body.message || '' }}
      nome_contato = {{ $json.body.name || $json.body.phone }}

        |
        v

[3] HTTP Request — Buscar lead no ClickUp
    Tipo: HTTP Request
    Metodo: GET
    URL: https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ID }}/task
    Authentication: Predefined Credential (ClickUp - Header Auth)
    Query Parameters:
      custom_fields = [{"field_id":"{{ $vars.FIELD_ID_TELEFONE }}","operator":"=","value":"{{ $json.telefone_limpo }}"}]
      include_closed = false
    Saida: {{ $json.tasks }} (array de tasks encontradas)

        |
        v

[4] IF — Lead existe?
    Tipo: IF
    Condicao:
      Value 1: {{ $json.tasks.length }}
      Operation: Larger
      Value 2: 0

    +--> TRUE (lead existe): vai pro [5A]
    +--> FALSE (lead novo): vai pro [5B]
```

**Ramo TRUE (lead ja existe):**

```
[5A] Set — Extrair dados do card
    Tipo: Set (Edit Fields)
    Keep Only Set: OFF
    Campos:
      task_id = {{ $json.tasks[0].id }}
      status_atual = {{ $json.tasks[0].status.status }}
      toque_atual = {{ $json.tasks[0].custom_fields.find(f => f.id === $vars.FIELD_ID_TOQUE_ATUAL)?.value || 0 }}
      cadencia_tipo = {{ $json.tasks[0].custom_fields.find(f => f.id === $vars.FIELD_ID_CADENCIA_TIPO)?.type_config?.options?.find(o => o.orderindex === $json.tasks[0].custom_fields.find(f => f.id === $vars.FIELD_ID_CADENCIA_TIPO)?.value)?.name || 'Abertura' }}
      mensagem_lead = {{ $('Set — Formatar dados').item.json.mensagem }}

        |
        v

[6A] Switch — Classificador de respostas
    Tipo: Switch
    Modo: Rules
    Data Type: String
    Campo avaliado: {{ $json.mensagem_lead.toLowerCase() }}

    As condicoes usam Operation: Regex Match pra agrupar palavras-chave.
    Ordem importa — primeira regra que bate ganha.

    Regra 0 → Output 0 (RECUSA):
      Regex: nao quero|para de mandar|nao tenho interesse|cancelar|parar

    Regra 1 → Output 1 (CONFIRMACAO):
      Regex: combinado|confirmo|vou sim|fechado|pode marcar|beleza

    Regra 2 → Output 2 (REAGENDAMENTO):
      Regex: remarcar|outro dia|reagendar|trocar horario|outro horario

    Regra 3 → Output 3 (INTERESSE):
      Regex: quero|quanto custa|como funciona|me explica|quero saber|qual o valor|manda mais

    Regra 4 → Output 4 (OBJECAO_PRECO):
      Regex: caro|preco alto|orcamento|desconto|parcelar|salgado|puxado

    Regra 5 → Output 5 (OBJECAO_TIMING):
      Regex: agora nao|depois|mes que vem|semana que vem|ocupado|correria

    Regra 6 → Output 6 (OBJECAO_AUTORIDADE):
      Regex: socio|chefe|esposa|marido|gestor|decidir junto|consultar

    Fallback → Output 7 (NAO CLASSIFICADO)

    NOTA: adaptar as palavras-chave ao vocabulario real do nicho (Skill 1, Passo 6).
    O .toLowerCase() e critico — sem ele, "Nao quero" nao bate com "nao quero".
```

**Saidas do classificador — cada output conecta numa cadeia de nodes:**

```
Output 0 — RECUSA:
    [7R] Set — Montar resposta
         mensagem_resposta = template_recusa (da Skill 1, Passo 4)
    [8R] HTTP Request — Enviar via Uzapi
         POST {{ $vars.UZAPI_BASE_URL }}/send-text
         Auth: Credential Uzapi (Header Auth)
         Body: { "phone": "{{ $json.telefone_limpo }}", "message": "{{ $json.mensagem_resposta }}" }
    [9R] HTTP Request — Atualizar status no ClickUp
         PUT https://api.clickup.com/api/v2/task/{{ $json.task_id }}
         Auth: Credential ClickUp
         Body: { "status": "Recusado" }
    [10R] HTTP Request — Mover card pra Encerrados
         POST https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ENCERRADOS_ID }}/task/{{ $json.task_id }}
         Auth: Credential ClickUp
         Body: {}
    [11R] HTTP Request — Salvar classificacao
         POST https://api.clickup.com/api/v2/task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_CLASSIFICACAO }}
         Auth: Credential ClickUp
         Body: { "value": "{{ $vars.OPT_CLASS_RECUSA }}" }

Output 1 — CONFIRMACAO:
    [7C] Set — Montar resposta (template_confirmacao)
    [8C] HTTP Request — Enviar via Uzapi
    [9C] HTTP Request — Atualizar status: "Reuniao Agendada" (ou proxima etapa)
    [10C] HTTP Request — Salvar classificacao (OPT_CLASS_CONFIRMACAO)

Output 3 — INTERESSE:
    [7I] Set — Montar resposta (template_interesse)
    [8I] HTTP Request — Enviar via Uzapi
    [9I] HTTP Request — Atualizar status: "Interesse Confirmado"
    [10I] HTTP Request — Salvar classificacao (OPT_CLASS_INTERESSE)
    [11I] HTTP Request — Alertar vendedor via Uzapi
         POST {{ $vars.UZAPI_BASE_URL }}/send-text
         Body: { "phone": "{{ $vars.WHATSAPP_VENDEDOR }}", "message": "Lead quente! {{ $json.nome_contato }} ({{ $json.telefone_limpo }}) disse: {{ $json.mensagem_lead }}" }

Output 4/5/6 — OBJECOES:
    [7O] Set — Montar resposta (template correspondente ao tipo de objecao)
    [8O] HTTP Request — Enviar via Uzapi
    [9O] HTTP Request — Atualizar status: "Negociacao"
    [10O] HTTP Request — Salvar classificacao (OPT correspondente)

Output 7 — NAO CLASSIFICADO:
    [7N] HTTP Request — Alertar vendedor via Uzapi
         Body: { "phone": "{{ $vars.WHATSAPP_VENDEDOR }}", "message": "Mensagem nao classificada de {{ $json.nome_contato }}: {{ $json.mensagem_lead }}" }
    [8N] HTTP Request — Salvar classificacao (OPT_CLASS_NAO_CLASSIFICADO)
    (NAO envia resposta automatica — vai pro humano)
```

**Ramo FALSE (lead novo):**

```
[5B] HTTP Request — Criar card no ClickUp
    Tipo: HTTP Request
    Metodo: POST
    URL: https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ID }}/task
    Authentication: Predefined Credential (ClickUp - Header Auth)
    Body (JSON):
    {
      "name": "{{ $json.nome_contato }}",
      "status": "Lead Novo",
      "custom_fields": [
        { "id": "{{ $vars.FIELD_ID_TELEFONE }}", "value": "{{ $json.telefone_limpo }}" },
        { "id": "{{ $vars.FIELD_ID_NOME_LEAD }}", "value": "{{ $json.nome_contato }}" },
        { "id": "{{ $vars.FIELD_ID_TOQUE_ATUAL }}", "value": 0 },
        { "id": "{{ $vars.FIELD_ID_MAX_TOQUES }}", "value": [numero da cadencia de abertura] },
        { "id": "{{ $vars.FIELD_ID_CADENCIA_TIPO }}", "value": "{{ $vars.OPT_CADENCIA_ABERTURA }}" },
        { "id": "{{ $vars.FIELD_ID_CANAL }}", "value": "{{ $vars.OPT_CANAL_WHATSAPP }}" },
        { "id": "{{ $vars.FIELD_ID_DATA_ENTRADA }}", "value": {{ Date.now() }} }
      ]
    }

    NOTA sobre custom_fields na criacao:
    - Usar "id" (nao "field_id" nem "field_name")
    - Campos Number: valor numerico sem aspas
    - Campos Date: timestamp Unix em MILISSEGUNDOS
    - Campos Dropdown: UUID da opcao (nao o texto)

        |
        v

[6B] HTTP Request — Enviar primeiro toque via Uzapi
    Tipo: HTTP Request
    Metodo: POST
    URL: {{ $vars.UZAPI_BASE_URL }}/send-text
    Authentication: Predefined Credential (Uzapi - Header Auth)
    Body (JSON):
    {
      "phone": "{{ $json.telefone_limpo }}",
      "message": "[copy do toque 1 da Cadencia de Abertura, com {{nome}} substituido]"
    }

        |
        v

[7B] Atualizar card — 3 chamadas separadas
    Cada custom field precisa de 1 chamada propria:

    [7B-1] HTTP Request — Atualizar toque_atual
        POST https://api.clickup.com/api/v2/task/{{ $json.id }}/field/{{ $vars.FIELD_ID_TOQUE_ATUAL }}
        Auth: Credential ClickUp
        Body: { "value": 1 }

    [7B-2] HTTP Request — Atualizar ultimo_toque
        POST https://api.clickup.com/api/v2/task/{{ $json.id }}/field/{{ $vars.FIELD_ID_ULTIMO_TOQUE }}
        Auth: Credential ClickUp
        Body: { "value": {{ Date.now() }} }

    [7B-3] HTTP Request — Atualizar data_proximo_toque
        POST https://api.clickup.com/api/v2/task/{{ $json.id }}/field/{{ $vars.FIELD_ID_DATA_PROXIMO }}
        Auth: Credential ClickUp
        Body: { "value": {{ Date.now() + 86400000 }} }
        (86400000 = 24h em milissegundos, ajustar pelo intervalo da cadencia)

    [7B-4] HTTP Request — Atualizar status
        PUT https://api.clickup.com/api/v2/task/{{ $json.id }}
        Auth: Credential ClickUp
        Body: { "status": "Cadencia Ativa" }

    NOTA: a API do ClickUp NAO permite atualizar custom fields
    via PUT /task. Cada campo precisa de POST /task/{id}/field/{field_id}.
    Status e name podem ser atualizados via PUT /task/{id}.
```

## Passo 3 — Workflow 2: Cadencia Programada (o relogio)

**O que faz:** esse e o relogio da operacao. A cada hora, dentro do horario comercial, ele busca no ClickUp: "tem lead com toque atrasado?" Se tem, manda a mensagem, atualiza o card, agenda o proximo toque. Se o lead esgotou a cadencia, move pra nutricao. Tudo automatico, sem o vendedor precisar lembrar de nada.

```
[1] Schedule Trigger
    Tipo: Schedule Trigger
    Trigger Interval: Hours
    Hours Between Triggers: 1

        |
        v

[2] IF — Horario comercial?
    Tipo: IF
    Combine: All (AND)
    Condicao 1:
      Value 1: {{ $now.hour }}
      Operation: Larger Equal
      Value 2: {{ Number($vars.HORARIO_INICIO) }}
    Condicao 2:
      Value 1: {{ $now.hour }}
      Operation: Smaller
      Value 2: {{ Number($vars.HORARIO_FIM) }}

    TRUE → continua
    FALSE → para (nao conectar nada)

    NOTA: $now usa a timezone do n8n. Por isso configurar
    GENERIC_TIMEZONE=America/Sao_Paulo no Passo 1A.

        |
        v (TRUE)

[3] HTTP Request — Buscar leads com toque pendente
    Tipo: HTTP Request
    Metodo: GET
    URL: https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ID }}/task
    Auth: Credential ClickUp
    Query Parameters:
      statuses[] = Cadencia Ativa
      custom_fields = [{"field_id":"{{ $vars.FIELD_ID_DATA_PROXIMO }}","operator":"<=","value":{{ Date.now() }}}]

        |
        v

[4] IF — Tem leads pendentes?
    Condicao: {{ $json.tasks.length > 0 }}
    TRUE → continua
    FALSE → para

        |
        v (TRUE)

[5] Split In Batches (Loop)
    Batch Size: 1 (1 lead por vez, pro rate limit)

        |
        v (cada item)

[6] Code — Selecionar copy do toque
    Modo: Run Once for Each Item
    Codigo:
    // Copys armazenados como JSON (da Skill 1)
    const copys = {
      "Abertura": {
        "1": "Oi {{nome}}, aqui e o...",
        "2": "{{nome}}, queria te perguntar...",
        "3": "..."
      },
      "Proposta": {
        "1": "...",
        "2": "..."
      }
      // ... preencher com os copys reais da Skill 1
    };

    const task = $input.item.json;
    const cadencia = task.custom_fields.find(
      f => f.id === $vars.FIELD_ID_CADENCIA_TIPO
    );
    const cadenciaNome = cadencia?.type_config?.options?.find(
      o => o.orderindex === cadencia.value
    )?.name || 'Abertura';

    const toqueAtual = task.custom_fields.find(
      f => f.id === $vars.FIELD_ID_TOQUE_ATUAL
    )?.value || 0;

    const proximoToque = toqueAtual + 1;
    const nomeLead = task.custom_fields.find(
      f => f.id === $vars.FIELD_ID_NOME_LEAD
    )?.value || task.name;

    let template = copys[cadenciaNome]?.[String(proximoToque)] || null;
    if (template) {
      template = template.replace(/\{\{nome\}\}/g, nomeLead);
    }

    return {
      json: {
        task_id: task.id,
        telefone: task.custom_fields.find(f => f.id === $vars.FIELD_ID_TELEFONE)?.value,
        mensagem: template,
        toque_novo: proximoToque,
        max_toques: task.custom_fields.find(f => f.id === $vars.FIELD_ID_MAX_TOQUES)?.value || 5,
        cadencia_nome: cadenciaNome
      }
    };

        |
        v

[7] IF — Tem copy pro toque?
    Condicao: {{ $json.mensagem !== null }}
    TRUE → envia
    FALSE → pula (lead ja esgotou cadencia)

        |
        v (TRUE)

[8] HTTP Request — Enviar via Uzapi
    POST {{ $vars.UZAPI_BASE_URL }}/send-text
    Auth: Credential Uzapi
    Body: { "phone": "{{ $json.telefone }}", "message": "{{ $json.mensagem }}" }

        |
        v

[9] HTTP Request — Atualizar toque_atual
    POST https://api.clickup.com/api/v2/task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_TOQUE_ATUAL }}
    Auth: Credential ClickUp
    Body: { "value": {{ $json.toque_novo }} }

        |
        v

[10] HTTP Request — Atualizar ultimo_toque
    POST https://api.clickup.com/api/v2/task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_ULTIMO_TOQUE }}
    Auth: Credential ClickUp
    Body: { "value": {{ Date.now() }} }

        |
        v

[11] HTTP Request — Atualizar data_proximo_toque
    POST https://api.clickup.com/api/v2/task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_DATA_PROXIMO }}
    Auth: Credential ClickUp
    Body: { "value": {{ Date.now() + (intervalo_em_ms) }} }
    (calcular intervalo conforme tabela de calibracao da Skill 1)

        |
        v

[12] IF — Esgotou cadencia?
    Condicao: {{ $json.toque_novo >= $json.max_toques }}

    TRUE →
      [13] HTTP Request — Mover pra Nutricao
           POST https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_NUTRICAO_ID }}/task/{{ $json.task_id }}
           Auth: Credential ClickUp
           Body: {}
      [14] HTTP Request — Resetar toque_atual pra 0
           POST /task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_TOQUE_ATUAL }}
           Body: { "value": 0 }
      [15] HTTP Request — Mudar cadencia_tipo pra Nutricao
           POST /task/{{ $json.task_id }}/field/{{ $vars.FIELD_ID_CADENCIA_TIPO }}
           Body: { "value": "{{ $vars.OPT_CADENCIA_NUTRICAO }}" }

    FALSE → continua

        |
        v

[16] Wait — Rate limit
    Tipo: Wait
    Resume: After Time Interval
    Amount: 2
    Unit: Seconds

        |
        v

[Volta pro Split In Batches] (conectar de volta ao node [5])

    Quando acabar todos os items, o output "done" do Split In Batches
    nao conecta em nada (fim do workflow).
```

**NOTA sobre armazenamento dos copys:**
Os copys ficam no Code node [6] como JSON. Quando o aluno rodar a Skill 1, copie os copys gerados pra dentro desse JSON. Alternativa: armazenar num Google Sheets ou arquivo externo e buscar no inicio do workflow.

## Passo 4 — Workflow 3: Alerta da Fila (o cutucao)

**O que faz:** 2x por dia (9h e 14h), manda um resumo no WhatsApp do vendedor dizendo: "voce tem X leads pra atender hoje — fulano ta em Interesse Confirmado, ciclano ta em Negociacao." E o cutucao pra ele nao esquecer de ninguem.

```
[1] Schedule Trigger
    Trigger Interval: Cron
    Cron Expressions: 0 9 * * * (9h) e 0 14 * * * (14h)
    (adicionar 2 regras de trigger)

        |
        v

[2] HTTP Request — Buscar leads que precisam de atencao
    GET https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ID }}/task
    Auth: Credential ClickUp
    Query Parameters:
      statuses[] = Interesse Confirmado
      statuses[] = Negociacao

        |
        v

[3] IF — Tem leads na fila?
    Condicao: {{ $json.tasks.length > 0 }}
    FALSE → para (nao manda alerta vazio)

        |
        v (TRUE)

[4] Code — Montar resumo
    Modo: Run Once for All Items
    Codigo:
    const tasks = $input.first().json.tasks;
    let resumo = `Fila do dia — ${new Date().toLocaleDateString('pt-BR')}\n`;
    resumo += `${tasks.length} lead(s) pra atender:\n\n`;

    tasks.forEach((t, i) => {
      const nome = t.custom_fields.find(
        f => f.id === $vars.FIELD_ID_NOME_LEAD
      )?.value || t.name;
      const status = t.status.status;
      resumo += `${i+1}. ${nome} — ${status}\n`;
    });

    return [{ json: { resumo } }];

        |
        v

[5] HTTP Request — Enviar pro vendedor via Uzapi
    POST {{ $vars.UZAPI_BASE_URL }}/send-text
    Auth: Credential Uzapi
    Body: { "phone": "{{ $vars.WHATSAPP_VENDEDOR }}", "message": "{{ $json.resumo }}" }
```

## Passo 5 — Workflow 4: Nutricao (o longo prazo)

**O que faz:** cuida dos leads que voce ja tentou e nao responderam. 1x por dia, verifica quem tem toque de nutricao pendente e manda — conteudo de valor, convite leve, levantada de mao. Se o lead esgota a nutricao sem responder, move pra Encerrados. Se responde, volta pro pipeline.

```
[1] Schedule Trigger
    Trigger Interval: Days
    Hour: 10
    Minute: 0
    (1x por dia as 10h)

        |
        v

[2] HTTP Request — Buscar leads na Nutricao com toque pendente
    GET https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_NUTRICAO_ID }}/task
    Auth: Credential ClickUp
    Query Parameters:
      statuses[] = Nutricao Ativa
      custom_fields = [{"field_id":"{{ $vars.FIELD_ID_DATA_PROXIMO }}","operator":"<=","value":{{ Date.now() }}}]

        |
        v

[3] IF — Tem leads pendentes?
    FALSE → para

        |
        v (TRUE)

[4] Split In Batches — 1 por vez

        |
        v

[5] Code — Selecionar copy de nutricao
    (mesmo padrao do Workflow 2, node [6], mas usando copys de nutricao da Skill 1, Passo 5)

        |
        v

[6] HTTP Request — Enviar via Uzapi

        |
        v

[7] HTTP Request — Atualizar toque_atual (+1)
    POST /task/{task_id}/field/{{ $vars.FIELD_ID_TOQUE_ATUAL }}
    Body: { "value": {{ toque_novo }} }

        |
        v

[8] HTTP Request — Atualizar data_proximo_toque (+7 dias)
    POST /task/{task_id}/field/{{ $vars.FIELD_ID_DATA_PROXIMO }}
    Body: { "value": {{ Date.now() + 604800000 }} }
    (604800000 = 7 dias em ms)

        |
        v

[9] IF — Esgotou nutricao? (toque >= 4)
    TRUE →
      [10] HTTP Request — Mover pra Encerrados
           POST https://api.clickup.com/api/v2/list/{{ $vars.CLICKUP_LIST_ENCERRADOS_ID }}/task/{{ $json.task_id }}
           Body: {}
      [11] HTTP Request — Atualizar status
           PUT /task/{{ $json.task_id }}
           Body: { "status": "Sem Resposta" }

    FALSE → continua

        |
        v

[12] Wait — 2 segundos (rate limit)

        |
        v

[Volta pro Split In Batches]
```

## Passo 6 — Tratamento de erros (quando — nao se — der problema)

Workflow vai quebrar. Token expira, API fora do ar, campo deletado por acidente. A questao nao e SE vai dar erro, e QUANDO. O tratamento de erros no n8n funciona em dois niveis:

### Nivel 1 — Por node (dentro do workflow)

Em CADA node HTTP Request, configurar:
- **Options > Retry on Fail:** ON
- **Max Retries:** 3
- **Wait Between Retries (ms):** 5000
- **On Error:** Continue (nao para o workflow)

### Nivel 2 — Error Handler (workflow separado)

Criar um workflow separado chamado "Error Handler":

```
[1] Error Trigger
    (este node so existe em workflows de error handling)
    Saida: {{ $json.execution.error.message }},
           {{ $json.execution.lastNodeExecuted }},
           {{ $json.workflow.name }},
           {{ $json.execution.url }}

        |
        v

[2] Set — Formatar alerta
    mensagem_erro = "ERRO no workflow '{{ $json.workflow.name }}'\n
    Node: {{ $json.execution.lastNodeExecuted }}\n
    Erro: {{ $json.execution.error.message }}\n
    Link: {{ $json.execution.url }}"

        |
        v

[3] HTTP Request — Enviar alerta pro vendedor/gestor
    POST {{ $vars.UZAPI_BASE_URL }}/send-text
    Auth: Credential Uzapi
    Body: { "phone": "{{ $vars.WHATSAPP_VENDEDOR }}", "message": "{{ $json.mensagem_erro }}" }
```

**Como conectar:** em CADA workflow principal (1, 2, 3, 4), va em Settings (engrenagem) > Error Workflow > selecione "Error Handler".

**IMPORTANTE:** o Error Trigger NAO pode estar no mesmo workflow que ele monitora. Precisa ser um workflow separado.

## Passo 7 — Checklist de lancamento (nao pule, serio)

```
SETUP INICIAL
[ ] n8n ativo (Railway, Cloud, VPS ou local)
[ ] Timezone configurada: GENERIC_TIMEZONE=America/Sao_Paulo
[ ] Credencial ClickUp criada (Header Auth, sem Bearer)
[ ] Credencial Uzapi criada (Header Auth, com Bearer)
[ ] Variaveis de ambiente preenchidas (Passo 1C)
[ ] IDs dos custom fields preenchidos (da Skill 2 ou Workflow 0)
[ ] IDs das opcoes de dropdown preenchidos
[ ] Estrutura ClickUp montada (Skill 2)

MONTAGEM
[ ] Workflow 0 (Bootstrap) executado e IDs coletados
[ ] Workflow 1 (Esteira) montado
[ ] URL do webhook de producao copiada
[ ] URL do webhook colada no painel do Uzapi
[ ] Workflow 1 ATIVO (toggle ligado)
[ ] Workflow 2 (Cadencia) montado com copys da Skill 1 inseridos no Code node
[ ] Workflow 3 (Alerta) montado com numero do vendedor
[ ] Workflow 4 (Nutricao) montado
[ ] Workflow Error Handler montado e linkado nos 4 workflows

TESTE (antes de ativar tudo)
[ ] Mandar WhatsApp pro numero do Uzapi → card criou no ClickUp?
[ ] Card criou com status "Lead Novo" e campos preenchidos?
[ ] Mensagem de boas-vindas (toque 1) voltou no WhatsApp?
[ ] Responder "quanto custa" → classificou como Interesse?
[ ] Vendedor recebeu alerta no WhatsApp?
[ ] Responder "nao quero" → card moveu pra Encerrados?
[ ] Ativar Workflow 2 e esperar o cron → mandou proximo toque?
[ ] Alerta da fila (Workflow 3) chegou no WhatsApp do vendedor?
[ ] Forcar um erro → Error Handler mandou alerta?

IR PRO AR
[ ] Ativar todos os workflows
[ ] Monitorar 24h: checar logs do n8n (Executions no menu lateral)
[ ] Semana 1: 5 leads de teste
[ ] Semana 2: leads reais
[ ] Semana 3: todas cadencias
[ ] Semana 4: otimizacao com Claude Code
```

## Passo 8 — Entregar o output

Gere **dois arquivos**:

1. `workflow-n8n-{negocio}.md` com: configuracao (Passo 1), workflows 1-4 documentados node por node (Passos 2-5), tratamento de erros (Passo 6), e checklist (Passo 7).

2. `workflow-n8n-{negocio}.html` — pagina autocontida, tokens visuais do cohort (fundo `#0A0A0A`, ouro `#C9B298`), com diagramas de cada workflow e checklist interativo.

**Abra o HTML automaticamente.**

**Atualize a Central de Entregas** (`central-de-entregas-aula3.html`), id: 3.

**Depois de entregar, diga:** *"Maquina montada. Esteira de entrada escutando o WhatsApp, cadencia disparando sozinha, classificador reagindo a cada resposta, alerta cutucando o vendedor, e nutricao cuidando de quem nao respondeu. Siga o checklist de lancamento — teste tudo antes de ir pro ar. A Aula 3 ta completa: copy pronto (Skill 1), ClickUp organizado (Skill 2), n8n conectando tudo (Skill 3)."*
