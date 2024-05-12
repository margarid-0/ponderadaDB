# PonderadaDB

Um banco de dados é uma coleção de dados relacionados e armazenados. Em bancos de dados relacionais, cada linha de uma tabela representa um registro, que é identificado por um número único. A ferramenta "SQL Toad" foi utilizada para desenvolver o banco de dados dessa atividade ponderada e para as entregas do projeto do módulo. Segue a imagem da modelagem do banco de dados:

<div align="center">
<sub>Modelo do Bancdo de Dados Relacional</sub>
<img src="/assets/db_ponderada.jpeg" width="100%" >
</div>
<br>

O arquivo gerado em XML é utilizado para estruturar e armazenar dados em um formato legível por máquina, como demonstrado:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: https://sql.toad.cz/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>

	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>

	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="740" y="485" name="User">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="type" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="email" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="password" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="birthday" null="1" autoincrement="0">
<datatype>DATE</datatype>
<default>NULL</default></row>
<row name="country_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Country" row="id" />
</row>
<row name="gender" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="age" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="university_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="University" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="426" y="754" name="Student">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="user_id" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<row name="country_review" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="350" y="568" name="QuestionAnswer">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="student_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<row name="answer" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="question_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Question" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="305" y="432" name="Question">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="question_type" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="alternatives" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1067" y="724" name="Tutor">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="user_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="461" y="330" name="Country">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="time_zone" null="1" autoincrement="0">
<datatype>TIMESTAMP</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1078" y="459" name="Group">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="number" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="game_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Game" row="id" />
</row>
<row name="tutor_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<row name="new field" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="742" y="795" name="Game">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="round" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="start_date" null="1" autoincrement="0">
<datatype>DATE</datatype>
<default>NULL</default></row>
<row name="end_date" null="1" autoincrement="0">
<datatype>DATE</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1005" y="354" name="University">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>
```


1. Entidade “User”
   * “id” (Chave primária da tabela): Identificador único do usuário;
   * “type”: Tipo do usuário;
   * “name”: Nome do usuário;
   * “email”: Email do usuário;
   * “password”: Senha do usuário;
   * “birthday”: Data de nascimento do usuário;
   * “country_id” (chave estrangeira da tabela “Country”): Referência ao país do usuário;
   * “gender”: Gênero do usuário;
   * “age”: Idade do usuário;
   * “university_id” (chave estrangeira da tabela “University”): Referência à universidade do usuário.

2. Entidade “Country”
   * “id” (Chave primária da tabela): Identificador único do país;
   * “name”: Nome do país;
   * “time_zone”: Fuso horário do país.

3. Entidade “University”
   * “id” (Chave primária da tabela): Identificador único da universidade;
   * “name”: Nome da universidade.

4. Entidade “Group”
   * “id” (Chave primária da tabela): Identificador único do grupo;
   * “number”: Número do grupo;
   * “name”: Nome do grupo;
   * “game_id” (chave estrangeira da tabela “Game”): Referência ao jogo associado;
   * “tutor_id” (chave estrangeira da tabela “Tutor”): Referência ao tutor do grupo.

5. Entidade “Tutor”
   * “id” (Chave primária da tabela): Identificador único do tutor;
   * “user_id” (chave estrangeira da tabela “User”): Referência ao usuário correspondente.

6. Entidade “Game”
   * “id” (Chave primária da tabela): Identificador único do jogo;
   * “round”: Rodada do jogo;
   * “start_date”: Data de início do jogo;
   * “end_date”: Data de término do jogo.

7. Entidade “Student”
   * “id” (Chave primária da tabela): Identificador único do estudante;
   * “user_id” (chave estrangeira da tabela “User”): Referência ao usuário correspondente;
   * “country_review”: Avaliação do país.

8. Entidade “Question”
   * “id” (Chave primária da tabela): Identificador único da pergunta;
   * “question_type”: Tipo de pergunta;
   * “alternatives”: Alternativas da pergunta.

9. Entidade “QuestionAnswer”
   * “id” (Chave primária da tabela): Identificador único da resposta;
   * “student_id” (chave estrangeira da tabela “Student”): Referência ao estudante que respondeu;
   * “answer”: Resposta dada;
   * “question_id” (chave estrangeira da tabela “Question”): Referência à pergunta respondida.

Para fazer as tabelas e estabelecer suas relações no banco de dados foi utilizado postgreSQL:

```sql
-- ---
-- Globals
-- ---

