<!-- Selezionare tutti gli studenti nati nel 1990 -->
SELECT * FROM students;
SELECT * FROM `students` WHERE YEAR(`date_of_birth`) LIKE '1990';

<!-- Selezionare tutti i corsi che valgono più di 10 crediti -->