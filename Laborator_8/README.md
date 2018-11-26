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