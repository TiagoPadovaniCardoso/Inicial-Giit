# 🧩 Aula Prática – Git Local (sem GitHub)

## 🎯 Objetivo
Aprender a utilizar o **Git** localmente para versionar projetos, criando commits, branches e manipulando o histórico de forma segura.

---

## 🧱 1. Configuração inicial

Esses comandos configuram o nome e o e-mail do usuário (necessário para registrar os commits).

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"   # Define o VS Code como editor padrão (opcional)
git config --list                                # Verifica as configurações atuais
```

---

## 📂 2. Criar e iniciar um repositório

```bash
mkdir meu_projeto
cd meu_projeto
git init
```

> O comando `git init` cria um repositório local, gerando a pasta oculta `.git`.

---

## 🏷️ 3. Alterar a branch padrão de `master` para `main`

Por padrão, o Git pode criar a branch inicial como **master**.  
Para padronizar e seguir boas práticas, altere para **main**:

```bash
git branch -m master main
```

Se quiser definir **main** como padrão para novos repositórios:

```bash
git config --global init.defaultBranch main
```

---

## 📄 4. Criar arquivos e verificar status

```bash
echo "Meu primeiro arquivo" > readme.txt
git status
```

> `git status` mostra arquivos novos, modificados ou prontos para commit.

---

## 🧺 5. Adicionar arquivos à área de staging

```bash
git add readme.txt       # adiciona um arquivo específico
git add .                # adiciona todos os arquivos do diretório
git status
```

> A área de staging é onde os arquivos ficam “preparados” antes do commit.

---

## 💾 6. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit - adiciona readme.txt"
```

> Um commit é o “salvamento” oficial no histórico do repositório.

---

## 🔍 7. Ver histórico e detalhes

```bash
git log
git log --oneline
git show
```

> Use `--oneline` para visualizar um resumo simplificado.

---

## ✏️ 8. Editar arquivos e registrar mudanças

```bash
echo "Adicionando nova linha" >> readme.txt
git status
git diff
git add readme.txt
git commit -m "Atualiza readme.txt com nova linha"
```

> `git diff` mostra as diferenças entre a versão atual e a anterior.

---

## ♻️ 9. Desfazer mudanças

```bash
git restore readme.txt              # descarta mudanças não adicionadas
git restore --staged readme.txt     # remove da área de staging
```

> Ideal para corrigir erros antes de um commit.

---

## 🌿 10. Criar e alternar entre branches

```bash
git branch                         # lista branches
git branch nova_funcionalidade     # cria nova branch
git switch nova_funcionalidade     # muda para ela
```

> Cada branch é uma linha independente de desenvolvimento.

---

## 🧬 11. Fazer commits em outra branch

```bash
echo "Nova feature" > feature.txt
git add feature.txt
git commit -m "Adiciona nova feature"
```

---

## 🔀 12. Voltar e mesclar mudanças

```bash
git switch main
git merge nova_funcionalidade
```

> Junta as alterações da branch `nova_funcionalidade` na `main`.

---

## 🗑️ 13. Excluir branches locais

```bash
git branch -d nova_funcionalidade
```

---

## 🧹 14. Ignorar arquivos com `.gitignore`

Crie um arquivo chamado `.gitignore` e adicione:

```
*.log
*.tmp
node_modules/
```

Depois:

```bash
git add .gitignore
git commit -m "Adiciona arquivo .gitignore"
```

---

## 🧠 15. Visualizar informações úteis

```bash
git status
git log --oneline --graph --decorate
git diff
git show HEAD
```

> `--graph` mostra o histórico com ramificações visualmente.

---

## 💡 16. Exemplo de fluxo completo

```bash
git init
echo "Aula prática Git local" > readme.txt
git add .
git commit -m "Primeiro commit"
git branch dev
git switch dev
echo "Nova versão em desenvolvimento" >> readme.txt
git add .
git commit -m "Atualiza versão dev"
git switch main
git merge dev
git log --oneline --graph
```

---

## Comandos Git Básicos 💻

### 1. `git clone` 🧑‍🤝‍🧑

O comando `git clone` é utilizado para criar uma cópia local de um repositório remoto. Isso é útil quando você deseja começar a trabalhar em um projeto que já existe em um repositório online (como GitHub, GitLab, etc.).

