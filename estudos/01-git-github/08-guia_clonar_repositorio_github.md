# Guia Prático: Como Clonar um Repositório do GitHub

Este guia orienta o processo de clonar (baixar com versionamento) repositórios do GitHub para a sua máquina local, utilizando o **Terminal** ou o **Visual Studio Code (VS Code)**.

---

## 📌 Requisitos Prévios

1. **Git Instalado:** Verifique se o Git está instalado no seu computador.
   - Abra o terminal e digite: `git --version`
   - Caso não esteja instalado, baixe em [git-scm.com](https://git-scm.com/).
2. **URL do Repositório:** 
   - No GitHub, acesse a página do repositório.
   - Clique no botão verde **`<> Code`**.
   - Na aba **HTTPS**, copie o link (exemplo: `https://github.com/usuario/nome-do-repo.git`).

---

## 🖥️ Método 1: Clonando pelo Terminal (Prompt / PowerShell / Bash)

Ideal para quem prefere linhas de comando rápidas.

### Passo 1: Acesse a pasta de destino
Para salvar o repositório dentro da pasta `Documents\github`:

```bash
# Windows (PowerShell ou Command Prompt)
cd %USERPROFILE%\Documents
mkdir github 2>nul
cd github
```

*(No macOS ou Linux, use `cd ~/Documents && mkdir -p github && cd github`)*

### Passo 2: Execute o comando de clonagem
Substitua a URL abaixo pela URL do seu repositório:

```bash
git clone https://github.com/usuario/nome-do-repo.git
```

### Passo 3: Acesse o projeto clonado
```bash
cd nome-do-repo
```

---

## 💙 Método 2: Clonando pelo VS Code

Método visual e recomendado para quem já utiliza o VS Code como editor principal.

1. **Abra a Paleta de Comandos:**
   - Pressione `Ctrl + Shift + P` (Windows/Linux) ou `Cmd + Shift + P` (macOS).
2. **Inicie o Comando:**
   - Digite `Git: Clone` e pressione **Enter**.
3. **Cole a URL:**
   - Cole a URL do repositório HTTPS e pressione **Enter**. 
   - *(Alternativa: Clique em **Clone from GitHub** para listar seus repositórios diretamente).*
4. **Escolha o Destino:**
   - Na janela do explorador de arquivos, navegue até `Documentos` > `github` (crie a pasta se necessário).
   - Clique em **Select as Repository Destination** (ou *Selecionar como Destino do Repositório*).
5. **Abra o Projeto:**
   - Na notificação no canto inferior direito, clique em **Open** (*Abrir*).

---

## ❓ Resolução de Problemas Frequentes

### 1. `git is not recognized as an internal or external command`
* **Causa:** O Git não está instalado ou o terminal foi aberto antes da instalação ser finalizada.
* **Solução:** Baixe e instale o Git, feche todas as janelas do terminal/VS Code e abra-os novamente.

### 2. Repositório Privado (Erro 403 / Authentication Failed)
* **Causa:** A máquina local não tem autorização para acessar o repositório privado.
* **Solução:**
  - **VS Code:** Ele exibirá uma janela pop-up solicitando login no GitHub. Autorize a aplicação.
  - **Terminal:** Configure o acesso via Token de Acesso Pessoal (PAT) ou autentique via GitHub CLI (`gh auth login`).

### 3. A pasta já existe e não está vazia (`destination path already exists and is not an empty directory`)
* **Causa:** Já existe uma pasta com o mesmo nome no diretório selecionado.
* **Solução:** Exclua/renomeie a pasta local existente ou altere o nome da pasta de destino na clonagem:
  ```bash
  git clone https://github.com/usuario/nome-do-repo.git nome-da-nova-pasta
  ```

---

## 🚀 Resumo de Comandos Rápidos

| Ação | Comando |
| :--- | :--- |
| **Clonar repo** | `git clone <URL>` |
| **Verificar status** | `git status` |
| **Verificar histórico** | `git log --oneline` |
| **Baixar novidades** | `git pull` |