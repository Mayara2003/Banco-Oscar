# Banco Oscar
Criando tabelas, fazendo inserts e alterando tabelas no MySQL
#
**Quantas vezes Natalie Portman foi indicada ao Oscar?**

resposta: Natalie Portman foi indicada ao Oscar três vezes.

>(SELECT * FROM `oscar` WHERE name LIKE "Natalie Portman")

##

**Quantos Oscars Natalie Portman ganhou?**

resposta: Natalie Portman ganhou o Oscar uma vez.

>(SELECT * FROM `oscar` WHERE name LIKE "Natalie Portman")

##

**Amy Adams já ganhou algum Oscar?**

resposta: Não.

>(SELECT * FROM `oscar` WHERE name LIKE "Amy Adams" and winner LIKE "true";)

##

**Alguém já ganhou um Oscar e tem o seu primeiro nome?**

resposta: Não.

>(SELECT * FROM `oscar` WHERE name LIKE "%Luana%";)

##

**Toy Story 3 ganhou um Oscar em quais anos?**

resposta: Foram dois Oscars em 2011.

>(SELECT * FROM `oscar` WHERE film LIKE "Toy Story 3";)

##

**Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme”?**

resposta: Melhor filme com 318, melhor ator tem apenas 232.

>SELECT COUNT(*) FROM `oscar` WHERE category LIKE "Actor";
>SELECT COUNT(*) FROM `oscar` WHERE category LIKE "CINEMATOGRAPHY";

##

**O primeiro Oscar para melhor Atriz foi para quem? Em que ano?**

resposta: Janet Gaynor, em 1928.

>SELECT * FROM `oscar` WHERE category LIKE "actress";

##

**Na categoria Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.**

>UPDATE `oscar` SET winner= ‘1’ WHERE winner='true';
>UPDATE `oscar` SET winner= ‘0’ WHERE winner='false';

##

**Em qual edição do Oscar "Crash" ganhou o prêmio?**

resposta: Foram três Oscars em 2006.

>SELECT * FROM `oscar` WHERE film LIKE 'crash';

##

**Que filme merecia ganhar um Oscar e não ganhou?**

resposta: Filme Cidade de Deus.

##

**Bom... dê um Oscar para esse filme, então.**

>UPDATE `oscar` SET winner=1 WHERE film LIKE "%city of god%" and category LIKE "CINEMATOGRAPHY";

##

**O filme Central do Brasil aparece no Oscar?**

resposta: Aparece.

>SELECT * FROM `oscar` WHERE film LIKE "%central station%";

##

**Inclua no banco 7 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.**

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner)
>VALUES('','2013', '2014', '86', 'SEGUNDO AMIGOS', 'Denis Villeneuve','O homem duplicado', null);


>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2007', '2008','80', 'SEGUNDO AMIGOS', 'David Fincher','Zodíaco', null);


>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner)
>VALUES('','2021', '2022','94', 'SEGUNDO AMIGOS', 'Julia Ducournau','Titane', null);


>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2018', '2019','91', 'SEGUNDO AMIGOS', 'Lee Chang-dong','Burning', null);


>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','1980', '1981','53', 'SEGUNDO AMIGOS', 'Stanley Kubrick','o iluminado', null);


>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','1960', '1961','33', 'SEGUNDO AMIGOS', 'Alfred Hitchcock','Psicose', null);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2012', '2013','85', 'SEGUNDO AMIGOS', 'Stephen Chbosky','As vantagens de ser invisível', null);

##

**Crie uma categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.**

>UPDATE `oscar` SET winner=1 WHERE category LIKE "SEGUNDO AMIGOS";

##

**Qual foi o primeiro ano a ter um prêmio do Oscar?**

resposta: Em 1928.

>SELECT * FROM `oscar` WHERE id LIKE "1";

##

**Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?**

resposta: Filme - Road to Perdition, Atriz - Nicole Kidman, Diretor - Roman Polanski.

>SELECT * FROM `oscar` WHERE year_ceremony LIKE "2003" AND category LIKE "%ACTRESS%";

>SELECT * FROM `oscar` WHERE year_ceremony LIKE "2003" AND category LIKE "CINEMATOGRAPHY";

>SELECT * FROM `oscar` WHERE year_ceremony LIKE "2003" AND category LIKE "%DIRECTING%";

##

**Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.**

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','1984', '1985','57', 'ACTRESS', 'Sayuri Yoshinaga','Station to Heaven', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2003', '2004','76', 'ACTRESS', 'Fan bingbing ','Cell Phone', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2016', '2017','89', 'ACTRESS', 'Son Ye-jin','The Truth Beneath', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2015', '2016','88', 'ACTRESS', 'Rie Miyazawa','Pale Moon', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2015', '2016','88', 'ACTRESS', 'Gong Li','Memórias de uma Gueixa', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2002', '2003','75', 'ACTRESS', 'Rie Miyazawa','The Twilight Samurai', 0);

>INSERT INTO `oscar`(id,year_film, year_ceremony, ceremony, category, name, film, winner) 
>VALUES('','2011', '2012','84', 'ACTRESS', 'Eugene Domingo','Ang Babae Sa Septic Tank', 0);

##

**Utilizando o comando 'Alter Table', troque os tipos dos dados da coluna/campo "Winner" para Bit.**

>ALTER TABLE `oscar` MODIFY COLUMN winner bit;












