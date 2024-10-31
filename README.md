# Momento-Database

## Departamento de Tecnologia
- Inclua suas próprias informações no departamento de Tecnologia da empresa.<br>
`INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('Vinicius', 'Cezario', 'viniciusamcezario@outllok.com', 'circulo', '11911111111', 2024-10-29, 9, 10000, 103, 6);`<br>

- Agora diga, quantos funcionários temos ao total na empresa?<br>
`SELECT COUNT(*) FROM momento.funcionarios;`<br>
42<br>

- E quanto ao Departamento de Tecnologia?<br>
`SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 6;`<br>
6<br>

## Departamento de Vendas
- Quantos funcionários trabalham no Departamento de Vendas? Use uma consulta para descobrir o número total de funcionários alocados nesse departamento.<br>
`SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 8;`<br>
8<br>

## Salários no Departamento de Vendas

- Qual é o custo total dos salários do pessoal de Vendas? Isso nos ajuda a entender o orçamento do departamento!<br>
`SELECT SUM(salario) FROM momento.funcionarios WHERE departamento_id = 8;`<br>
51500.00<br>

- Quanto o departamento de Vendas gasta em salários?<br>
`SELECT SUM(salario) FROM momento.funcionarios WHERE departamento_id = 8;`<br>
51500.00<br>

- Quais são os produtos mais vendidos e quais têm pouca ou nenhuma saída?<br>
`SELECT * FROM momento.produtos;`<br>
`SELECT * FROM momento.vendas ORDER BY quantidade;`<br>
Batarangs Oficiais, Laço da Honestidade, Uniforme do Superman<br>

- Qual é o produto mais caro no inventário da empresa?<br>
`SELECT * FROM momento.produtos ORDER BY produto_price DESC LIMIT 1;`<br>
Sabre de Luz (Mace Windu) 990.29<br>

## Departamento de Inovações
- Um novo departamento foi criado. O departamento de Inovações. Ele será locado no Brasil. Por favor, adicione-o no banco de dados da empresa colocando quaisquer informações que você achar relevantes.<br>
`INSERT INTO momento.escritorios(escritorio_nome, endereco, cep, cidade, estado_provincia, pais_id) VALUES ('Omar silvestre', 'Rua Casa do caixa prego', '08537150', 'São Paulo', 'São Paulo', 'BR');`<br>
`INSERT INTO momento.departamentos(departamento_nome, escritorio_id) VALUES('Inovação', 3901);`<br>

- O departamento de Inovações está sem funcionários. Inclua alguns colegas de turma nesse departamento.<br>
`INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('Paola', 'Karossela', 'paolak198@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);`<br>
`INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('enrick', 'fogaça', 'enriquecendo@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);`<br>
`INSERT INTO momento.funcionarios (primeiro_nome, sobrenome, email, senha, telefone, data_contratacao, cargo_id, salario, gerente_id, departamento_id) VALUES ('erick', 'jakan', 'pesadeloonkithcen@outllok.com', 'defaultPass', '11911111111', '2024-10-29', 18, 5000, null, 14);`<br>

## Funcionários
- Quantos funcionários da empresa Momento possuem conjuges?<br>
`SELECT COUNT(*) FROM momento.dependentes WHERE relacionamento LIKE '%conjuge%';`<br>
4<br>

- Qual o funcionário contratado há mais tempo na empresa?<br>

- Qual o funcionário contratado há menos tempo na empresa?<br>

- Quem são os funcionários com mais tempo na empresa, considerando a data_contratacao?<br>

- Como a média salarial dos funcionários da "Momento" evoluiu nos últimos anos? Dica: utilize a função AVG() para calcular a média salarial dos funcionários. e GROUP BY para agrupar os resultados por ano.<br>

## Médias salariais
- Qual a média salarial dos funcionários da empresa Momento, excluindo-se o CEO, CMO e CFO?<br>
`SELECT AVG(salario) FROM momento.funcionarios WHERE NOT cargo_id IN (4,7,10);`<br>
8442.894737<br>

- Qual a média salarial do departamento de tecnologia?<br>
`SELECT AVG(salario) FROM momento.funcionarios WHERE departamento_id = 6;`<br>
6466.666667<br>

- Qual o departamento com a maior média salarial?<br>
`SELECT AVG(salario) AS media_salario FROM momento.funcionarios WHERE departamento_id IN (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13) GROUP BY departamento_id ORDER BY media_salario DESC LIMIT 1;`<br>
21815.000000<br>

- Qual o departamento com o menor número de funcionários?<br>
`SELECT departamento_id, COUNT(*) AS numero_funcionarios FROM momento.funcionarios WHERE departamento_id IN (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13) GROUP BY departamento_id ORDER BY numero_funcionarios ASC LIMIT 1;`<br>
departamento_id = 1, com 1 funcionario<br>

## Produtos
- Pensando na relação quantidade e valor unitario, qual o produto mais valioso da empresa?<br>
`SELECT * FROM momento.vendas ORDER BY quantidade DESC;`<br>
`SELECT * FROM momento.produtos ORDER BY produto_price DESC;`<br>
Uniforme do Superman, R$300.13, quantidade: 167<br>

- Qual o produto mais vendido da empresa?<br>
`SELECT * FROM momento.vendas ORDER BY quantidade DESC;`<br>
Uniforme do Superman com 167 unidades vendidas<br>

- Qual o produto menos vendido da empresa?<br>
`SELECT * FROM momento.vendas ORDER BY quantidade ASC;`<br>
Batarangs Oficiais, com 3 unidades vendidas<br>

Escritórios
- Quantos escritórios a "Momento" possui em cada região? (Dica: relacione as tabelas regioes e escritorios).<br>
`SELECT * FROM momento.escritorios;`<br>
3 nos estados unidos<br>
1 no canada<br>
2 no reino unido<br>
1 em wakanda<br>
1 na alemanha<br>

- Qual é o custo total de suprimentos em cada escritório? Que tal ordenar os resultados para ver qual escritório possui os suprimentos mais caros?<br>
`SELECT * FROM momento.suprimentos;`<br>
1400 - 148000.00<br>
1700 - 5050.07<br>
1800 - 2000.00<br>
1900 - 4000.00<br>
2400 - 5505.70<br>
2500 - 405000.00<br>
3900 - 403752.85<br>















