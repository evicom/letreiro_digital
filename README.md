# Letreiro Digital Personalizável

App web de letreiro estilo placar eletrônico: totalmente customizável (texto, fonte, cor, velocidade), responsivo, funciona em tela cheia (retrato e paisagem) e é **instalável como aplicativo (PWA)** em celular, tablet e computador.

## Arquivos

```
index.html                  → app principal
manifest.json                → configuração do PWA (nome, ícone, tela cheia)
sw.js                        → service worker (permite instalar/funcionar offline)
icons/icon-192.png           → ícone do app
icons/icon-512.png           → ícone do app
icons/icon-512-maskable.png  → ícone adaptável (Android)
```

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (ex: `letreiro-digital`).
2. Envie todos os arquivos desta pasta para a raiz do repositório (mantendo a pasta `icons/`).
3. No repositório, vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` (ou `master`) e a pasta `/ (root)`.
5. Salve. Em alguns minutos seu app estará disponível em:
   `https://SEU-USUARIO.github.io/letreiro-digital/`

> ⚠️ Importante: o PWA (instalação e tela cheia real) só funciona em produção com **HTTPS** — o GitHub Pages já fornece isso automaticamente.

## Como instalar no celular/computador

- **Android (Chrome):** abra o link publicado → toque no botão flutuante ⬇️ (ou no menu ⋮ → "Instalar app / Adicionar à tela inicial").
- **iPhone/iPad (Safari):** abra o link → toque em Compartilhar → "Adicionar à Tela de Início" (o iOS não expõe o prompt automático, então é sempre manual).
- **Computador (Chrome/Edge):** clique no ícone de instalação que aparece na barra de endereço, ou no botão ⬇️ dentro do app.

## Tela cheia e rotação

- Toque no botão ⛶ (ou dê duplo clique/duplo toque no letreiro) para entrar/sair da tela cheia.
- Em tela cheia, o painel de controles fica oculto para o letreiro ocupar 100% da tela — puxe a alcinha amarela na parte inferior para reabri-lo.
- O layout e o tamanho da fonte se recalculam automaticamente ao girar o aparelho entre vertical e horizontal, sempre preenchendo a altura disponível.
- Em navegadores compatíveis (principalmente Chrome/Android), o app tenta manter a orientação livre durante a tela cheia; em navegadores sem suporte (ex.: Safari/iOS), a rotação continua funcionando normalmente pelo sistema, só sem o "lock" automático.

## Testar localmente

Como o `sw.js` exige um servidor (não abre direto com `file://`), rode um servidor local simples dentro da pasta:

```bash
python3 -m http.server 8080
```

E acesse `http://localhost:8080` no navegador.
