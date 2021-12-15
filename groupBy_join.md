GROUP BY
<!-- Contare quanti iscritti ci sono stati ogni anno -->
SELECT COUNT(*), year(enrolment_date) FROM students GROUP BY year(enrolment_date)

<!-- Contare gli insegnanti che hanno l'ufficio nello stesso edificio -->
SELECT COUNT(*), office_address FROM teachers GROUP BY office_address

<!-- Calcolare la media dei voti di ogni appello d'esame -->
SELECT COUNT(exam_id) as exam_id, avg(`vote`) as avarage FROM exam_student GROUP BY exam_id

<!-- Contare quanti corsi di laurea ci sono per ogni dipartimento
 -->
 SELECT COUNT(*) as number_of_degrees, department_id FROM degrees GROUP BY department_id

<!--  -->

JOIN

<!-- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia -->