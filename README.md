
# README - Correções de Código

Este é um guia para identificar e corrigir os erros no código da classe User fornecida.

## Erros Encontrados:

1. **Erro de Carregamento do Driver JDBC:**
   - Na linha 19, o método `Class.forName()` está carregando o driver JDBC de forma incorreta.
   - Correção: Altere `"com.mysql.Driver.Manager"` para `"com.mysql.jdbc.Driver"`.

2. **Erro de Conexão com o Banco de Dados:**
   - Na linha 23, a URL de conexão com o banco de dados está sendo especificada incorretamente.
   - Correção: A URL deve ser `"jdbc:mysql://127.0.0.1/test?user=lopes&password=123"`.

3. **Erro de Manipulação de Exceções:**
   - O código lida com exceções de forma inadequada, ignorando os detalhes do erro.
   - Correção: Implemente uma melhor gestão de exceções, por exemplo, registrando os detalhes do erro ou lançando exceções personalizadas.

4. **Vulnerabilidade de Injeção SQL:**
   - Na linha 38, a concatenação de strings para construir a consulta SQL é uma prática insegura e pode levar a vulnerabilidades de injeção de SQL.
   - Correção: Use PreparedStatement para evitar injeções de SQL. 

5. **Variáveis Públicas:**
   - As variáveis `nome` e `result` são públicas, o que pode levar a problemas de encapsulamento.
   - Correção: Torne essas variáveis privadas e forneça métodos para acessá-las, se necessário.

6. **Não Fechamento de Recursos:**
   - Não há fechamento dos recursos (Statement, ResultSet, Connection) após o uso, o que pode levar a vazamentos de recursos.
   - Correção: Use blocos try-with-resources ou feche explicitamente os recursos no bloco finally.
