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
SELECT DISTINCT degrees.name as degree_name, students.name as students_name, students.surname as students_surname;

FROM degrees;

JOIN students ON degrees.id = students.degree_id;

WHERE degrees.name = 'Corso di Laurea in Economia';

<!-- Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze -->
SELECT departments.id as dep_id, degrees.name;

FROM degrees;

JOIN departments ON degrees.department_id = departments.id;

WHERE departments.name = 'Dipartimento di Neuroscienze';

<!-- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44) -->
SELECT teachers.name as teach_name, teachers.surname as teach_surn, courses.name as course_name, courses.description as course_descr;

FROM course_teacher;

JOIN teachers ON teachers.id = course_teacher.teacher_id;

JOIN courses ON courses.id = course_teacher.course_id;

WHERE teachers.id = 44

<!-- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome -->
SELECT DISTINCT  students.surname as student_surname, students.name AS students_name, degrees.id as degree_id, degrees.name as degree_name, departments.id as dep_id, departments.name as dep_name;

FROM students;

JOIN degrees ON degrees.id = students.degree_id;

JOIN departments ON departments.id = degrees.department_id;

ORDER BY students.surname, students.name ASC;

<!-- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti -->
SELECT degrees.name as degrees_name, courses.name AS course_name, teachers.name as teacher_name, teachers.surname as teacher_surname;

FROM course_teacher;

JOIN courses ON courses.id = course_teacher.course_id;

JOIN teachers ON teachers.id = course_teacher.teacher_id;

JOIN degrees ON degrees.id = courses.degree_id;

ORDER BY `degrees_name` ASC

<!-- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) -->
select DISTINCT departments.name as department_name, teachers.name as teacher_name, teachers.surname as teacher_surname;

FROM course_teacher;

JOIN teachers ON teachers.id = course_teacher.teacher_id;

JOIN courses ON courses.id = course_teacher.course_id;

JOIN degrees on degrees.id = courses.degree_id;

JOIN departments on departments.id = degrees.department_id;

WHERE departments.name = 'Dipartimento di Matematica';

ORDER BY teachers.name, teachers.surname asc

<!-- Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami -->
