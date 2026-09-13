# MandAPI Connect v1.2.12

> Correção do diálogo de confirmação que aparecia por trás do painel de Configurações.

## O que mudou

- **Correção crítica (z-index):** ao clicar em **Restaurar padrões** dentro de Configurações, o diálogo de confirmação ("⚠️ Restaurar os padrões irá:…") era renderizado **atrás** do painel de Configurações (`.app-dialog-overlay` z-index 1000 vs `.modal` z-index 2000) — ou seja, invisível. O painel fechava sem que o usuário visse a confirmação, dando a impressão de que os botões "Cancelar" e "Restaurar padrões" estavam com as funções invertidas.
  - `.app-dialog-overlay` agora usa `z-index: 2500` — acima de qualquer `.modal` (2000) e abaixo dos toasts (3000). Aplica-se a todos os diálogos: confirmar, alertar e o novo prompt de chave de API.
- Mantidas as correções da v1.2.11: `showPrompt()` nativo (os botões Claude/Codex respondem na primeira execução sem chave salva) e atualizador apontando para `saleiyi/mandapi-connect-releases`.

## Instalador

| Arquivo | Tamanho | SHA-256 |
| --- | --- | --- |
| MandAPI-Connect-Setup.exe | 419,4 MB | `c4c9291ab5b06eee08094aa03103a05c233cdeaf73bdf31e4ccd1643cf2a090c` |

## A v1.2.11 foi revogada

A v1.2.11 será excluída; a v1.2.12 assume como `latest`. Usuários com a v1.2.11 instalada receberão a atualização automática ao reiniciar o aplicativo.