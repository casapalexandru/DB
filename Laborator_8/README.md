# Laboratorul Nr.8
# Administrarea viziunilor si a expresiilor-tabel

#TASK_01

Sa se creeze doua viziuni in baza interogarilor formulate in doua exercitii indicate din capitolul Prima viziune sa fie construita in Editorul de interogari, iar a doua, utilizand View Designer.

* Editorul de interogari

![interogarea 1_1](Image1_1.PNG)

* View Designer

![interogarea 1_2](Image1_2.PNG)

#TASK_02

Sa se scrie cate un exemplu de instructiuni INSERT, UPDATE, DELETE asupra viziunilor create. Sa se adauge comentariile respective referitoare la rezultatele executarii acestor instructiuni.

```SQL
create view task11 as
select Id_Student,Nume_Student, Prenume_Student
from stud_St

--Inserarea unui student nou in viziunea task01:
INSERT INTO task11
values (555,'NEW', 'STUDENT')

-- Modificarea unui student in viziune
UPDATE dbo.task11
SET Nume_Student = 'Vorotet'
WHERE Id_Student = 555
SELECT * FROM dbo.task11

-- Stergerea unui student din viziune
DELETE FROM task11 WHERE Nume_Student = 'Vorotet'

select * from task11
```

![interogarea 2_1](Image2_1.PNG) ![interogarea 2_2](Image2_2.PNG) ![interogarea 2_3](Image2_3.PNG)

Functiile Insert, Update si Delete in viziune sunt posibile, numai daca noul tuplu satisface conditiile viziunii.

#TASK_03

Sa se scrie instructiunile SQL care ar modifica viziunile create (in exercitiul 1) in asa fel, incat sa nu fie posibila modificarea sau stergerea tabelelor pe care acestea sunt definite si viziunile sa nu accepte operatiuni DML, daca conditiile clauzei WHERE nu sunt satisfacute.

*
```SQL
ALTER VIEW task01 WITH SCHEMABINDING AS
select distinct studenti.Nume_Student, studenti.Prenume_Student
from studenti.studenti_reusita
inner join studenti.studenti on studenti.studenti_reusita.Id_Student = studenti.studenti.Id_Student
where studenti.studenti_reusita.Tip_Evaluare = 'Reusita curenta'
WITH CHECK OPTION;
```

*
```SQL
alter view task02 with schemabinding as
select plan_studii.discipline.Disciplina, AVG(cast(studenti.studenti_reusita.Nota as float)) as Media
from studenti.studenti_reusita
inner join plan_studii.discipline on studenti.studenti_reusita.Id_Disciplina = plan_studii.discipline.Id_Disciplina
group by plan_studii.discipline.Disciplina
having AVG(cast(studenti.studenti_reusita.Nota as float)) > 7
WITH CHECK OPTION;
```

#TASK_04

Sa se scrie instructiunile de testare a proprietatilor noi definite.

```SQL
--*1
ALTER TABLE studenti.studenti DROP COLUMN Nume_Student

--*2
INSERT INTO task01
values ('Arja','Abdula')

--*3
ALTER TABLE plan_studii.discipline DROP COLUMN Disciplina

---*4

INSERT INTO task02
values('Practica', 7)
```