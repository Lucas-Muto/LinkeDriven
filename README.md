# LinkeDriven - Projeto de SQL

## 📋 Descrição

Este projeto foi desenvolvido como parte do curso da Driven Education para praticar conhecimentos em SQL. O LinkeDriven simula uma plataforma de conexão entre empresas e candidatos, similar ao LinkedIn, permitindo explorar diversas consultas SQL em um banco de dados relacional.

## 🎯 Objetivo

O objetivo principal deste projeto é praticar consultas SQL de diferentes níveis de complexidade, desde simples seleções até junções complexas entre múltiplas tabelas, além de inserções, atualizações e exclusões de dados.

## 🗃️ Estrutura do Banco de Dados

O banco de dados contém as seguintes tabelas principais:

- `companies`: Empresas cadastradas na plataforma
- `jobs`: Vagas de emprego disponíveis
- `users`: Usuários/candidatos
- `roles`: Cargos/funções
- `experiences`: Experiências profissionais dos usuários
- `educations`: Formação educacional dos usuários
- `applicants`: Candidaturas a vagas
- `testimonials`: Depoimentos entre usuários
- `cities`: Cidades
- `schools`: Instituições educacionais
- `courses`: Cursos

## 💻 Como Executar

1. Importe o banco de dados no pgAdmin 4
2. Abra o arquivo `respostas.sql`
3. Execute cada consulta individualmente para verificar os resultados

## 📝 Consultas Implementadas

O projeto contém 20 consultas SQL que abordam diferentes cenários:

1. Listar empresas (limite de 5)
2. Buscar empresa específica por nome
3. Inserir nova empresa
4. Remover empresa
5. Atualizar nome de empresa
6. Atualizar salário de vaga
7. Inserir nova experiência profissional
8. Remover candidatura
9. Listar vagas com maiores salários
10. Encontrar vaga com menor salário
11. Listar usuários de uma cidade específica
12. Listar depoimentos com autor e destinatário
13. Mostrar formação educacional de um usuário
14. Listar experiências profissionais anteriores
15. Buscar candidatos com formação específica
16. Contar experiências atuais
17. Contar formações por usuário
18. Contar depoimentos escritos por um usuário
19. Encontrar salário máximo por cargo
20. Listar as instituições educacionais mais populares

## 🔍 Explicação Detalhada das Consultas SQL

### Aliases utilizados nas consultas:

- **u**: Alias para tabela `users` (usuários)
  - `u.id`: ID do usuário
  - `u.name`: Nome do usuário
  - `u.city_id`: ID da cidade do usuário

- **c**: Alias para tabela `companies` (empresas) ou `cities` (cidades) ou `courses` (cursos)
  - `c.id`: ID da empresa/cidade/curso
  - `c.name`: Nome da empresa/cidade/curso

- **j**: Alias para tabela `jobs` (vagas)
  - `j.id`: ID da vaga
  - `j.salary`: Salário da vaga
  - `j.description`: Descrição da vaga
  - `j.company_id`: ID da empresa
  - `j.role_id`: ID do cargo
  - `j.active`: Status da vaga (ativa/inativa)

- **r**: Alias para tabela `roles` (cargos)
  - `r.id`: ID do cargo
  - `r.name`: Nome do cargo

- **e**: Alias para tabela `experiences` (experiências) ou `educations` (educações)
  - `e.id`: ID da experiência/educação
  - `e.user_id`: ID do usuário
  - `e.company_id`: ID da empresa (para experiences)
  - `e.role_id`: ID do cargo (para experiences)
  - `e.start_date`: Data de início
  - `e.end_date`: Data de fim
  - `e.course_id`: ID do curso (para educations)
  - `e.school_id`: ID da escola (para educations)
  - `e.status`: Status da educação (finished, ongoing, etc.)

- **t**: Alias para tabela `testimonials` (depoimentos)
  - `t.id`: ID do depoimento
  - `t.message`: Mensagem do depoimento
  - `t.writer_id`: ID do autor do depoimento
  - `t.recipient_id`: ID do destinatário do depoimento

- **s**: Alias para tabela `schools` (escolas)
  - `s.id`: ID da escola
  - `s.name`: Nome da escola

- **a**: Alias para tabela `applicants` (candidatos)
  - `a.user_id`: ID do usuário candidato
  - `a.job_id`: ID da vaga

- **w**: Alias para `users` quando usado como "writer" (autor)
  - `w.name`: Nome do autor

- **co**: Alias para `companies` quando usado junto com `c` (courses)
  - `co.name`: Nome da empresa

### Funções e Comandos SQL utilizados:

- **SELECT**: Seleciona dados das tabelas
- **FROM**: Especifica a tabela principal
- **WHERE**: Filtra resultados com condições
- **JOIN**: Une tabelas relacionadas
- **GROUP BY**: Agrupa resultados por campo
- **ORDER BY**: Ordena resultados
- **LIMIT**: Limita número de resultados
- **COUNT()**: Conta número de registros
- **MAX()**: Retorna valor máximo
- **AS**: Cria alias para campos e tabelas
- **INSERT INTO**: Insere novos registros
- **UPDATE**: Atualiza registros existentes
- **DELETE**: Remove registros
- **IS NULL / IS NOT NULL**: Verifica valores nulos
- **CURRENT_DATE**: Data atual do sistema

### Exemplos de Uso:

```sql
-- Buscar usuários de uma cidade específica
SELECT u.id, u.name, c.name AS city
FROM users u
JOIN cities c ON u.city_id = c.id
WHERE c.name = 'Rio de Janeiro';
```

Neste exemplo:
- `u` é alias para `users`
- `c` é alias para `cities`
- `u.city_id = c.id` relaciona usuário com sua cidade
- `c.name AS city` renomeia o campo para "city" no resultado

## 🛠️ Tecnologias Utilizadas

- PostgreSQL
- pgAdmin 4

## 👨‍💻 Autor

Lucas Sabbag Muto

---

*Projeto criado para fins educacionais como parte do curso da Driven Education.* 
