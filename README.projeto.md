# AstroNet Bot - Atendimento Inteligente via Telegram

Projeto de chatbot da **AstroNet**, desenvolvido em **Node-RED** com integração ao **Telegram** e aos serviços da **IBM Watson**. O bot atende usuários interessados em internet via satélite, cobertura em áreas remotas, planos, instalação, equipamentos, suporte técnico e contratação.

> Esta versão foi preparada para GitHub com o fluxo limpo, sem tokens, senhas ou API keys reais.

## 1. Visão geral

O AstroNet Bot é um assistente virtual criado para automatizar o atendimento inicial da AstroNet. Ele recebe mensagens pelo Telegram, interpreta texto ou áudio, consulta o IBM Watson Assistant e responde ao usuário em texto e, quando configurado, também em áudio.

## 2. Principais funcionalidades

- Atendimento via Telegram.
- Respostas automáticas sobre a AstroNet.
- Reconhecimento de mensagens de texto.
- Recebimento de áudio pelo Telegram.
- Conversão de áudio em texto com IBM Watson Speech to Text.
- Integração com IBM Watson Assistant.
- Conversão de resposta em áudio com IBM Watson Text to Speech.
- Mensagem de boas-vindas para `/start`, `/help`, `oi`, `olá` e comandos semelhantes.
- Separação automática entre mensagens de texto e áudio.
- Contexto de conversa salvo por usuário usando `flow.set` do Node-RED.
- Tratamento básico de erros para áudio, texto vazio e falhas de API.
- Estrutura preparada para versionamento no GitHub.
- Uso de `.env.example` para documentar variáveis necessárias sem expor credenciais.
- Fluxo exportado em JSON para importação no Node-RED.
- Organização mínima para documentação, fluxo e configuração.

## 3. Tecnologias utilizadas

- Node-RED
- Telegram Bot API
- IBM Watson Assistant V2
- IBM Watson Speech to Text
- IBM Watson Text to Speech
- JavaScript em Function Nodes

## 4. Estrutura do projeto

```text
AstroNet-Bot-GitHub/
├── README.md
├── package.json
├── .gitignore
├── .env.example
├── flows/
│   └── astronet-flow.safe.json
├── docs/
│   ├── CONFIGURACAO.md
│   └── SEGURANCA.md
├── assets/
└── data/
```

## 5. Pré-requisitos

Antes de rodar o projeto, instale:

- Node.js
- Node-RED
- Conta no Telegram com bot criado pelo BotFather
- Conta IBM Cloud com serviços Watson configurados
- Navegador para acessar o editor do Node-RED

## 6. Dependências do Node-RED

O fluxo usa estes módulos:

```bash
npm install node-red-contrib-telegrambot@17.4.5
npm install node-red-node-watson@0.10.3
npm install node-red-node-sqlite@2.0.1
```

Também é possível instalar pelo próprio editor do Node-RED em:

```text
Menu → Manage palette → Install
```

## 7. Configuração das variáveis de ambiente

Copie o arquivo de exemplo:

```bash
cp .env.example .env
```

Depois preencha com seus dados reais:

```env
TELEGRAM_TOKEN=seu_token_do_telegram
IBM_WATSON_STT_API_KEY=sua_chave_speech_to_text
IBM_WATSON_STT_URL=sua_url_speech_to_text
IBM_WATSON_TTS_API_KEY=sua_chave_text_to_speech
IBM_WATSON_TTS_URL=sua_url_text_to_speech
IBM_WATSON_ASSISTANT_API_KEY=sua_chave_assistant
IBM_WATSON_ASSISTANT_URL=sua_url_assistant
IBM_WATSON_ASSISTANT_ID=seu_assistant_id
```

Nunca envie o `.env` para o GitHub.

## 8. Como importar o fluxo no Node-RED

1. Abra o Node-RED.
2. Clique no menu no canto superior direito.
3. Vá em **Import**.
4. Selecione o arquivo `flows/astronet-flow.safe.json`.
5. Clique em **Import**.
6. Configure os nodes do Telegram e IBM Watson com suas credenciais reais.
7. Clique em **Deploy**.

## 9. Como o fluxo funciona

O fluxo segue esta lógica:

```text
Telegram Receiver
        ↓
Separar texto e áudio
        ↓
Texto direto ───────────────→ Preparar Assistant
        ↓                         ↓
Áudio → Baixar áudio → STT → Texto transcrito
                                  ↓
                            Watson Assistant
                                  ↓
                            Tratar resposta
                                  ↓
              Responder texto no Telegram + gerar áudio com TTS
```

## 10. Mensagem inicial do bot

Ao receber `/start`, `/help`, `oi`, `olá` ou comandos semelhantes, o bot envia uma apresentação da AstroNet e exemplos de perguntas que o usuário pode fazer.

## 11. Segurança

Esta versão removeu as credenciais reais do fluxo. Mesmo assim, antes de publicar qualquer projeto no GitHub, confira:

- se o `.env` está no `.gitignore`;
- se não há tokens dentro de Function Nodes;
- se não há API keys em comentários;
- se não há endpoints privados ou IDs sensíveis que você não queira expor;
- se não há arquivos de banco local com dados reais.

## 12. Importante sobre credenciais antigas

Se alguma chave real já apareceu em arquivos exportados, prints, mensagens ou repositórios públicos, o mais seguro é revogar e gerar novas credenciais no Telegram e na IBM Cloud.

## 13. Possíveis melhorias futuras

- Salvar histórico de conversas em banco de dados.
- Criar painel administrativo.
- Melhorar tratamento de erros do áudio.
- Adicionar logs mais organizados.
- Criar respostas específicas por categoria: planos, instalação, suporte e orçamento.
- Criar integração com CRM ou formulário de captação de leads.
- Separar ambiente de desenvolvimento e produção.

## 14. Como subir para o GitHub

Dentro da pasta do projeto, rode:

```bash
git init
git add .
git commit -m "Primeira versão segura do AstroNet Bot"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/astronet-bot.git
git push -u origin main
```

Depois, para atualizações futuras:

```bash
git add .
git commit -m "Atualiza fluxo do AstroNet Bot"
git push
```

## 15. Autor

Projeto desenvolvido para fins acadêmicos e demonstração da solução AstroNet.

**Nome:** Luis Henrique  
```
