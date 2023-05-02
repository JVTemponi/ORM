# ORM

Trabalho Projeto de Software - ORM


## ORM (Object-Relational Mapping) 
  
É a técnica que permite consultar e manipular dados de um banco de dados relacional utilizando um paradigma orientado a objetos. Isso significa que ao invés de escrever um comando SQL diretamente para consultar ou manipular os dados,é possível usar uma camada de abstração que traduz essas operações para a linguagem de programação usada na aplicação.

O acesso a banco de dados por ORM comumente é realizado através de um conjunto de bibliotecas ou frameworks que fornecem as ferramentas necessárias para realizar operações CRUD (Create, Read, Update, Delete). Essas bibliotecas mapeiam as tabelas do banco de dados para classes em uma linguagem de programação, permitindo manipular objetos ao invés de tabelas.

Durante o desenvolvimento de uma aplicação utilizando ORM, é possível escrever comandos na linguagem de programação orientada a objetos desejada de acordo com sintaxe suportada pela biblioteca ORM, que irá traduzir os comandos em SQL antes de consumir os dados. A camada de abstração fornecida por ORM também lida com gerenciamento de transações, caching de consultas e mapeamento de tipos de dados entre a linguagem de programação e o banco de dados.

Alguns dos benefícios de se usar ORM para acessar bancos de dados incluem:

-   Abstração de complexidade: ORM simplifica o acesso aos bancos de dados relacionais, permitindo que através da classe, o consumo seja realizado
    
-   Maior produtividade: Ao fornecer uma camada de abstração, ORM reduz a quantidade de trabalho necessário para escrever código SQL manualmente, não sendo necessário informar dados para conexão com o banco de dados entre outras exigências da sintaxe SQL.

-   Portabilidade: A sintaxe ORM é geralmente independente de banco de dados utilizado, sendo possível migrar o banco de dados sem necessariamente alterar os trechos de código para consumo e manipulação.
    
-   Maior segurança: Ajudar a evitar vulnerabilidades de segurança como SQL injection, uma vez que as consultas são geradas pela biblioteca ORM e não pelo usuário.
    
Alguns dos frameworks ORM mais populares incluem Django ORM (para Python), Hibernate (para Java) e Entity Framework (para C#). Abaixo, segue um exemplo utilizando a técnica ORM através de uma linguagem fictícia.

## Exemplo utilização ORM

### Tabela: Pessoa
|ID   | NOME	| IDADE | 
| ---- | ---- | ---- | 
|1 | João | 23 |
|2 | Maurício | 40 |
|3 | Francisley | 22 |
|4 | Gustavo | 26 |
|5 | Pedro | 22 |
|6 | Vítor | 25 |


### Classe: Pessoa
```
class Pessoa
{
    int id;
    string nome;
    int idade;
}
```

### Consumo sem ORM:
```
string sql = "SELECT * FROM PESSOA";
SqlCommand command = new SqlCommand(sql, connection);

DataReader reader = command.Execute();
List<Pessoas> pessoas = new List<Pessoas>();

while(row = reader.Next())
{
    pessoas.Add(new Pessoa
    {
        id = Convert.ToInt(row["ID"]),
        nome = row["NOME"].ToString(),
        idade = Convert.ToInt(row["IDADE"]);
    };
}

```
### Com ORM:
```
List<Pessoas> pessoas = database.Pessoas.SelectAll().ToList();
```
