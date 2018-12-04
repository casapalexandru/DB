# Laboratorul Nr.9
# Crearea procedurilor stocate si a functiilor definite de utilizator

#TASK_01

Sa se creeze proceduri stocate in baza exercitiilor (2 exercitii) din capitolul 4. Parametrii de intrare trebuie sa corespunda criteriilor din clauzele WHERE ale exercitiilor respective.

```SQL
drop procedure if exists proc_ex19;
go

create procedure proc_ex19
@nume_student varchar (20) = 'Cosovanu',
@reusita smallint = 5

as
select distinct Nume_Profesor,Prenume_Profesor
from reusita_St sr
inner join prof_St p on sr.Id_Profesor = p.Id_Profesor
inner join stud_St s on sr.Id_Student = s.Id_Student
where s.Nume_Student = @nume_student 
  and sr.Nota < @reusita

exec proc_ex19
```

![interogarea 1_1](Image1_1.PNG)

```SQL
drop procedure if exists proc_ex35
go

create procedure proc_ex35
@media_min smallint = 7

as
select d.Disciplina,AVG(cast(sr.Nota as float)) as Media
from reusita_St sr
inner join disc_St d on sr.Id_Disciplina = d.Id_Disciplina
group by d.Disciplina
having AVG(cast(sr.Nota as float)) > @media_min
order by Media

exec proc_ex35
```

![interogarea 1_2](Image1_2.PNG)