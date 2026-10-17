# Grav Browser

Navegador Android nativo (WebView) com suporte a extensões no próprio app.

## Recursos
- `alert()`, `confirm()` e `prompt()` do JavaScript viram diálogos nativos (AlertDialog).
- Ao clicar em "Adicionar ao Chrome" (Chrome Web Store) ou "Adicionar ao Firefox" (Firefox Add-ons),
  abre o diálogo "Você quer instalar a extensão {Nome}?". Sim instala; Não fecha.
- Extensões são baixadas, descompactadas em `files/extensions/` e aplicadas via `content_scripts`
  (js e css) nas páginas que casam com `matches`. Botão "Ext" permite ativar, desativar ou remover.
- Downloads comuns via DownloadManager.

## Build (Code on the Go ou Android Studio)
1. Abra a pasta `GravBrowser`.
2. Gere o APK (debug). Requer JDK 17 e Android SDK 34.

## Limitações
- Suporte a extensões é um subconjunto: content scripts e CSS. Service workers / background
  scripts e APIs `chrome.*` não são executados ainda.
- Extensões do Firefox (XPI) usam, em geral, manifest compatível; as que dependem de APIs específicas não funcionarão.
- Se a loja mudar o texto do botão, ajuste a lista em `assets/store_hook.js`.
