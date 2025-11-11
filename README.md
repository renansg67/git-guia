# 🚀📚 Guia Essencial de Comandos Git ✨

Este documento apresenta os **comandos Git mais utilizados** e suas funções primárias para gerenciar o versionamento de projetos de forma eficiente.

---

### **1. 🛠️ Configuração e Inicialização (Setup)**

| Comando | Descrição |
| :--- | :--- |
| `git init` | 🎯 Inicializa um novo repositório Git no diretório atual (local). |
| `git clone <url>` | 📥 Baixa um repositório remoto completo para a sua máquina. |
| `git config --global user.name "Seu Nome"` | 👤 Define o **nome do usuário** para todos os repositórios locais. |
| `git config --global user.email "seu@email.com"` | 📧 Define o **e-mail do usuário** para todos os repositórios locais. |

---

### **2. 🔍 Gerenciamento de Status e Arquivos (Staging)**

| Comando | Descrição |
| :--- | :--- |
| `git status` | 🚦 Exibe o estado da árvore de trabalho e da *staging area*. **Sempre útil!** |
| `git add <arquivo>` | ✅ Adiciona um arquivo específico à *staging area*. |
| `git add .` | ➕ Adiciona todos os arquivos modificados e novos à *staging area*. |
| `git restore <arquivo>` | 🔙 Descarta as alterações não *staged*. |
| `git reset <arquivo>` | 🗑️ Remove um arquivo da *staging area*. |

---

### **3. 💾 Commit (Salvando Alterações)**

| Comando | Descrição |
| :--- | :--- |
| `git commit -m "Mensagem"` | ✍️ Cria um **novo commit**. |
| `git commit --amend` | ✏️ Altera o **último commit** (mensagem ou conteúdo). |
| `git commit --amend --no-edit` | 🔁 Atualiza o último commit mantendo a **mesma mensagem**. |

---

### **4. 📜 Histórico e Logs**

| Comando | Descrição |
| :--- | :--- |
| `git log` | 📖 Exibe o histórico de commits. |
| `git log --oneline` | ⚡ Histórico resumido (uma linha por commit). |
| `git diff` | 🔀 Mostra as diferenças entre *working directory* e *staging area*. |
| `git show <hash>` | 🔍 Detalhes de um commit específico. |

---

### **5. 🌱 Branches (Ramificações)**

| Comando | Descrição |
| :--- | :--- |
| `git branch` | 🌲 Lista branches locais. |
| `git branch <nome-branch>` | ➕ Cria uma nova branch. |
| `git switch <nome-branch>` | ➡️ Muda para a branch especificada. |
| `git merge <branch>` | 🤝 Mescla a branch especificada na atual. |
| `git branch -d <branch>` | ❌ Remove uma branch local. |

---

### **6. 🌐 Repositórios Remotos (Push/Pull)**

| Comando | Descrição |
| :--- | :--- |
| `git remote -v` | 🔍 Exibe URLs remotas. |
| `git remote add origin <url>` | 🔗 Conecta ao repositório remoto. |
| `git fetch origin` | ⬇️ Baixa dados remotos, **sem mesclar**. |
| `git pull origin <branch>` | ⬇️ Baixa e mescla alterações do remoto. |
| `git push origin <branch>` | ⬆️ Envia commits locais. |
| `git push --force` | ⚠️ Sobrescreve o remoto (use com cuidado). |
| `git pull --rebase` | 🔄 Atualiza sem criar merge extra. |

---

### **7. ✏️ Atualizar um Commit Após o Push**

#### 🧩 **Caso 1 – Antes de dar o push**
Você cometeu algo, notou um erro e ainda **não enviou o commit** para o GitHub.

```bash
# Faça as correções necessárias
git add nome_do_arquivo

# Atualize o último commit (mantendo a mesma mensagem)
git commit --amend --no-edit

# ou altere também a mensagem
git commit --amend -m "nova mensagem corrigida"
```

✅ Como o commit ainda não foi enviado, não há risco de sobrescrever histórico remoto.

#### 🚀 **Caso 2 – Após já ter dado o push**

Você já enviou o commit e quer atualizar o mesmo commit remoto com uma pequena correção.

```bash
# Faça as alterações e adicione novamente
git add nome_do_arquivo

# Atualize o commit (mantendo ou alterando a mensagem)
git commit --amend --no-edit

# Envie novamente sobrescrevendo o commit remoto
git push --force
```

#### ⚠️ Atenção:
Use `--force` apenas se:
- o repositório for pessoal; ou  
- ninguém mais tiver feito `pull` desde o último push.

#### ✅ Alternativa segura:
```bash
git add nome_do_arquivo
git commit -m "fix: pequeno ajuste após commit anterior"
git push
```

### **8. 💡 Boas Práticas: Nomes de Commits**

| Tipo         | Uso                               | Exemplo                              |
| :----------- | :-------------------------------- | :----------------------------------- |
| **feat**     | ✨ Nova funcionalidade.            | `feat: adicionar autenticação`       |
| **fix**      | 🐞 Correção de bug.               | `fix(login): corrigir erro de senha` |
| **docs**     | 📄 Atualização de documentação.   | `docs: atualizar README`             |
| **style**    | 💅 Formatação sem alterar código. | `style: aplicar prettier`            |
| **refactor** | ♻️ Refatoração.                   | `refactor: simplificar função`       |
| **test**     | 🧪 Testes.                        | `test: adicionar casos de soma`      |
| **chore**    | ⚙️ Tarefas auxiliares.            | `chore: atualizar dependências`      |
