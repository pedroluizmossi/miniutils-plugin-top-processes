# Top processos — plugin do MiniUtils

Plugin para o [MiniUtils](https://github.com/pedroluizmossi/hub-app-rust) (hub de mini-apps para o
desktop Linux e Windows) que mostra os processos que mais usam CPU ou memória, atualizados a
cada 3 segundos. É o exemplo de plugin **com tela e script próprios**.

| Arquivo | O que é |
|---|---|
| `manifest.toml` | id, nome, o provedor que lê (`uses = ["procs"]`) e a seção `[ui]` |
| `view.slint` | a tela, interpretada pelo MiniUtils (só importa `std-widgets.slint` e `miniutils.slint`) |
| `main.rhai` | a lógica: `on_event("procs", …)` com a lista de processos e `action()` dos botões CPU/Memória |

## Permissões

Lê `procs`: os processos que mais usam CPU e memória, que o próprio MiniUtils coleta (igual
no Linux e no Windows). Não executa nenhum programa; sem rede, sem acesso a arquivos.

Precisa de um MiniUtils com o provedor `procs` (o mesmo que traz `miniutils --version`);
uma versão anterior recusa a instalação.

## Instalar

Pela loja do MiniUtils (Configurações > Loja de plugins), com o índice
[miniutils-store](https://github.com/pedroluizmossi/miniutils-store). Ou pela linha de comando:

```sh
miniutils --instalar io.github.pedroluizmossi.top-processes <índice> --chave <chave pública>
```

Remover: `miniutils --remover io.github.pedroluizmossi.top-processes`.

## Versões

- **0.3.0**: a lista vem do provedor `procs` do MiniUtils em vez do `ps`: funciona também
  no Windows, e o plugin não executa mais nenhum programa. CPU em % da máquina toda.
- **0.2.0**: título na fonte de título e percentuais na fonte mono do visual da janela
  (`theme.font-title`, `theme.font-mono`).
- **0.1.0**: primeira versão.

## Licença

MIT
