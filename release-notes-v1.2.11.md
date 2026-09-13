# MandAPI Connect v1.2.11

> Correção de bug que travava os botões Claude e Claude na primeira execução.

## O que mudou

- **Correção crítica:** ao clicar em **Claude** ou **Codex** pela primeira vez (sem chave de API salva), o app chamava `window.prompt(...)`, que não é implementado no processo de renderização do Electron 33. O resultado era um erro silencioso e os botões paravam de responder.
  - Adicionado `showPrompt()` em `src/renderer/app.js` (mesma família do `showAlert` / `showConfirm`), com campo `<input type="password">` e botões **Cancelar** / **OK**.
  - Substituído `window.prompt(...)` em `launchTool()` (linha 966) e na renomeação de dispositivo remoto (`app.js:1860`).
- Atualizador interno agora consulta `https://api.github.com/repos/saleiyi/mandapi-connect-releases/releases/latest` em vez do repositório inexistente `MandAPI/mandapi-connect`.

## Instalador

| Arquivo | Tamanho | SHA-256 |
| --- | --- | --- |
| MandAPI-Connect-Setup.exe | 419,4 MB | `b599a757219eb676e65dd11be935ad5aac7e1d65daa7729de9a3fb482b0a2daa` |

O instalador traz o seletor de idioma (Português Brasileiro / English / 简体中文), mantém o multi-idioma automático por detecção de locale do Windows e continua com auto-update configurado para o repositório público.

## A v1.2.10 foi revogada

A v1.2.10 (`6d6e36db...`) foi marcada como "pre-release" e será excluída. Todos os usuários existentes devem receber a atualização automática para a v1.2.11 assim que o app for reiniciado.