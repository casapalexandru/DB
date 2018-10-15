# Laboratorul Nr.4

1. Interogarea Nr. 19

select distinct Nume_Profesor,Prenume_Profesor
from studenti_reusita sr
inner join profesori p on sr.Id_Profesor = p.Id_Profesor
inner join studenti s on sr.Id_Student = s.Id_Student
where s.Nume_Student = 'Cosovanu' and sr.Nota<5


![interogarea 19](Image3.1.png)