# 📝 Guia Completo de Sintaxe e Formatação Markdown

Este guia apresenta a estrutura e as principais tags para criação de documentos formatados em Markdown (`.md`), abrangendo desde formatações básicas de texto até blocos de código e tabelas.

---

## 1. 📐 Títulos e Hierarquia (*Headings*)

A hierarquia de títulos é definida pela quantidade de símbolos `#` no início da linha (do nível 1 ao nível 6):

```markdown
# Título Nível 1 (Principal - usar apenas um por documento)
## Título Nível 2 (Seções principais)
### Título Nível 3 (Subseções)
#### Título Nível 4
##### Título Nível 5
###### Título Nível 6
```

---

## 2. ✒️ Formatação de Texto

Estilize trechos de texto utilizando marcações simples ao redor das palavras:

```markdown
*Texto em itálico* ou _Texto em itálico_
**Texto em negrito** ou __Texto em negrito__
***Texto em negrito e itálico***
~~Texto tachado (riscado)~~
```

---

## 3. 💻 Código e Realce de Sintaxe (*Syntax Highlighting*)

### Código *Inline* (no meio da frase)
Use acentos graves simples (`` ` ``) para destacar comandos ou variáveis dentro de um parágrafo:

```markdown
Para verificar a versão, utilize o comando `git --version` no terminal.
```

### Blocos de Código multilinha
Envolva o bloco de código com três acentos graves (`` ``` ``) e informe a linguagem ao lado dos primeiros acentos para ativar o destaque colorido (*syntax highlighting*):

````markdown
```powershell
git add .
git commit -m "docs: adiciona guia de markdown"
git push origin main
```
````

````markdown
```python
def saudar_usuario(nome):
    return f"Olá, {nome}! Bem-vindo ao repositório."

print(saudar_usuario("Lysa"))
```
````

````markdown
```sql
SELECT nome, cargo, salario 
FROM funcionarios 
WHERE departamento = 'Dados' 
ORDER BY salario DESC;
```
````

---

## 4. 📋 Listas

### Listas Não Ordenadas
Utilize asteriscos (`*`), hífens (`-`) ou mais (`+`):

```markdown
* Item 1
* Item 2
  * Subitem 2.1
  * Subitem 2.2
```

### Listas Ordenadas
Utilize números seguidos de ponto:

```markdown
1. Primeiro passo
2. Segundo passo
3. Terceiro passo
```

### Listas de Tarefas (*Checklists*)
Ideal para roadmap, prazos e controle de entregáveis no GitHub:

```markdown
- [x] Configurar Git localmente
- [x] Criar repositório no GitHub
- [ ] Mover projeto para fora do OneDrive
- [ ] Concluir módulo de SQL
```

---

## 5. 💬 Citações e Blocos de Destaque (*Blockquotes*)

Utilize o símbolo de maior (`>`) para criar destaques de texto ou citações:

```markdown
> 💡 **Dica de Ouro:** Sempre execute `git status` antes de fazer um commit para conferir as alterações pendentes.
```

### *Callouts* nativos do GitHub (Caixas de Aviso)

```markdown
> [!NOTE]
> Informação útil para ter em mente durante o estudo.

> [!TIP]
> Dica prática para acelerar sua produtividade.

> [!WARNING]
> Cuidado: executar git reset sem salvar pode sobrescrever arquivos.
```

---

## 6. 📊 Tabelas

Crie tabelas utilizando barras verticais (`|`) para colunas e hífens (`-`) para a linha divisória do cabeçalho. Os dois pontos (`:`) definem o alinhamento:

```markdown
| Comando | Descrição | Exemplo |
| :--- | :---: | ---: |
| `git status` | Exibe o estado dos arquivos | Esquerda |
| `git add` | Adiciona arquivos ao staging | Centralizado |
| `git commit` | Salva as alterações | Direita |
```

---

## 7. 🔗 Links e Conexões

### Links Externos

```markdown
[Acessar a documentação do Git](https://git-scm.com/doc)
```

### Links Internos (Âncoras entre arquivos)

```markdown
[Ir para o Guia de Atalhos](./03-atalhos-vs-code.md)
```

---

## 8. 🛡️ Caracteres de Escape

Se precisar exibir um caractere reservado do Markdown (como `#`, `*`, `_`, `` ` ``) sem formatar o texto, insira uma barra invertida (`\`) antes dele:

```markdown
\# Este texto não virará um Título Nível 1
\*Este texto não ficará em itálico\*
```