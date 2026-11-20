# 🏷️ Guia de Indicadores e Símbolos de Status do Git no VS Code

Este guia explica o significado das letras, cores e marcações que aparecem ao lado dos arquivos e pastas no painel lateral (*Explorer*) do VS Code ao utilizar o Git.

---

## 1. 🔤 Significado das Letras de Status

No VS Code, cada arquivo alterado recebe uma letra maiúscula no canto direito que representa o seu estado atual dentro do repositório Git:

| Letra | Nome do Estado | Cor | O que significa? |
| :---: | :--- | :---: | :--- |
| **`U`** | **Untracked** (Não rastreado) | 🟢 Verde | É um arquivo novo criado no seu projeto. O Git ainda não está acompanhando o histórico dele. |
| **`M`** | **Modified** (Modificado) | 🟡 Amarelo / Laranja | É um arquivo que já existia nos commits anteriores e sofreu alterações desde a última gravação. |
| **`A`** | **Added / Staged** (Adicionado) | 🟢 Verde | O arquivo foi adicionado à área de preparação (*staging area*) via `git add .` e está pronto para o commit. |
| **`D`** | **Deleted** (Deletado) | 🔴 Vermelho | O arquivo foi excluído da pasta, mas a remoção ainda precisa ser gravada no commit. |
| **`R`** | **Renamed** (Renomeado) | 🔵 Azul | O arquivo teve o seu nome ou caminho alterado. |
| **`C`** | **Conflict** (Conflito) | 🔴 Vermelho | O arquivo possui conflitos de mesclagem (*merge/rebase*) que precisam ser resolvidos manualmente. |
| **`I`** | **Ignored** (Ignorado) | ⚪ Cinza Escuro | O arquivo ou pasta está listado no `.gitignore` e não será enviado para o GitHub. |

---

## 2. 🎨 Significado das Cores e Destaques

As cores ajudam na identificação rápida do estado do projeto antes de enviar ao GitHub:

* **Verde (`U` ou `A`):** Indica adições (novos arquivos ou arquivos prontos para commit).
* **Amarelo / Laranja (`M`):** Indica modificações em arquivos existentes.
* **Vermelho (`D` ou `C`):** Indica exclusões ou atenção crítica (conflitos pendentes).
* **Texto Opaco / Apagado:** Arquivos ignorados pelo Git (ex: pasta `node_modules/` ou arquivos `.log`).

---

## 3. 🟡 Pontos ao lado das Pastas e Abas

* **Ponto ao lado da pasta (ex: `estudos` e `01-git-github`):** Indica que dentro daquela pasta existe pelo menos um arquivo com alterações (`M`, `U`, `D`, etc.).
* **Bolinha branca na aba do arquivo:** Significa que você editou o arquivo, mas **ainda não salvou** no computador (pressione `Ctrl + S` para salvar).

---

## 4. 🔄 Como os Arquivos Transitam entre os Estados

O ciclo de vida de um arquivo no Git segue o fluxo abaixo:

1. **Criar arquivo novo** $\rightarrow$ Fica como **`U`** (*Untracked*).
2. **Executar `git add .`** $\rightarrow$ Passa para **`A`** ou fica limpo na área de *Staging*.
3. **Executar `git commit -m "..."`** $\rightarrow$ A letra desaparece (o arquivo está salvo no histórico).
4. **Editar o arquivo novamente** $\rightarrow$ Passa para **`M`** (*Modified*).
5. **Executar `git push`** $\rightarrow$ Envia tudo para o repositório remoto no GitHub.

---

## 💡 Dica Visual

Para visualizar todas as alterações consolidadas em uma única tela, clique no ícone do **Controle de Fonte** (*Source Control*) no menu lateral esquerdo do VS Code (ou use o atalho `Ctrl + Shift + G`).