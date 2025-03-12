🚀 Projeto: Sistema de Cadastro de Usuários e Pets
Este projeto faz parte de uma atividade prática para o curso técnico em informática do Colégio ULBRA São Lucas. Os alunos vão criar um sistema de cadastro de usuários e pets usando Java e MySQL para consolidar os conceitos de programação orientada a objetos (POO).
________________________________________
🎯 Objetivo
•	Criar um sistema de cadastro simples para praticar manipulação de banco de dados, POO e interfaces gráficas.
•	Implementar um sistema de login e validação de senha forte.
•	Criar e manipular objetos utilizando boas práticas de programação.
________________________________________
📂 Estrutura de Pastas
css
CopiarEditar
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

________________________________________

🧪 Requisitos (Divididos por Ação)
🧑💻 Usuário
✅ Requisito 1 - Criar Classe Usuario
•	A classe Usuario.java deve conter os seguintes atributos: 
o	pkidusu (int)
o	nomeusu (String)
o	emailusu (String)
o	senhausu (String)
o	foneusu (String)
•	Crie os métodos:

// Construtor padrão e completo
public Usuario(int id, String nome, String email, String senha, String fone) {}

// Getters e Setters
public int getId() {}
public void setId(int id) {}
________________________________________
✅ Requisito 2 - Implementar Sistema de Login
1.	Criar uma tela de login (FrmLogin.java).
2.	Implementar método para validar o login:

public boolean validarLogin(String email, String senha) {
    // Lógica para verificar se o email e senha existem no banco
}
3.	Se o usuário não existir, abrir tela de cadastro (FrmCadUsuario.java).
________________________________________
✅ Requisito 3 - Validar Senha Forte
•	Crie um método na classe Usuario para validar a senha.
•	A senha deve ter no mínimo 8 caracteres e conter pelo menos: 
o	Uma letra maiúscula
o	Uma letra minúscula
o	Um número
o	Um caractere especial (@, #, $, %, etc.)
•	O que fazer: 
o	Crie um método chamado validarSenha(String senha) que retorna um boolean.
o	Use o método matches() com expressões regulares (regex) para validar.
________________________________________
✅ Requisito 4 - Confirmar Senha
•	Ao cadastrar o usuário, peça para o usuário digitar a senha duas vezes para confirmação.
•	Se as senhas não forem iguais, exiba uma mensagem de erro.
________________________________________
✅ Requisito 5 - Criar Tela de Cadastro de Usuário
1.	Criar FrmCadUsuario.java para permitir cadastro de usuário.
2.	Chamar o método salvar() na DAO ao clicar em salvar.
________________________________________
✅ Requisito 6 - Salvar Usuário no Banco de Dados
•	Implementar o método salvar() na UsuarioDAO.java:

public void salvar(Usuario usuario) {
    // Código para salvar no banco de dados
}
________________________________________
🐶 Pet
✅ Requisito 1 - Criar Classe Pet
•	A classe Pet.java deve conter os seguintes atributos: 
o	id (int)
o	nomePet (String)
o	raca (String)
o	anoNascimento (int)
o	sexo (String)
o	corPelo (String)
•	Crie os métodos:

// Construtor padrão e completo
public Pet(int id, String nomePet, String raca, int anoNascimento, String sexo, String corPelo) {}

// Getters e Setters
public int getId() {}
public void setId(int id) {}
________________________________________
✅ Requisito 2 - Criar Tela de Cadastro de Pet
1.	Criar FrmCadPet.java para permitir cadastro de pet.
2.	Chamar o método salvar() na DAO ao clicar em salvar.
________________________________________
✅ Requisito 3 - Salvar Pet no Banco de Dados
•	Implementar o método salvar() na PetDAO.java:

public void salvar(Pet pet) {
    // Código para salvar no banco de dados
}
________________________________________
💡 Requisitos Extras (Somente para Pet)
🔥 Extra 1 - Calcular Idade do Pet
•	Crie um método calcularIdade() na classe Pet para retornar a idade baseada no ano de nascimento.
•	Exemplo:

public int calcularIdade() {
   
}
________________________________________
🔥 Extra 2 - Validar Nome do Pet
•	Crie uma validação para que o nome do pet: 
o	Tenha pelo menos 3 caracteres
o	Não contenha números ou caracteres especiais
•	Se o nome for inválido, exiba uma mensagem de erro.
________________________________________
🔥 Extra 3 - Criar Método de Exibição de Informações
•	Crie um método exibirInformacoes() para retornar uma String com os dados formatados do pet.
•	Exemplo:
java
CopiarEditar
public String exibirInformacoes() {
    return String.format("Nome: %s\nRaça: %s\nIdade: %d\nSexo: %s\nCor do Pelo: %s", 
                          nomePet, raca, calcularIdade(), sexo, corPelo);
}
________________________________________
🔥 Extra 4 - Criar Método para Definir Sexo (M/F)
•	Crie um método setSexo() que aceite apenas valores "M" ou "F".
•	Se o valor for inválido, exiba uma mensagem de erro.
________________________________________
🏢 Banco de Dados
✅ Requisito 1 - Configurar Banco de Dados
1.	Criar uma classe ConnectionFactory.java para configurar o acesso ao MySQL.
2.	Criar as tabelas no MySQL:


CREATE TABLE usuario (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(100) NOT NULL,
    fone VARCHAR(15)
);

CREATE TABLE pet (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nomePet VARCHAR(100) NOT NULL,
    raca VARCHAR(50) NOT NULL,
    anoNascimento INT NOT NULL,
    sexo VARCHAR(10),
    corPelo VARCHAR(50)
);
________________________________________
🚀 Como Executar o Projeto
1.	Clone o repositório
2.	Abra o projeto no Netbeans
3.	Configure o banco de dados (Xampp)
4.	Execute o projeto
________________________________________
🏆 Desafio Extra
✅ Implementar o cálculo de idade do pet
✅ Criar exibição formatada das informações

