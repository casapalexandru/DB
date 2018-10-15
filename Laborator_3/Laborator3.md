# Laboratorul Nr.4

1. Interogarea Nr. 19
Gasiti Numele si Prenumele profesorilor, care au predat discipline, in care studentul "Cosovanu" a fost respins (nota<5) la cel putin o proba.

select distinct Nume_Profesor,Prenume_Profesor
from studenti_reusita sr
inner join profesori p on sr.Id_Profesor = p.Id_Profesor
inner join studenti s on sr.Id_Student = s.Id_Student
where s.Nume_Student = 'Cosovanu' and sr.Nota<5


![interogarea 19](Image1.png)


2. Interogarea Nr. 33
Gasiti Numele si Prenumele studentilor, care nu au luat nota de promovare la reusita curenta la nici o disciplina.

select distinct Nume_Student, Prenume_Student
from studenti_reusita sr
inner join studenti s on sr.Id_Student = s.Id_Student
where sr.Tip_Evaluare = 'Reusita curenta' and sr.Nota<5


![interogarea 33](Image2.png)



3. Interogarea Nr. 35
Gasiti denumirile disciplinelor si media notelor pe disciplina. Afisati numai disciplinele cu medii mai mari de 7.0.

select d.Disciplina,AVG(cast(sr.Nota as float)) as Media
from studenti_reusita sr
inner join discipline d on sr.Id_Disciplina = d.Id_Disciplina
group by d.Disciplina
having AVG(cast(sr.Nota as float)) > 7
order by Media

![interogarea 35](Image3.png)