# Laboratorul Nr.4

1. Interogarea Nr. 19

select distinct Nume_Profesor,Prenume_Profesor
from studenti_reusita sr
inner join profesori p on sr.Id_Profesor = p.Id_Profesor
inner join studenti s on sr.Id_Student = s.Id_Student
where s.Nume_Student = 'Cosovanu' and sr.Nota<5


![interogarea 19](Image1.png)


2. Interogarea Nr. 33

select distinct Nume_Student, Prenume_Student
from studenti_reusita sr
inner join studenti s on sr.Id_Student = s.Id_Student
where sr.Tip_Evaluare = 'Reusita curenta' and sr.Nota<5


![interogarea 33](Image2.png)