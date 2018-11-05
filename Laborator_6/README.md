# Laboratorul Nr.6
# CREAREA TABELELOR SI INDECSILOR

TASK_01
Sa se scrie o instructiune T-SQL, care ar popula coloana Adresa _ Postala _ Profesor din tabelul profesori cu valoarea 'Mun. Chisinau', unde adresa este necunoscuta:

```SQL
use universitatea
go
update profesori
set Adresa_Postala_Profesor = 'Mun. Chisinau'
where Adresa_Postala_Profesor is null
```

![interogarea 1](Image1.PNG)
