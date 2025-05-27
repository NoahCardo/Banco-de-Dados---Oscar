# 🏆🎥 Nomeados ao Oscar 🏆🎥

Contém a base de indicados ao Oscar em formato SQL para treinar comandos CRUD. 

Abaixo, algumas atividades para trabalharmos.

--- 

## * Atualize os registros da tabela com os dados do Oscar 2025

---

## * Qual o **total** de registros na tabela indicados?

R: 10889 registros!

Q:
```sql
SELECT COUNT(*) AS total_registros FROM indicados_ao_oscar;
```

---

## * Qual o número de indicações por categoria agrupadas por categoria?

R: 2!

Q:
```sql
SELECT categoria, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY total_indicacoes DESC;
```

---

## * Quantas vezes Natalie Portman foi indicada ao Oscar?

R: 3 vezes!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado Like '%Natalie Portman%';
```

---

## * Quantos Oscars Natalie Portman ganhou?

R: 1 Oscar!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Natalie Portman%' AND vencedor = 'true';
```

---

## * Quantas vezes Viola Davis foi indicada ao Oscar?

R: 4 vezes!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado Like '%Viola Davis%';
```

---

## * Quantos Oscars Viola Davis ganhou?

R: 1 Oscar!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Viola Davis%' AND vencedor = 'true';
```

---

## * Amy Adams já ganhou algum Oscar?

R: Não; nenhum Oscar!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Amy Adams%' AND vencedor = 'true';
```

---

## * Quais os atores/atrizes que foram indicados mais de uma vez?

Obs: Utilizar a função COUNT e GROUP BY, e a função HAVING para filtrar os registros que possuem mais de uma indicação. 

R: Alguns deles seriam: Adrienne Fazan (com 2 indicações), Agnes Moorehead (com 4 indicações), Akim Tamiroff (com 2 indicações), Al Pacino (com 9 indicações), Alan Arkin (com 4 indicações)... E muitos outros mais!

Q:
```sql
SELECT nome_do_indicado, COUNT(*) AS num_indicacoes
FROM indicados_ao_oscar
GROUP BY nome_do_indicado
HAVING COUNT(*) > 1
ORDER BY num_indicacoes DESC;
```

---

## * A série de filmes Toy Story ganhou Oscars em quais anos?

R: 2010 e 2019!

Q:
```sql
SELECT ano_filmagem
FROM indicados_ao_oscar
WHERE nome_do_filme LIKE '%Toy Story%' AND vencedor = 'true'
GROUP BY ano_filmagem
ORDER BY ano_filmagem;
```

---

## * A partir de que ano que a categoria "Actress" deixa de existir? 

R: 1975!

Q:
```sql
SELECT DISTINCT ano_filmagem 
FROM indicados_ao_oscar 
WHERE categoria = 'Actress'
ORDER BY ano_filmagem DESC 
LIMIT 1;
```

---

## * Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R: Janet Gaynor, em 1928!

Q:
```sql
SELECT nome_do_indicado, ano_cerimonia
FROM indicados_ao_oscar
WHERE categoria LIKE '%Actress%' AND vencedor = 'true'
ORDER BY ano_cerimonia ASC
LIMIT 1;
```

---

## * Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R: Feito!

Q:
```sql
UPDATE indicados_ao_oscar SET vencedor = '1' WHERE vencedor = 'true';

UPDATE indicados_ao_oscar SET vencedor = '0' WHERE vencedor = 'false';
```

---

## * Em qual edição do Oscar "Crash" concorreu ao Oscar?

R: 2006!

Q:
```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme = 'Crash';
```

---

## * O filme Central do Brasil aparece no Oscar?

R: Não!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_filme = 'Central do Brasil';
```

---

## * Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

R: Três filmes foram incluídos ao banco, sendo estes...:

- 🌳 "Princesa Mononoke" (1997) – Dirigido por Hayao Miyazaki e Produzido pelo Studio Ghibli;

