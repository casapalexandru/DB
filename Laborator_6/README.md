# Laboratorul Nr.6
# CREAREA TABELELOR SI INDECSILOR

#TASK_01
Sa se scrie o instructiune T-SQL, care ar popula coloana Adresa _ Postala _ Profesor din tabelul profesori cu valoarea 'Mun. Chisinau', unde adresa este necunoscuta:

```SQL
use universitatea
go
update profesori
set Adresa_Postala_Profesor = 'Mun. Chisinau'
where Adresa_Postala_Profesor is null
```

![interogarea 1](Image1.PNG)

#TASK_02
Sa se modifice schema tabelului grupe, ca sa corespunda urmatoarelor cerinte: a) Campul Cod_ Grupa sa accepte numai valorile unice ~i sa nu accepte valori necunoscute. b) Sa se tina cont ca cheie primarii, deja, este definitii asupra coloanei Id_ Grupa.

```SQL
create unique index idx_cod_grupa
on grupe (cod_grupa);
exec sp_helpindex grupe;
```
![interogarea 2](Image2.PNG)
