# Relatório de Preparação para GitHub

Arquivo recebido: `flows (1).json`

## Alterações feitas

- Mantido somente o fluxo principal da AstroNet.
- Removidos config nodes antigos e não utilizados.
- Removidas credenciais reais de nodes e comentários.
- Ajustado Function Node de download de áudio para usar `env.get("TELEGRAM_TOKEN")`.
- Debug nodes desativados por padrão.
- Criado `README.md` completo.
- Criado `.gitignore`.
- Criado `.env.example`.
- Criado `package.json` com dependências do Node-RED.
- Criados documentos em `docs/`.

## Quantidade de nodes

- Nodes no export original: 27
- Nodes na versão limpa: 18

## Atenção

As credenciais antigas devem ser revogadas caso tenham sido reais.