**Exemplo de uso:**
```bash
git clone https://github.com/usuario/repo.git
```

---

### 2. `git add`➕

O comando `git add` é usado para adicionar alterações feitas nos arquivos ao "staging area" (área de preparação), ou seja, ele coloca os arquivos para serem commitados. Ele pode ser usado tanto para arquivos individuais quanto para todos os arquivos modificados.

**Exemplo de uso:**
```bash
git add nome-do-arquivo.ext

git add .
```

---

### 3. `git commit`🖥️

O comando `git commit` registra as alterações no repositório local. Após usar o git add, você deve executar o git commit para salvar as mudanças de forma permanente no histórico do repositório.

**Exemplo de uso:**
```bash
git commit -m "Mensagem de commit"
```

---

### 4. `git push`🫸

O comando `git push` é usado para enviar os commits locais para o repositório remoto. Isso é o que permite que outras pessoas vejam suas alterações e que seu trabalho seja compartilhado.

**Exemplo de uso:**
```bash
git push origin nome-da-branch
```

---

### 5. 👨‍💻Fluxo básico de trabalho no Git:

   - `git clone` para obter o repositório.
  
   - `git add` para preparar as mudanças.
  
   - `git commit` para registrar as mudanças no seu repositório local.
  
   - `git push` para enviar essas mudanças ao repositório remoto.

---

## Como usar o `GitFluence`🤖:

**Gitfluence** é uma ferramenta poderosa e intuitiva que utiliza **Inteligência Artificial (IA)** para simplificar a sua interação com o Git.

 - Se você gasta tempo procurando a sintaxe exata de comandos Git complexos, o Gitfluence está aqui para transformar seu fluxo de trabalho.

1.  **Descreva a Tarefa:** Insira o que você deseja fazer em linguagem natural.
    * *Exemplo:* "fazer um commit com a mensagem 'feature completa'"
2.  **Gere o Comando:** A IA processa sua intenção e gera o comando Git correto.
    * *Resultado:* `git commit -m "feature completa"`
3.  **Cole e Execute:** Copie o comando e cole-o diretamente no seu terminal.

---

## 🤝 Como Adicionar Colaboradores a um Repositório Privado

Para compartilhar seu repositório privado com outras pessoas e permitir que elas acessem, editem ou contribuam com o código, é necessário adicioná-las como colaboradoras.

Siga o passo a passo abaixo para gerenciar o acesso no GitHub:

## ⚙️ Passo a Passo para Adicionar Colaboradores

1.  **Acesse seu Repositório no GitHub**
    * Vá até o site `https://github.com` e entre na sua conta.
    * Abra o repositório privado desejado.

2.  **Abra as Configurações do Repositório**
    * No menu superior do repositório, clique na aba **"Settings"** (Configurações).

3.  **Vá até a Seção de Acesso**
    * No menu lateral esquerdo, clique em **"Collaborators"** ou **"Manage access"** (Gerenciar acesso).

4.  **Adicione um Novo Colaborador**
    * Clique no botão **"Add people"** (Adicionar pessoas).

5.  **Procure o Usuário**
    * Digite o **nome de usuário** ou **e-mail** da pessoa que você quer adicionar e selecione-a na lista que aparece.

6.  **Defina as Permissões**
    * Escolha o nível de acesso que a pessoa terá:
        * **Read (Leitura):** Apenas visualiza o repositório.
        * **Write (Escrita):** Pode enviar (`push`) alterações.
        * **Admin (Administrador):** Controle total sobre o repositório.

7.  **Envie o Convite**
    * Clique em **"Add collaborator"** (Adicionar colaborador).

> **Observação:** O colaborador receberá um convite por e-mail ou no GitHub e precisará **aceitar o convite** para começar a colaborar.

---

## 📘 Créditos

Material criado para fins educacionais na aula prática de **Git Local**,  
ministrada por *Anderson R. M. Gomes* 🧑‍🏫

---

**🚀 Próximos passos:**  
Na próxima aula, você aprenderá a conectar este repositório local ao GitHub com os comandos `git remote`, `git push` e `git pull`.
