# Configuração do AstroNet Bot

## 1. Importar o fluxo

Importe o arquivo:

```text
flows/astronet-flow.safe.json
```

no editor do Node-RED.

## 2. Configurar Telegram

Crie um bot no BotFather e salve o token na variável:

```env
TELEGRAM_TOKEN=seu_token_real
```

No fluxo, o Function Node **baixar áudio Telegram** lê essa variável usando:

```js
env.get("TELEGRAM_TOKEN")
```

## 3. Configurar IBM Watson

No Node-RED, abra e configure manualmente:

- `speech to text`
- `assistantV2`
- `text to speech`

Preencha endpoint, API key e Assistant ID conforme sua conta IBM Cloud.

## 4. Fazer deploy

Depois de configurar tudo:

1. Clique em **Deploy**.
2. Abra o Telegram.
3. Envie `/start` para o bot.
4. Teste mensagem de texto.
5. Teste áudio.

## 5. Problemas comuns

### Bot não responde

Verifique o token do Telegram e se o Node-RED está rodando.

### Áudio não transcreve

Verifique a API key e o endpoint do Watson Speech to Text.

### Resposta do Watson não aparece

Confira o Assistant ID, endpoint e credenciais do Watson Assistant.

### Áudio de resposta não chega

Confira a configuração do Watson Text to Speech e o formato de saída `audio/mp3`.
