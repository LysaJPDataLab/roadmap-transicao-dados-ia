# 01 — Primeiros Passos no Git e GitHub (Criação do Primeiro Repositório)

**Data:** 20/11/2026  
**Etapa:** Fase 0 — Adaptação e Setup do Ambiente  
**Objetivo:** Configurar o Git localmente no VS Code, estruturar o repositório `roadmap-transicao-dados-ia` e realizar o primeiro `commit` e `push` para o perfil `@LysaJPDataLab`.

---

## Pré-requisito
- Ter o **Git** instalado na máquina (`git-scm.com`, instalação padrão) e o **VS Code** configurado.

---

## Passo a Passo Executado

### 1. Criação do Repositório Remoto no GitHub
1. Acessar o GitHub em `@LysaJPDataLab` e clicar em **New**.
2. Definir o nome do repositório como `roadmap-transicao-dados-ia`.
3. Manter a visibilidade como **Public**.
4. Criar o repositório **vazio** (sem `README`, `.gitignore` ou licença) para evitar conflitos no primeiro `push`.

### 2. Abertura da Pasta Local no VS Code
1. Criar a pasta local `roadmap-transicao-dados-ia`.
2. Abrir a pasta no VS Code (**File > Open Folder**).
3. Abrir o terminal integrado com **`Ctrl + '`**.

### 3. Configuração de Identidade no Git (feita apenas uma vez)
Configuração do nome e e-mail vinculados à conta do GitHub:

```bash
git config --global user.name "Lysara Pinheiro"
git config --global user.email "seu-email-do-github@exemplo.com"
```

### 4. Criação da Estrutura de Pastas e Arquivos Iniciais
Comandos executados no terminal para criar a árvore de diretórios:

```bash
mkdir docs
mkdir estudos
mkdir estudos/01-git-github
mkdir estudos/02-sql
mkdir estudos/03-python-dados
mkdir estudos/04-powerbi-ux
mkdir laboratorio-om-sintetico
mkdir projetos
mkdir projetos/01-indicadores-om-bi
mkdir projetos/02-pipeline-api-sql
mkdir projetos/03-analise-com-ia
```

Arquivos criados manualmente via Explorer do VS Code:
- `README.md` (raiz)
- `docs/01-cenario-e-perfil.md`
- `docs/02-rotina-e-cronograma.md`
- `docs/03-roadmap-6-meses.md`

> **Aprendizado:** O Git versiona arquivos, não pastas vazias. Pastas sem arquivos só aparecem no GitHub quando recebem o primeiro conteúdo.

### 5. Inicialização, Primeiro Commit e Push
Sequência de comandos executada no terminal do VS Code:

```bash
# Inicializa o controle de versão na pasta local
git init

# Define a branch principal como 'main'
git branch -M main

# Adiciona todos os arquivos criados à área de preparação (staging)
git add .

# Registra o primeiro marco no histórico com mensagem descritiva
git commit -m "docs: adiciona plano de estudos, rotina e roadmap de transicao"

# Conecta o repositório local ao repositório remoto no GitHub
git remote add origin [https://github.com/LysaJPDataLab/roadmap-transicao-dados-ia.git](https://github.com/LysaJPDataLab/roadmap-transicao-dados-ia.git)

# Envia os commits para o GitHub e vincula a branch principal
git push -u origin main
```

---

## Fluxo Recorrente de Atualização (Cola Rápida)

Sempre que novos estudos, anotações ou projetos forem adicionados:

```bash
git add .
git commit -m "tipo(escopo): descricao curta da alteracao"
git push
```

### Comandos Úteis de Consulta
- `git status` — verifica quais arquivos foram modificados ou ainda não foram adicionados.
- `git log --oneline` — lista o histórico resumido de commits realizados.

---

## Checklist de Validação
- [ ] Git configurado com nome e e-mail do GitHub.
- [ ] Estrutura de pastas criada localmente.
- [ ] Primeiro `commit` realizado sem erros.
- [ ] Arquivos visíveis no GitHub em `@LysaJPDataLab/roadmap-transicao-dados-ia`.