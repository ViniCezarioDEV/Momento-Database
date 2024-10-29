# Momento-Database

Quantos funcionarios da empresa Momento trabalham no departamento de vendas?
SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 8;
8

Inclua suas próprias informações no departamento de Tecnologia da empresa.
INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('Vinicius', 'Cezario', 'viniciusamcezario@outllok.com', 'circulo', '11911111111', 2024-10-29, 9, 10000, 103, 6);

Agora diga, quantos funcionários temos ao total na empresa?
SELECT COUNT(*) FROM momento.funcionarios;
42

E quanto ao Departamento de Tecnologia?
SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 6;
6

Quanto o departamento de Vendas gasta em salários?
SELECT SUM(salario) FROM momento.funcionarios;
379830.00

Um novo departamento foi criado. O departamento de Inovações. Ele será locado no Brasil. Por favor, adicione-o no banco de dados da empresa colocando quaisquer informações que você achar relevantes.
INSERT INTO momento.escritorios(escritorio_nome, endereco, cep, cidade, estado_provincia, pais_id) VALUES ('Jalin Habey', 'Rua Casa do caixa prego', '08537150', 'São Paulo', 'São Paulo', 'BR');
INSERT INTO momento.departamentos(departamento_nome, escritorio_id) VALUES('Inovação', 3901);


O departamento de Inovações está sem funcionários. Inclua alguns colegas de turma nesse departamento.
INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('Paola', 'Karossela', 'paolak198@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);
INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('enrick', 'fogaça', 'enriquecendo@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);
INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('erick', 'jakan', 'pesadeloonkithcen@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);

Quantos funcionarios a empresa Momento tem agora?
SELECT COUNT(*) FROM momento.funcionarios;
45

Quantos funcionários da empresa Momento possuem conjuges?
SELECT COUNT(*) FROM momento.dependentes WHERE relacionamento LIKE '%conjuge%';
4

Qual a média salarial dos funcionários da empresa Momento, excluindo-se o CEO?
SELECT AVG(salario) FROM momento.funcionarios WHERE NOT cargo_id = 4;
8427.954545

Qual a média salarial do departamento de tecnologia?
SELECT AVG(salario) FROM momento.funcionarios WHERE departamento_id = 6;
6466.666667












