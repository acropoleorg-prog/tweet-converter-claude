# Tweet Machine — Acrópole

Ferramenta interna para transformar matérias e colunas em tweets e threads.

## Rodando localmente

1. Instale as dependências:
   ```
   npm install
   ```

2. Copie o arquivo de variáveis de ambiente:
   ```
   cp .env.example .env
   ```

3. Edite o `.env` e coloque sua chave da Anthropic:
   ```
   ANTHROPIC_API_KEY=sk-ant-...
   ```
   A chave está em: https://console.anthropic.com/settings/keys

4. Inicie o servidor:
   ```
   npm start
   ```

5. Abra no navegador: http://localhost:3000

---

## Deploy no Railway

1. Faça push deste projeto para um repositório no GitHub

2. No Railway, clique em **New Project → Deploy from GitHub repo**

3. Selecione o repositório

4. Vá em **Variables** e adicione:
   ```
   ANTHROPIC_API_KEY = sk-ant-sua-chave-aqui
   ```

5. O Railway detecta automaticamente que é Node.js e faz o deploy

6. Clique em **Settings → Networking → Generate Domain** para ter uma URL pública

---

## Estrutura

```
tweet-machine/
├── server.js          ← backend (Express, proxy para Anthropic)
├── public/
│   └── index.html     ← frontend completo
├── package.json
├── .env.example
└── .env               ← NÃO commitar no GitHub
```

## Importante

Nunca suba o arquivo `.env` para o GitHub. O `.gitignore` já o exclui.
A chave da API fica apenas no Railway (variáveis de ambiente do servidor).
