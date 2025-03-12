# 🚀 Projeto: Sistema de Cadastro de Usuários e Pets

Este projeto faz parte de uma atividade prática para o curso técnico em informática do Colégio ULBRA São Lucas. Os alunos vão criar um sistema de cadastro de usuários e pets usando Java e MySQL para consolidar os conceitos de programação orientada a objetos (POO).

## 📋 Introdução Técnica

Este sistema utiliza as seguintes tecnologias e conceitos:
- **Java**: Linguagem de programação principal
- **MySQL**: Sistema de gerenciamento de banco de dados
- **POO**: Programação Orientada a Objetos
- **DAO**: Data Access Object (padrão para persistência de dados)
- **Swing**: Framework para interfaces gráficas

## 🎯 Objetivo

- Criar um sistema de cadastro simples para praticar manipulação de banco de dados, POO e interfaces gráficas.
- Implementar um sistema de login e validação de senha forte.
- Criar e manipular objetos utilizando boas práticas de programação.

## 🖥️ Pré-requisitos

- Java JDK 8 ou superior
- MySQL 5.7 ou superior
- NetBeans IDE 8.2 ou superior
- XAMPP (para gerenciamento do MySQL)
- Conhecimentos básicos em Java e SQL

## 📂 Estrutura de Pastas

```
src/main/java/com/seuprojeto/
├── br.ulbra.entity/
│   ├── Usuario.java
│   ├── Pet.java
├── br.ulbra.dao/
│   ├── UsuarioDAO.java
│   ├── PetDAO.java
│   ├── ConnectionFactory.java
├── br.ulbra.view/
│   ├── FrmLogin.java
│   ├── FrmPrincipal.java
│   ├── FrmCadUsuario.java
│   ├── FrmCadPet.java
```

## 🔣 Legenda

- ✅ Requisito obrigatório - Deve ser implementado
- 🔥 Requisito extra - Implementação opcional para desafio adicional
- 🧑💻 Usuário - Relacionado ao cadastro e gerenciamento de usuários
- 🐶 Pet - Relacionado ao cadastro e gerenciamento de pets
- 🏢 Banco de Dados - Relacionado à configuração e manipulação do banco de dados


### 🏢 Banco de Dados

## 📐 Diagrama Entidade Relacionamento (DER)

```mermaid
erDiagram
    USUARIO {
        int id PK
        string nome
        string email
        string senha
        string fone
        string cpf
        string endereco
    }
    PET {
        int id PK
        string nomePet
        string raca
        int anoNascimento
        string sexo
        string corPelo
    }
```

## 🧪 Requisitos (Divididos por Ação)

### 🧑💻 Usuário

#### ✅ Requisito 1 - Criar Classe Usuario

- A classe Usuario.java deve conter os seguintes atributos: 
  - pkidusu (int)
  - nomeusu (String)
  - emailusu (String)
  - senhausu (String)
  - foneusu (String)
  - cpfusu (String)
  - enderecousu (String)
- Crie os métodos:

```java
// Construtor padrão e completo
public Usuario(int id, String nome, String email, String senha, String fone, String cpf, String endereco) {}

// Getters e Setters
public int getId() {}
public void setId(int id) {}
// ... outros getters e setters
```

#### ✅ Requisito 2 - Implementar Sistema de Login

1. Criar uma tela de login (FrmLogin.java).
2. Implementar método para validar o login:

```java
public boolean validarLogin(String email, String senha) {
    // Lógica para verificar se o email e senha existem no banco
}
```

3. Se o usuário não existir, abrir tela de cadastro (FrmCadUsuario.java).

#### ✅ Requisito 3 - Validar Senha Forte

