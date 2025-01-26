
## Parte 1: [[Git]] e [[GitHub]]

### Introdução ao Versionamento de Scripts

O versionamento de scripts é essencial para manter um histórico de alterações no código, possibilitar colaboração em equipe e gerenciar diferentes versões do projeto. O Git é uma ferramenta de controle de versão distribuído, enquanto o GitHub é uma plataforma de hospedagem de repositórios Git na nuvem que facilita a colaboração e o compartilhamento de código.

### Configurando o Git com o GitHub no [[Visual Studio Code]]

1. **Instale o Git:** Baixe e instale o Git em [git-scm.com](https://git-scm.com/).
2. **Configuração inicial:** Configure seu nome de usuário e e-mail no terminal do Git:
    
    ```bash
    git config --global user.name "Seu Nome"
    git config --global user.email "seuemail@email.com"
    ```
    
3. **Instale o Visual Studio Code (VS Code):** Baixe e instale em [code.visualstudio.com](https://code.visualstudio.com/).
4. **Extensão GitHub no VS Code:**
    - Abra o VS Code e vá para a aba de extensões.
    - Instale a extensão "GitHub Pull Requests and Issues".
5. **Configure a autenticação com o GitHub usando Tokens:**
    - Acesse as configurações da sua conta no GitHub.
    - Vá para **Developer Settings > Personal Access Tokens > Tokens (classic)** e clique em **Generate new token**.
    - Escolha as permissões desejadas (por exemplo, repositórios públicos e privados) e defina uma validade para o token (ou ilimitado, se preferir).
    - Copie o token gerado (ele não será mostrado novamente).
    - No VS Code, quando solicitado, cole o token gerado para autenticar sua conta do GitHub.
6. **Clonando um Repositório no VS Code:**
    - No menu do VS Code, clique em **View > Command Palette**.
    - Digite "Git: Clone" e selecione a opção.
    - Cole o link HTTPS ou SSH do repositório GitHub.
    - Escolha um diretório local para clonar o repositório.
7. **Sincronizando Alterações no VS Code:**
    - Utilize a aba de controle de fonte (Source Control) no VS Code para gerenciar alterações.
    - Adicione arquivos ao stage, faça commits e envie as alterações para o repositório remoto diretamente pela interface do VS Code.

### Principais Comandos do Git e Integração com o GitHub

#### 1. Inicialização de Repositório

- **Local:**
    
    ```bash
    git init
    ```
    
    Cria um repositório Git local no diretório atual.
    
- **Remoto:** Crie um novo repositório no GitHub e copie o link HTTPS ou SSH.
    
    **Adicione o repositório remoto:**
    
    ```bash
    git remote add origin https://github.com/usuario/nome_repositorio.git
    ```
    

#### 2. `git commit`

- O `commit` é usado para salvar alterações locais no repositório.
- **Passos:**
    1. Adicione os arquivos ao stage com `git add nome_do_arquivo` ou `git add .` (para adicionar todos os arquivos modificados).
    2. Salve as alterações com `git commit -m "Mensagem descritiva"`.
- **Exemplo:**
    
    ```bash
    git add script.py
    git commit -m "Corrigido bug na função de cálculo"
    ```
    

#### 3. `git pull`

- O `pull` atualiza o repositório local com as alterações feitas no repositório remoto.
- **Comando:**
    
    ```bash
    git pull origin main
    ```
    

#### 4. `git push`

- O `push` envia as alterações locais para o repositório remoto no GitHub.
- **Comando:**
    
    ```bash
    git push origin main
    ```
    

#### 5. Clonando um Repositório

- Para trabalhar em um repositório já existente no GitHub:
    
    ```bash
    git clone https://github.com/usuario/nome_repositorio.git
    ```
    

#### 6. Trabalhando com Branches

- Crie uma nova branch:
    
    ```bash
    git branch nome_da_branch
    ```
    
- Mude para a nova branch:
    
    ```bash
    git checkout nome_da_branch
    ```
    
- Envie a branch para o GitHub:
    
    ```bash
    git push origin nome_da_branch
    ```
    
- Faça merge de uma branch:
    
    ```bash
    git checkout main
    git merge nome_da_branch
    ```
    

### Boas Práticas ao Usar Git e GitHub

- Sempre escreva mensagens de commit claras e descritivas.
- Use branches para desenvolver novas funcionalidades sem impactar a branch principal.
- Sincronize frequentemente seu repositório local com o remoto para evitar conflitos.
- Utilize Pull Requests no GitHub para revisão de código antes de mesclar alterações.

### Exercício Prático

1. Crie um repositório no GitHub.
2. Clone o repositório para sua máquina local usando o VS Code.
3. Crie um arquivo simples (ex.: `README.md`) e adicione uma descrição do projeto.
4. Use os comandos `git add`, `git commit` e `git push` para enviar o arquivo ao repositório remoto.
5. Crie uma nova branch, faça alterações e envie para o GitHub.
6. Abra um Pull Request no GitHub para mesclar a nova branch com a branch principal.

---

## Parte 2: [[SQL]]

### Introdução a Bancos de Dados

Bancos de dados são sistemas para armazenar, organizar e gerenciar grandes volumes de informações. O SQL (Structured Query Language) é a linguagem padrão para interagir com bancos de dados relacionais.

### Configuração de um Banco de Dados com [[MySQL]]

#### 1. Instalação do MySQL

1. Acesse o site oficial do MySQL ([https://dev.mysql.com/](https://dev.mysql.com/)).
2. Baixe e instale o MySQL Community Server.
3. Durante a instalação, configure a senha do usuário `root`.

#### 2. Configuração

1. Inicie o servidor MySQL após a instalação.
2. Acesse o MySQL pelo terminal:
    
    ```bash
    mysql -u root -p
    ```
    
3. Insira a senha configurada durante a instalação.

### Comandos Básicos de SQL

#### 1. Criação de Banco de Dados

```sql
CREATE DATABASE loja;
```

#### 2. Seleção de Banco de Dados

```sql
USE loja;
```

#### 3. Criação de Tabela

```sql
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    preco DECIMAL(10, 2) NOT NULL,
    quantidade INT NOT NULL
);
```

#### 4. Inserção de Dados

```sql
INSERT INTO produtos (nome, preco, quantidade)
VALUES ('Produto A', 50.00, 10),
       ('Produto B', 30.00, 5),
       ('Produto C', 100.00, 2);
```

#### 5. Consulta de Dados

```sql
SELECT * FROM produtos;
```

#### 6. Atualização de Dados

```sql
UPDATE produtos
SET preco = 60.00
WHERE id = 1;
```

#### 7. Exclusão de Dados

```sql
DELETE FROM produtos
WHERE id = 2;
```

### Conexão do MySQL com R

1. **Instale os pacotes necessários no R:**
    
    ```R
    install.packages("DBI")
    install.packages("RMySQL")
    ```
    
2. **Estabeleça a conexão:**
    
    ```R
    library(DBI)
    
    # Conectando ao banco de dados MySQL
    conexao <- dbConnect(RMySQL::MySQL(), 
                         dbname = "loja", 
                         host = "localhost", 
                         user = "root", 
                         password = "sua_senha")
    ```
    
3. **Executando consultas:**
    
    ```R
    # Listar tabelas no banco
    dbListTables(conexao)
    
    # Realizar uma consulta
    produtos <- dbGetQuery(conexao, "SELECT * FROM produtos")
    print(produtos)
    ```
    
4. **Encerrando a conexão:**
    
    ```R
    dbDisconnect(conexao)
    ```
    

### Exercício Prático

1. Instale o MySQL e configure um banco de dados chamado `loja`.
2. Crie a tabela `produtos` com as colunas `id`, `nome`, `preco` e `quantidade`.
3. Insira ao menos três registros na tabela.
4. Conecte-se ao banco de dados usando R e realize as seguintes operações:
    - Liste todas as tabelas.
    - Recupere os dados da tabela `produtos`.
    - Atualize os preços de um produto e visualize a mudança no R.

---