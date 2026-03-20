# Domus Leiturista — PWA

## O que é
Aplicativo web progressivo (PWA) para leituristas da Domus Soluções.
Funciona offline, pode ser instalado no celular como app nativo.

## Funcionalidades
- 📋 Manual completo com todos os 9 capítulos
- ✅ 5 checklists interativos (Leitura, Religue, Suspensão, Vistoria Visual, Inventário)
- 📵 100% offline após primeiro acesso
- 📱 Instalável no Android e iOS

## Como instalar no celular

### Android (Chrome)
1. Abra o app no navegador
2. Toque nos 3 pontinhos (menu)
3. Selecione "Adicionar à tela inicial"
4. Confirme — o ícone aparece como app

### iPhone (Safari)
1. Abra o app no Safari
2. Toque no botão compartilhar (⬆️)
3. Selecione "Adicionar à tela de início"
4. Confirme

## Como hospedar

### Opção 1 — GitHub Pages (gratuito)
1. Crie um repositório no GitHub
2. Suba todos os arquivos desta pasta
3. Ative GitHub Pages nas configurações
4. Compartilhe o link com os leituristas

### Opção 2 — Netlify (gratuito)
1. Acesse netlify.com
2. Arraste a pasta do app
3. URL gerada automaticamente

### Opção 3 — Servidor interno
Qualquer servidor web estático serve (nginx, Apache).
Precisa de HTTPS para o Service Worker funcionar.

## Arquivos
- index.html — app principal
- sw.js — service worker (offline)
- manifest.json — configurações do PWA
- icon-192.svg / icon-512.svg — ícones

## Atualização de conteúdo
Todo o conteúdo está em `index.html`, nas constantes `DETAILS` e `CHECKLISTS`.
Edite diretamente para atualizar textos, etapas ou adicionar novos checklists.
