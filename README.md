# 🏆🎥 Nomeados ao Oscar 🏆🎥

Contém a base de indicados ao Oscar em formato SQL para treinar comandos CRUD. 

Abaixo, algumas atividades para trabalharmos.

--- 

* Atualize os registros da tabela com os dados do Oscar 2025

---

* Qual o **total** de registros na tabela indicados?

R:

Q:
```sql

```

---

* Qual o número de indicações por categoria agrupadas por categoria?

R: 2

Q:
```sql
SELECT categoria, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY total_indicacoes DESC;
```

---

* Quantas vezes Natalie Portman foi indicada ao Oscar?

R: 3 vezes

Q:
```sql
SELECT COUNT(*) FROM indicados WHERE "Name" Like "%Natalie Portman%";
```

---

* Quantos Oscars Natalie Portman ganhou?

R:

Q:
```sql

```

---

* Quantas vezes Viola Davis foi indicada ao Oscar?

R:

Q:
```sql

```

---

* Quantos Oscars Viola Davis ganhou?

R:

Q:
```sql

```

---

* Amy Adams já ganhou algum Oscar?

R:

Q:
```sql

```

---

* Quais os atores/atrizes que foram indicados mais de uma vez?

Obs: Utilizar a função COUNT e GROUP BY, e a função HAVING para filtrar os registros que possuem mais de uma indicação. 

R:

Q:
```sql

```

---

* A série de filmes Toy Story ganhou Oscars em quais anos?

R:

Q:
```sql

```

---

* A partir de que ano que a categoria "Actress" deixa de existir? 

R:

Q:
```sql

```

---

* Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R:

Q:
```sql

```

---

* Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R:

Q:
```sql

```

---

* Em qual edição do Oscar "Crash" concorreu ao Oscar?

R:

Q:
```sql

```

---

* O filme Central do Brasil aparece no Oscar?

R:

Q:
```sql

```

---

* Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

R:

Q:
```sql

```

---

* Denzel Washington já ganhou algum Oscar?

R:

Q:
```sql

```

---

* Quais os filmes que ganharam o Oscar de Melhor Filme?

R:

Q:
```sql

```

---

* Sidney Poitier foi o primeiro ator negro a ser indicado ao Oscar. Em que ano ele foi indicado? Por qual filme?

R:

Q:
```sql

```

---

* Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?

R:

Q:
```sql

```

---

* Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?

R:

Q:
```sql

```
