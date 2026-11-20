# 🚀 Guia de Configuração do Ambiente de Desenvolvimento

Este documento serve como um registo prático da instalação e configuração das ferramentas fundamentais utilizadas durante a jornada de estudos em programação: **Python**, **Jupyter**, **Visual Studio Code**, **Blackbox AI**, **Git** e **GitHub**.

## 📋 Conteúdo

1. [Python](#1-python)

2. [Jupyter (Notebook / JupyterLab)](#2-jupyter-notebook--jupyterlab)

3. [Visual Studio Code (VS Code)](#3-visual-studio-code-vs-code)

4. [Blackbox AI (Assistente de Código)](#4-blackbox-ai-assistente-de-código)

5. [Git](#5-git)

6. [Perfil e Configuração no GitHub](#6-perfil-e-configuração-no-github)

7. [Checklist de Verificação](#7-checklist-de-verificação)

## 1. 🐍 Python

O **Python** é a linguagem de programação principal utilizada nos estudos.

### 📥 Instalação e Ajustes Iniciais (Windows)

1. Transfira o instalador oficial em [python.org](https://www.python.org/downloads/) ou utilize o **Python Manager / Windows Store**.

2. **Ativar Suporte a Caminhos Longos (*Long Paths*):**

   * Na opção `Update setting now? [y/N]`, selecione **`y`**.

   * Permite ultrapassar o limite de 260 caracteres do Windows, evitando falhas na instalação de pacotes complexos.

3. **Adicionar ao PATH:**

   * Na opção `Add commands directory to your PATH now? [y/N]`, escolha **`y`**.

   * Permite executar comandos como `python`, `py` e `pip` em qualquer terminal.

4. **Instalar o CPython:**

   * Confirme a pergunta `Install CPython now? [Y/n]` com **`y`** para descarregar o *runtime* oficial.

### 🔍 Verificação no Terminal

Após reiniciar o sistema ou o terminal, execute os seguintes comandos para validar:

```bash
# Verificar a versão instalada
python --version
# ou via gerenciador de inicialização py
py --version

# Listar os runtimes Python ativos
py list

# Verificar o gestor de pacotes pip
pip --version
```

## 2. 🪐 Jupyter (Notebook / JupyterLab)

O **Jupyter** é um ambiente interativo ideal para análise de dados, prototipagem rápida e anotações de estudo em formato de cadernos (`.ipynb`).

### 📥 Instalação via `pip`

Abra o terminal (PowerShell, CMD ou Terminal integrado) e execute:

```bash
# Atualizar o pip antes da instalação
python -m pip install --upgrade pip

# Instalar o JupyterLab e Jupyter Notebook
pip install jupyterlab notebook
```

### 🚀 Formas de Utilização

1. **Via Terminal (Navegador):**

   * Para abrir a interface do JupyterLab:

     ```bash
     jupyter lab
     ```

   * Para abrir a interface clássica do Jupyter Notebook:

     ```bash
     jupyter notebook
     ```

2. **Via VS Code (Recomendado para estudos):**

   * O VS Code permite executar blocos de código (*cells*) de ficheiros `.ipynb` diretamente no editor, sem necessidade de abrir o browser.

## 3. 💻 Visual Studio Code (VS Code)

O **VS Code** é o ambiente de desenvolvimento (IDE/Editor) principal.

### 📥 Instalação

1. Transfira o instalador oficial em [code.visualstudio.com](https://code.visualstudio.com/).

2. Execute o assistente de instalação e marque as opções:

   * **Adicionar "Abrir com Code"** ao menu de contexto do Windows Explorer.

   * **Adicionar ao PATH** (para permitir o comando `code .` no terminal).

### 🧩 Extensões Recomendadas

Aceda ao separador de Extensões (`Ctrl + Shift + X`) e instale:

* **Python** (Microsoft): Suporte essencial com autocompletar, depuração e verificação de erros.

* **Jupyter** (Microsoft): Permite abrir, criar e executar notebooks `.ipynb` nativamente no VS Code.

* **Pylance** (Microsoft): Motor de análise estática e inteligência de código rápida.

* **Blackbox AI** (Blackboxapp): Assistente de IA para autocompletar, gerar código e tirar dúvidas (ver secção dedicada).

* **Portuguese (Brazil) Language Pack** *(Opcional)*: Interface traduzida para Português.

* **GitLens** *(Opcional)*: Visualização avançada do histórico de commits diretamente no código.

### ⚙️ Seleção do Interpretador e Kernel

1. **Ficheiros `.py`:** Prima `Ctrl + Shift + P`, digite `Python: Select Interpreter` e escolha o interpretador do sistema.

2. **Ficheiros `.ipynb` (Notebooks):** Abra o ficheiro no VS Code e clique no canto superior direito do documento em **Select Kernel** -> Escolha o ambiente Python instalado.

## 4. 🤖 Blackbox AI (Assistente de Código)

O **Blackbox AI** é um assistente de inteligência artificial que auxilia na escrita de código, explicação de trechos complexos, autocompletar inteligente e pesquisa direta dentro do editor.

### 📥 Instalação no VS Code

1. Abra o VS Code e vá até ao menu de Extensões (`Ctrl + Shift + X`).

2. Pesquise por **`Blackbox AI`** (desenvolvido por *Blackboxapp*).

3. Clique em **Instalar** e faça o login com a sua conta (se solicitado) para ativar os recursos de IA.

### 🛠️ Recursos e Utilização nos Estudos

* **Autocompletar Inteligente:** Sugere continuações de código em tempo real enquanto digita.

* **Geração de Código por Comentário:** Escreva um comentário a explicar o que deseja e pressione a atalho/tecla de sugestão (ex: `# função para calcular média de uma lista`).

* **Chat & Explicação de Erros:** Selecione um trecho de código ou mensagem de erro no terminal e utilize o painel da Blackbox para solicitar explicações ou correções (*Refactor/Explain*).

## 5. 🐙 Git

O **Git** é o sistema de controlo de versões para registar o histórico de alterações do projeto.

### 📥 Instalação

* **Windows:** Faça o download no site oficial [git-scm.com](https://git-scm.com/download/win).

* **Linux (Debian/Ubuntu):** `sudo apt update && sudo apt install git`

* **macOS:** `brew install git`

### ⚙️ Configuração Global da Identidade

Abra o terminal (Git Bash, PowerShell ou Terminal Linux/macOS) e execute:

```bash
# Configurar nome de utilizador
git config --global user.name "Seu Nome"

# Configurar email associado à conta do GitHub
git config --global user.email "seu.email@exemplo.com"

# Definir a branch padrão como 'main'
git config --global init.defaultBranch main

# Confirmar as configurações ativas
git config --list
```

## 6. 🌐 Perfil e Configuração no GitHub

O **GitHub** hospeda os repositórios remotos para partilha e cópia de segurança dos estudos.

### 🔑 Autenticação por Chave SSH (Recomendado)

Para enviar código sem pedir credenciais repetidamente:

1. **Gerar a Chave SSH:**

   ```bash
   ssh-keygen -t ed25519 -C "seu.email@exemplo.com"
   ```

   *(Prima `Enter` para aceitar a pasta predefinida).*

2. **Copiar a Chave Pública:**

   * Windows (PowerShell): `Get-Content ~/.ssh/id_ed25519.pub | Set-Clipboard`

   * Linux/macOS: `cat ~/.ssh/id_ed25519.pub` (e copie o texto gerado).

3. **Adicionar ao GitHub:**

   * Aceda a **GitHub -> Settings -> SSH and GPG keys -> New SSH key**.

   * Cole a chave copiada e guarde.

4. **Testar a Ligação:**

   ```bash
   ssh -T git@github.com
   ```

### 🖼️ Personalização do Perfil (Profile README)

1. Crie um novo repositório público com o **mesmo nome do seu utilizador** (ex: `seu-usuario/seu-usuario`).

2. Marque a opção **"Add a README file"**.

3. Edite o ficheiro com informações pessoais, tecnologias em aprendizagem, links de contacto e estatísticas.

## 7. ✅ Checklist de Verificação

* \[ \] Python instalado e reconhecido no terminal (`py --version`).

* \[ \] Suporte a caminhos longos (*long paths*) ativado no Windows.

* \[ \] JupyterLab/Notebook instalado via `pip install jupyterlab notebook`.

* \[ \] VS Code instalado com as extensões **Python**, **Jupyter** e **Blackbox AI**.

* \[ \] Blackbox AI configurado e a funcionar no VS Code.

* \[ \] Teste de execução de célula de código num ficheiro `.ipynb` no VS Code.

* \[ \] Git configurado globalmente (`user.name` e `user.email`).

* \[ \] Chave SSH criada e associada à conta do GitHub.

* \[ \] Primeiro repositório clonado ou publicado via `git push`.

---
*Documentação elaborada para organização pessoal do ambiente de desenvolvimento.*