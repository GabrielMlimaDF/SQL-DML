# Comandos SQL – DML 📘

SQL é uma linguagem **declarativa** e **case sensitive**.

## 📚 Sublinguagens SQL

### 1. DML — DATA MANIPULATION LANGUAGE

**Principais comandos:**

1. `SELECT` – Busca informações 
2. `INSERT` – Adicionar registros 
3. `UPDATE` – Altera informações em registros  
4. `DELETE` – Exclui registros

---

## 🧱 Exemplos de Comandos DML

```sql
-- Consulta dados
SELECT * FROM Clientes;

-- Consultar apenas o nome e o email dos clientes:
SELECT nome, email FROM Clientes;

-- Consultar clientes que são de São Paulo:
SELECT * FROM Clientes
WHERE cidade = 'São Paulo';

-- SELECT DISTINCT serve para eliminar registros duplicados no resultado de uma consulta
SELECT DISTINCT cidade FROM Clientes;

-- ALIAS (apelido) é usado principalmente com SELECT para facilitar a leitura dos resultados.
SELECT nome AS NomeCliente, cidade AS CidadeCliente
FROM Clientes AS c
WHERE c.cidade = 'São Paulo';

-- Podemos usar IN e NOT IN junto com WHERE
SELECT *
FROM Clientes
WHERE Cidade IN ('salvador','goania');

--Podemos realizer subconsultas utilizando IN de forma não correlacionada e correlacionada
SELECT *
FROM Clientes
WHERE Cidade IN (SELECT Capital FROM Capitais);

--Correlacionadas Contexto do EXIST
SELECT *
FROM Capitais c
WHERE EXISTS (SELECT Cidade FROM Clientes AS cl WHERE cl.cidade = c.capitais);


-- Inserir um novo cliente
INSERT INTO Clientes (nome, email, cidade)
VALUES ('Marcos Souza', 'marcos@email.com', 'Belo Horizonte');

-- Atualizar o email do cliente Ana Silva
UPDATE Clientes
SET email = 'ana.silva@novomail.com'
WHERE id = 1;

-- Deletar o cliente com id 2 (João Lima)
DELETE FROM Clientes
WHERE id = 2;


## 📚 importante sempre usar WHERE com

UPDATE	Para atualizar apenas registros específicos (e não todos!).
DELETE	Para apagar apenas registros específicos (evitando apagar tudo!).

```
