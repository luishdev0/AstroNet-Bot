# Segurança do Projeto

Este projeto foi preparado para ser publicado no GitHub sem expor credenciais reais.

## O que foi limpo

- API keys do IBM Watson Speech to Text.
- API keys do IBM Watson Text to Speech.
- Informações sensíveis do comentário de configuração.
- Token do Telegram que estava em comentário.
- Configurações antigas e não utilizadas de outros bots/exportações.
- Caminhos locais antigos de banco de dados que não fazem parte do AstroNet.

## O que você precisa fazer

Se as credenciais antigas eram reais, revogue e gere novas credenciais antes de continuar.

### Telegram

1. Abra o BotFather.
2. Gere ou regenere o token do bot.
3. Atualize o `.env` local.

### IBM Cloud

1. Acesse os serviços Watson usados no projeto.
2. Gere novas API keys.
3. Atualize o Node-RED localmente.

## Regra principal

Nunca publique:

```text
.env
API keys
Tokens
Senhas
flows_cred.json
Bancos de dados reais
```
