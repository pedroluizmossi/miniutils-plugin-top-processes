# Top processos — plugin do MiniUtils

Plugin para o [MiniUtils](https://github.com/pedroluizmossi/hub-app-rust) (hub de mini-apps para o
desktop Linux) que mostra os processos que mais usam CPU ou memória, lidos com `ps` a cada
5 segundos. É o exemplo de plugin **com tela e script próprios**.

| Arquivo | O que é |
|---|---|
| `manifest.toml` | id, nome, permissões (`exec = ["ps"]`) e a seção `[ui]` |
| `view.slint` | a tela, interpretada pelo MiniUtils (só importa `std-widgets.slint` e `miniutils.slint`) |
| `main.rhai` | a lógica: `start()`, `tick()` a cada 5 s e `action()` dos botões CPU/Memória |

## Permissões

Executa só o programa `ps` (`ps -eo comm,pcpu,pmem`). Sem rede, sem acesso a arquivos.

## Instalar

Pela loja do MiniUtils (Configurações > Loja de plugins), com o índice
[miniutils-store](https://github.com/pedroluizmossi/miniutils-store). Ou pela linha de comando:

```sh
miniutils --instalar io.github.pedroluizmossi.top-processes <índice> --chave <chave pública>
```

Remover: `miniutils --remover io.github.pedroluizmossi.top-processes`.

## Versões

- **0.2.0**: título na fonte de título e percentuais na fonte mono do visual da janela
  (`theme.font-title`, `theme.font-mono`).
- **0.1.0**: primeira versão.

## Licença

MIT
