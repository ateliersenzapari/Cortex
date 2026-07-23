# CORTEX — segundo cérebro

> o sistema operacional da sua vida

Projeto do CORTEX, um "segundo cérebro" pessoal organizado em módulos:

- **Memória**
- **Conhecimento**
- **Identidade**
- **Visão**
- **Voz**
- **Raciocínio**
- **Automação**

## Estrutura

- `index.html` — animação de marca do CORTEX (rede neural em canvas com os 7 módulos), vitrine de conteúdo (fase 1)
- `assistente.html` — MVP do assistente de voz (fase 2 inicial): fala com o usuário via voz real (Web Speech API no Chrome/Android, fallback de ditado do teclado no iPhone Safari), conversa com Claude através de um workflow n8n, e o visual reage aos estados (ouvindo/pensando/respondendo). Fonte da página hospedada ao vivo em `https://senza-pari.app.n8n.cloud/webhook/cortex`.
- `docs/cortex-briefing.pdf` — briefing do projeto

## Backend (n8n — instância Senza Pari)

- **`Cortex - Pagina`** — serve `assistente.html` via `GET /webhook/cortex`
- **`Cortex - API de Voz`** — recebe `{mensagem, sessionId}` via `POST /webhook/cortex-comando`, conversa com Claude (com memória por sessão) e responde `{resposta}`

Ainda sem acesso a e-mail, calendário ou arquivos reais — isso é a próxima etapa (conectar Google OAuth2 no n8n).
