# AstroNet Bot 🚀

![Node-RED](https://img.shields.io/badge/Node--RED-Flow%20Automation-red?style=for-the-badge)
![IBM Watson](https://img.shields.io/badge/IBM%20Watson-AI%20Assistant-blue?style=for-the-badge)
![Telegram Bot](https://img.shields.io/badge/Telegram-Bot%20API-2CA5E0?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/JavaScript-Function%20Nodes-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Projeto%20Acad%C3%AAmico-green?style=for-the-badge)

Chatbot de atendimento virtual da **AstroNet**, desenvolvido com **Node-RED**, **IBM Watson Assistant**, **IBM Watson Speech to Text**, **IBM Watson Text to Speech** e integração com a **Telegram Bot API**.

O objetivo do projeto é simular um assistente inteligente para uma empresa de internet via satélite, ajudando usuários com dúvidas sobre cobertura, planos, instalação, suporte técnico, equipamentos e contratação.

> Esta versão foi preparada para publicação no GitHub sem tokens, senhas ou API keys reais.

---

## 📌 Sobre o projeto

A **AstroNet** é uma proposta de solução voltada para conectividade em regiões onde a internet tradicional não chega com qualidade, como áreas rurais, fazendas, comunidades afastadas e locais de difícil acesso.

Dentro desse contexto, o **AstroNet Bot** funciona como um canal de atendimento automatizado no Telegram. O usuário pode enviar mensagens de texto ou áudio, e o bot processa a solicitação, consulta o IBM Watson Assistant e retorna uma resposta em texto e, quando configurado, também em áudio.

O projeto foi construído em **Node-RED**, utilizando fluxos visuais para integrar diferentes serviços e automatizar o atendimento.

---

## 🎯 Objetivo

Criar um bot de atendimento inteligente capaz de:

- receber mensagens pelo Telegram;
- identificar se o usuário enviou texto ou áudio;
- converter áudio em texto com IBM Watson Speech to Text;
- enviar perguntas para o IBM Watson Assistant;
- retornar respostas automáticas sobre a AstroNet;
- transformar respostas em áudio com IBM Watson Text to Speech;
- simular um atendimento digital simples, acessível e funcional.

---

## ⚙️ Funcionalidades

- Atendimento automatizado via Telegram.
- Mensagem inicial de boas-vindas.
- Suporte a perguntas frequentes sobre a AstroNet.
- Recebimento de mensagens em texto.
- Recebimento de mensagens em áudio.
- Conversão de áudio para texto com IBM Watson Speech to Text.
- Integração com IBM Watson Assistant V2.
- Conversão de respostas em áudio com IBM Watson Text to Speech.
- Envio de resposta em texto para o usuário.
- Envio de resposta em áudio para o usuário.
- Separação automática entre mensagens de texto e áudio.
- Tratamento básico de erros.
- Organização do fluxo no Node-RED.
- Estrutura preparada para versionamento no GitHub.
- Uso de arquivo `.env.example` para documentar variáveis sem expor credenciais.

---

## 🧠 Tecnologias utilizadas

| Tecnologia | Uso no projeto |
|---|---|
| **Node-RED** | Criação do fluxo visual de automação e integração do bot |
| **IBM Watson Assistant** | Interpretação das mensagens e geração das respostas do chatbot |
| **IBM Watson Speech to Text** | Conversão de áudio enviado pelo Telegram em texto |
| **IBM Watson Text to Speech** | Conversão das respostas do bot em áudio |
| **Telegram Bot API** | Comunicação entre o usuário e o chatbot no Telegram |
| **JavaScript** | Lógica personalizada dentro dos Function Nodes do Node-RED |
| **JSON** | Formato de exportação/importação do fluxo do Node-RED |

---

## 🏗️ Arquitetura do fluxo

O fluxo principal segue esta lógica:

```text
Telegram Receiver
        ↓
Separar texto e áudio
        ↓
Texto direto ───────────────→ Preparar Assistant
        ↓                         ↓
Áudio → Baixar áudio → Speech to Text → Texto transcrito
                                  ↓
                            Watson Assistant
                                  ↓
                            Tratar resposta
                                  ↓
               Resposta em texto + geração de áudio com TTS
                                  ↓
                            Telegram Sender