- Crie um método na classe Usuario para validar a senha.
- A senha deve ter no mínimo 8 caracteres e conter pelo menos: 
  - Uma letra maiúscula
  - Uma letra minúscula
  - Um número
  - Um caractere especial (@, #, $, %, etc.)
- O que fazer: 
  - Crie um método chamado validarSenha(String senha) que retorna um boolean.
  - Use o método matches() com expressões regulares (regex) para validar.

#### ✅ Requisito 4 - Confirmar Senha

- Ao cadastrar o usuário, peça para o usuário digitar a senha duas vezes para confirmação.
- Se as senhas não forem iguais, exiba uma mensagem de erro.

#### ✅ Requisito 5 - Criar Tela de Cadastro de Usuário

1. Criar FrmCadUsuario.java para permitir cadastro de usuário.
2. Chamar o método salvar() na DAO ao clicar em salvar.

#### ✅ Requisito 6 - Salvar Usuário no Banco de Dados

- Implementar o método salvar() na UsuarioDAO.java:

```java
public void salvar(Usuario usuario) {
    // Código para salvar no banco de dados
}
```

#### ✅ Requisito 7 - Validar CPF

- Crie um método na classe Usuario para validar o CPF.
- O método deve verificar se o CPF é válido (formato e dígitos verificadores).
- Exemplo:

```java
public boolean validarCPF(String cpf) {
    // Implementação da validação de CPF
}
```

### 🐶 Pet

#### ✅ Requisito 1 - Criar Classe Pet

- A classe Pet.java deve conter os seguintes atributos: 
  - id (int)
  - nomePet (String)
  - raca (String)
  - anoNascimento (int)
  - sexo (String)
  - corPelo (String)
- Crie os métodos:

```java
// Construtor padrão e completo
public Pet(int id, String nomePet, String raca, int anoNascimento, String sexo, String corPelo) {}

// Getters e Setters
public int getId() {}
public void setId(int id) {}
```

#### ✅ Requisito 2 - Criar Tela de Cadastro de Pet

1. Criar FrmCadPet.java para permitir cadastro de pet.
2. Chamar o método salvar() na DAO ao clicar em salvar.

#### ✅ Requisito 3 - Salvar Pet no Banco de Dados

- Implementar o método salvar() na PetDAO.java:

```java
public void salvar(Pet pet) {
    // Código para salvar no banco de dados
}
```

### 💡 Requisitos Extras (Somente para Pet)

#### 🔥 Extra 1 - Calcular Idade do Pet

- Crie um método calcularIdade() na classe Pet para retornar a idade baseada no ano de nascimento.
- Exemplo:

```java
public int calcularIdade() {
    Calendar cal = Calendar.getInstance();
    int anoAtual = cal.get(Calendar.YEAR);
    return anoAtual - this.anoNascimento;
}
```

#### 🔥 Extra 2 - Validar Nome do Pet

- Crie uma validação para que o nome do pet: 
  - Tenha pelo menos 3 caracteres
  - Não contenha números ou caracteres especiais
- Se o nome for inválido, exiba uma mensagem de erro.

#### 🔥 Extra 3 - Criar Método de Exibição de Informações

- Crie um método exibirInformacoes() para retornar uma String com os dados formatados do pet.
- Exemplo:

```java
public String exibirInformacoes() {
    return String.format("Nome: %s\nRaça: %s\nIdade: %d\nSexo: %s\nCor do Pelo: %s", 
                          nomePet, raca, calcularIdade(), sexo, corPelo);
}
```

#### 🔥 Extra 4 - Criar Método para Definir Sexo (M/F)

- Crie um método setSexo() que aceite apenas valores "M" ou "F".
- Se o valor for inválido, exiba uma mensagem de erro.


## 🚀 Como Executar o Projeto

1. **Clone o repositório**
   ```
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```

2. **Configure o MySQL**
   - Inicie o XAMPP e ative o serviço MySQL
   - Acesse o phpMyAdmin (http://localhost/phpmyadmin)
   - Crie um banco de dados chamado `cadastro_pet`
   - Execute os scripts SQL fornecidos na seção "Banco de Dados"

3. **Configure o projeto no NetBeans**
   - Abra o NetBeans IDE
   - Vá para "File" > "Open Project" e selecione a pasta do projeto
   - Certifique-se de que as bibliotecas Java necessárias estão incluídas (MySQL Connector/J)

4. **Compile e execute o projeto**
   - Clique com o botão direito no projeto e selecione "Clean and Build"
   - Execute o projeto clicando em "Run" ou pressionando F6

## 📅 Cronograma Sugerido

| Semana | Atividade |
|--------|-----------|
| Dia 1 | Configuração do ambiente e banco de dados - Implementação das classes de entidade (Usuario e Pet) |
| Dia 2 |  Implementação das classes DAO  - Criação das interfaces gráficas                                 |
| Dia 3 |Testes e correção de bugs                                                                          |
| Dia 4 | Apresentação do projeto                                                                           |



## 🤝 Contribuição e Suporte

Para dúvidas ou sugestões sobre o projeto, entre em contato com o professor responsável ou abra uma issue no repositório do projeto.

- **E-mail de contato**: jeferson.leon@ulbra.br
