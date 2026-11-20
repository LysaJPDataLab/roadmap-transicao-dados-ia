# 🐙 Guia Definitivo: Terminologias e Comandos do Git

Este repositório reúne os termos fundamentais do ecossistema Git/GitHub e os comandos mais utilizados no dia a dia do desenvolvimento de software e análise de dados.

---

## 1. 📚 Terminologias Essenciais

Para entender o funcionamento do Git, é fundamental compreender a sua arquitetura e seus conceitos-chave:

* **Working Directory (Diretório de Trabalho):** A pasta do seu computador onde você cria, edita e deleta arquivos localmente.
* **Staging Area (Index):** A área intermediária (*palco*) onde os arquivos modificados são preparados antes de virarem um commit.
* **Local Repository (Repositório Local):** A pasta `.git` oculta dentro do seu projeto onde todo o histórico de versões fica salvo no seu computador.
* **Remote Repository (Repositório Remoto):** A versão do projeto hospedada na nuvem (servidores do GitHub, GitLab, Bitbucket, etc.).
* **Commit:** Um "snapshot" (foto instantânea) das alterações do seu projeto gravada no histórico com uma mensagem descritiva e um hash de identificação único.
* **Branch (Ramificação):** Uma linha de desenvolvimento paralela. A branch principal geralmente se chama `main` (ou `master`).
* **HEAD:** Um ponteiro que indica qual branch e commit estão ativos na sua tela no momento.
* **Clone:** Uma cópia completa de um repositório remoto baixada para o seu computador local.
* **Fork:** Uma cópia de um repositório de outro usuário salva dentro da sua própria conta do GitHub.
* **Pull Request (PR):** Uma proposta enviada no GitHub para juntar as alterações da sua branch com a branch principal do projeto original.
* **Merge:** O ato de fundir o histórico de duas branches diferentes.
* **Rebase:** Reescrever o histórico aplicando os seus commits locais no topo das últimas alterações vindas da branch remota.
* **Merge Conflict (Conflito de Mesclagem):** Situação em que duas alterações conflitantes foram feitas na mesma linha do mesmo arquivo e o Git exige uma decisão manual.
* **Stash:** Um "gaveteiro" temporário onde você guarda alterações não salvas para limpar o diretório de trabalho sem perder o código.

---

## 2. ⚙️ Comandos de Configuração Inicial

Utilizados para identificar o autor das alterações no projeto:

```powershell
# Configura o nome do usuário globalmente
git config --global user.name "Seu Nome"

# Configura o e-mail do usuário globalmente
git config --global user.email "seu-email@exemplo.com"

# Define o nome 'main' como padrão para novas branches principais
git config --global init.defaultBranch main

# Exibe todas as configurações ativas do Git
git config --list
```

---

## 3. 🚀 Inicialização e Conexão Remota

```powershell
# Transforma a pasta atual em um repositório Git local
git init

# Clona um repositório remoto para o computador
git clone https://github.com/usuario/repositorio.git

# Conecta o repositório local a um repositório remoto
git remote add origin https://github.com/usuario/repositorio.git

# Exibe os links de repositórios remotos conectados
git remote -v
```

---

## 4. 🔄 Fluxo de Trabalho Diário

O ciclo básico de salvamento e envio de alterações:

```powershell
# 1. Verifica o status dos arquivos (Untracked, Modified, Staged)
git status

# 2. Adiciona arquivos específicos ou todos (.) para a Staging Area
git add nome-do-arquivo.txt
git add .

# 3. Grava as alterações preparadas no histórico local
git commit -m "docs: descreve as alterações feitas"

# 4. Envia os commits locais para o repositório remoto no GitHub
git push origin main

# 5. Baixa e aplica as alterações mais recentes do GitHub no seu computador
git pull origin main
```

---

## 5. 🔍 Inspeção de Histórico e Logs

```powershell
# Exibe o histórico de commits ordenado do mais recente ao mais antigo
git log

# Exibe o histórico resumido em uma linha por commit
git log --oneline

# Mostra as diferenças de código entre arquivos não salvos na Staging Area
git diff

# Mostra detalhes e alterações específicas de um commit pelo seu HASH
git show 3fd207c
```

---

## 6. 🌿 Gerenciamento de Branches (Ramificações)

```powershell
# Lista todas as branches locais
git branch

# Cria uma nova branch
git branch nome-da-branch

# Muda para a branch especificada (método moderno)
git switch nome-da-branch

# Cria e muda para a nova branch no mesmo comando
git checkout -b nova-feature

# Mescla o conteúdo da branch secundária na branch atual
git merge nome-da-branch

# Deleta uma branch local que já foi mesclada
git branch -d nome-da-branch
```

---

## 7. 🛠️ Resolução, Descarte e Limpeza

```powershell
# Desfaz alterações em um arquivo não adicionado à staging (volta ao estado do último commit)
git restore nome-do-arquivo.txt

# Remove um arquivo da Staging Area (tira do git add) mantendo as edições
git restore --staged nome-do-arquivo.txt

# Guarda edições temporariamente sem fazer commit
git stash

# Restaura o último trabalho guardado no stash
git stash pop

# Cancela um rebase travado ou com problemas
git rebase --abort

# Encerra o estado de rebase quando não há conflitos pendentes
git rebase --quit
```

---

## 🎯 Padronização de Mensagens (Conventional Commits)

Adotar prefixos padronizados nas mensagens de commit facilita a leitura do histórico do repositório:

| Prefixo | Finalidade | Exemplo |
| :--- | :--- | :--- |
| **`feat:`** | Nova funcionalidade no código | `feat: adiciona filtro por data na consulta SQL` |
| **`fix:`** | Correção de um erro/bug | `fix: corrige sintaxe no script de limpeza` |
| **`docs:`** | Alterações na documentação (`.md`, comentários) | `docs: cria guia de comandos do git` |
| **`style:`** | Ajustes de formatação sem alterar lógica | `style: ajusta identação no código python` |
| **`refactor:`** | Reestruturação de código para melhoria de desempenho | `refactor: otimiza query de agrupamento` |
| **`chore:`** | Tarefas administrativas ou de configuração | `chore: atualiza pacotes do projeto` |