-- SET SQL_MODE="NO_AUTO_VALUE_ON_ZERO";

-- ---
-- Table 'User'
-- ---

DROP TABLE IF EXISTS "User" CASCADE;
		
CREATE TABLE "User" (
  "id" SERIAL PRIMARY KEY,
  "type" TEXT,
  "name" TEXT,
  "email" TEXT,
  "password" TEXT,
  "birthday" DATE,
  "country_id" INTEGER,
  "gender" INTEGER,
  "age" INTEGER,
  "university_id" INTEGER,
  FOREIGN KEY ("country_id") REFERENCES "Country" ("id"),
  FOREIGN KEY ("university_id") REFERENCES "University" ("id")
);

-- ---
-- Table 'Student'
-- ---

DROP TABLE IF EXISTS "Student" CASCADE;
		
CREATE TABLE "Student" (
  "id" SERIAL PRIMARY KEY,
  "user_id" INTEGER,
  "country_review" TEXT,
  FOREIGN KEY ("user_id") REFERENCES "User" ("id")
);

-- ---
-- Table 'QuestionAnswer'
-- ---

DROP TABLE IF EXISTS "QuestionAnswer" CASCADE;
		
CREATE TABLE "QuestionAnswer" (
  "id" SERIAL PRIMARY KEY,
  "student_id" INTEGER,
  "answer" TEXT,
  "question_id" INTEGER,
  FOREIGN KEY ("student_id") REFERENCES "Student" ("id"),
  FOREIGN KEY ("question_id") REFERENCES "Question" ("id")
);

-- ---
-- Table 'Question'
-- ---

DROP TABLE IF EXISTS "Question" CASCADE;
		
CREATE TABLE "Question" (
  "id" SERIAL PRIMARY KEY,
  "question_type" TEXT,
  "alternatives" TEXT
);

-- ---
-- Table 'Tutor'
-- ---

DROP TABLE IF EXISTS "Tutor" CASCADE;
		
CREATE TABLE "Tutor" (
  "id" SERIAL PRIMARY KEY,
  "user_id" INTEGER,
  FOREIGN KEY ("user_id") REFERENCES "User" ("id")
);

-- ---
-- Table 'Country'
-- ---

DROP TABLE IF EXISTS "Country" CASCADE;
		
CREATE TABLE "Country" (
  "id" SERIAL PRIMARY KEY,
  "name" TEXT,
  "time_zone" TIMESTAMP
);

-- ---
-- Table 'Group'
-- ---

DROP TABLE IF EXISTS "Group" CASCADE;
		
CREATE TABLE "Group" (
  "id" SERIAL PRIMARY KEY,
  "number" INTEGER,
  "name" TEXT,
  "game_id" INTEGER,
  "tutor_id" INTEGER,
  "new_field" INTEGER,
  FOREIGN KEY ("game_id") REFERENCES "Game" ("id"),
  FOREIGN KEY ("tutor_id") REFERENCES "Tutor" ("id")
);

-- ---
-- Table 'Game'
-- ---

DROP TABLE IF EXISTS "Game" CASCADE;
		
CREATE TABLE "Game" (
  "id" SERIAL PRIMARY KEY,
  "round" INTEGER,
  "start_date" DATE,
  "end_date" DATE
);

-- ---
-- Table 'University'
-- ---

DROP TABLE IF EXISTS "University" CASCADE;
		
CREATE TABLE "University" (
  "id" SERIAL PRIMARY KEY,
  "name" TEXT
);

-- ---
-- Table Properties
-- ---

-- ---
-- Test Data
-- ---
```