<div align="center">
  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ2d1MGpseTZlcWVoYWMzdWNtcGpzY3lsZnliZDBibW5uMW56ZHJkdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/8aA3w9pt0duIE/giphy.gif" height="250">
</div>

- 👻 "Colorful" (2010) – Dirigido por Keiichi Hara e Produzido pelo Estúdio Sunrise;

<div align="center">
  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ2d1MGpseTZlcWVoYWMzdWNtcGpzY3lsZnliZDBibW5uMW56ZHJkdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/8aA3w9pt0duIE/giphy.gif" height="250">
</div>

- 🫴🏽 "Fale Comigo" (2022) – Dirigido por Danny e Michael Philippou.

<div align="center">
  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ2d1MGpseTZlcWVoYWMzdWNtcGpzY3lsZnliZDBibW5uMW56ZHJkdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/8aA3w9pt0duIE/giphy.gif" height="250">
</div>

Q:
```sql
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor) VALUES
(1997, 1998, 70, 'BEST ANIMATED MOVIE', NULL, 'Princesa Mononoke', 'false'),
(2010, 2011, 83, 'BEST ANIMATED MOVIE', NULL, 'Colorful', 'false'),
(2022, 2023, 95, 'WRITING (Original Story)', NULL, 'Fale Comigo', 'false');
```

---

## * Denzel Washington já ganhou algum Oscar?

R: Sim; 2 Oscars!

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Denzel Washington%' AND vencedor = 'true';
```

---

## * Quais os filmes que ganharam o Oscar de Melhor Filme?

R:  Alguns deles seriam: Lawrence of Arabia (1962), Tom Jones (1963), My Fair Lady (1964), The Sound of Music (1965), A Man for All Seasons (1966)... E muitos outros mais!

Q:
```sql
SELECT nome_do_filme, ano_filmagem FROM indicados_ao_oscar WHERE categoria = 'BEST PICTURE' AND vencedor = 'true';
```

---

## * Sidney Poitier foi o primeiro ator negro a ser indicado ao Oscar. Em que ano ele foi indicado? Por qual filme?

R: Em 1959 e 1964! Sydney Poitier foi indicado ao Oscar pelos filmes "The Defiant Ones" (1958), em 1959, e "Lilies of the Field" (1963), em 1964!

Q:
```sql
SELECT nome_do_indicado, nome_do_filme, ano_cerimonia, ano_filmagem
FROM indicados_ao_oscar
WHERE nome_do_indicado = 'Sidney Poitier'
ORDER BY ano_filmagem ASC
LIMIT 1;
```

---

## * Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?

R: Alguns deles seriam: Lawrence of Arabia (1962), Tom Jones (1963), My Fair Lady (1964), The Sound of Music (1965), A Man for All Seasons (1966)... E muitos outros mais!
Ao todo, 48 filmes!

Q:
```sql
SELECT DISTINCT
    mf.nome_do_filme,
    mf.ano_filmagem,
    mf.cerimonia
FROM
    indicados_ao_oscar mf
JOIN
    indicados_ao_oscar md ON mf.nome_do_filme = md.nome_do_filme
                         AND mf.ano_cerimonia = md.ano_cerimonia
                         AND mf.cerimonia = md.cerimonia
WHERE
    mf.categoria = 'BEST PICTURE' AND mf.vencedor = 'true'
    AND md.categoria = 'DIRECTING' AND md.vencedor = 'true';
```

---

## * Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?

R: Não!

Q:
```sql
SELECT DISTINCT
    dw.ano_cerimonia
FROM
    indicados_ao_oscar dw
JOIN
    indicados_ao_oscar jf ON dw.ano_cerimonia = jf.ano_cerimonia
WHERE
    dw.nome_do_indicado LIKE '%Denzel Washington%'
    AND jf.nome_do_indicado LIKE '%Jamie Foxx%';
```

---

## 🐬 Arquivo .sql Citado: [Banco de Dados em MySQL - Indicados ao Oscar](./indicados_ao_oscar.sql)

---
