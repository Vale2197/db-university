<!-- Selezionare tutti gli studenti nati nel 1990 -->
SELECT * FROM students;
SELECT * FROM `students` WHERE YEAR(`date_of_birth`) LIKE '1990';

<!-- Selezionare tutti i corsi che valgono più di 10 crediti -->
SELECT * FROM `courses` WHERE cfu > '10';

<!-- Selezionare tutti gli studenti che hanno più di 30 anni -->
SELECT * FROM `students` WHERE '2021' - YEAR(`date_of_birth`) > '30'

<!-- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea -->
SELECT * FROM `courses` WHERE `year` = '1' && `period` = 'I semestre'

<!-- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 -->
SELECT * FROM `exams` WHERE `hour` > '14:00:00' && `date` = '2020-06-20'

<!-- Selezionare tutti i corsi di laurea magistrale -->
SELECT * FROM `degrees` WHERE `level` = 'magistrale'

<!-- Da quanti dipartimenti è composta l'università? -->
SELECT COUNT(*) AS total_departments FROM departments

<!-- Quanti sono gli insegnanti che non hanno un numero di telefono? -->
SELECT COUNT(*) AS howManyTeacher_has_no_phone FROM `teachers` WHERE `phone` IS NULL