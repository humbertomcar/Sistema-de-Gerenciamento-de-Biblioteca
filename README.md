# Sistema-de-Gerenciamento-de-Biblioteca
Aluno: Humberto Moraes Carneiro

Diagrama MER produzido representa um simples sistema de gerenciamento de biblioteca conforme aprendizado da cadeira Banco de Dados 1

Alguns simbolos utilizados no relatório:
*Atributo primário*
**Atributo derivado**
<Relacionamento> / Relacionamento<>
Relacionamento de identificação<<>>
Entidade fraca[[]]
Entidade associativa[<>]

Requisitos Mínimos:

1. Identificar entidades principais envolvidas no sistema (9 entidades):
Autor; Livro; Cliente; Funcionário; Assistente; Gerente; Sala de Estudo; Assinante; Estudante; Empréstimo.

2. Definir os atributos essenciais para cada entidade:
Autor- *Email_Profissional*; Nome (Primeiro_Nome, Sobrenome);
Livro- *Código_de_Barras*; Edição; Número_setor; Título; Editora;
Empréstimo[<>]- Data_do_Empréstimo; *Código_do_Empréstimo*; **Data_de_Vencimento**;
Cliente- *Registro_Geral*; Nome (Primeiro_Nome, Sobrenome); Gênero; *Endereço* (Bairro, Rua, Número, Cidade, **Apartamento**); *Email*;
Aplica Multa<>- Valor; Data_da_Multa;
Funcionário- Nome (Primeiro_Nome, Sobrenome); *Registro_Funcionário*;
Sala de Estudo- *Número_da_Sala*; Cadeira; Quadro; Mesa;
Assinante- *Comprovante_da_Assinatura*;
Estudante- *Carteira_Est*.

3. Estabelecer relacionamentos entre as entidades:
4. Utilizar cardinalidades para especificar a quantidade de entidades em cada lado do relacionamento:
Escreve<>- (1,n) Autor <Escreve> (1,n) Livro;
Realiza Empréstimo[<>]- (1,n) Cliente <Realiza Empréstimo> (1,n) Livro;
Aplica Multa<>- (0,1) Gerente <Aplica Multa> (0,n) Cliente;
Gerencia<>- (1,1) Gerente <Gerencia> (1,n) Empréstimo;
Atende<>- (0,1) Assistente <Atende> (0,1) Cliente; (OBS.: levei em consideração que o atendimento seria facultativo em relação ao cliente)
Supervisiona<>- (1,1) Gerente <Supervisiona> (1,n) Assistente;
Abre<>- (1,1) Gerente <Abre> (1,n) Sala de Estudo;
Acessa<>- (1,n) Estudante e Assinante <Acessa> (1,1) Sala de Estudo.

5. Modelar a especialização-generalização:
Cliente- Estudante ou Assinante (Especialização); (OBS.: a ligação da entidade cliente não está ligada a especialização pois não consegui ligá-lo no brModelo)
Funcionário- Assistente e/ou Gerente (Generalização).

Requisitos Adicionais:

Dependência- Utilizei entidades fracas e relacionamento de identificação para demonstrar a dependência. Foram aplicadas 2 entidades fracas e 2 relacionamentos de idenfitificação, sendo eles Sala de Estudo[[]] e Abre<<>>, onde mostraria que a Sala de Estudo é dependente do Gerente abrir a sala; e também, Livro[[]] e Escreve<<>>, onde mostraria que o livro dependesse de ser escrito pelo(s) autor(es);
Entidade Associativa- Utilizei uma entidade associativa para o empréstimo, pois o empréstimo pode ser vista tanto da forma de entidade, quanto uma relação;
