## Joins

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
  - SELECT students.name, students.surname, students.registration_number, students.email 
    FROM students 
    JOIN degrees 
    ON degrees.id = students.degree_id 
    WHERE degrees.name = 'Corso di Laurea in Economia';

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
  - SELECT degrees.name, degrees.level, degrees.address 
    FROM degrees JOIN departments 
    ON departments.name = 'Dipartimento di Neuroscienze' 
    WHERE level = 'magistrale';

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
  - SELECT * 
    FROM courses 
    JOIN teachers 
    ON teachers.id = 44;

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
  - SELECT `students`.`surname` AS `surname`, `students`.`name` AS `name`, `degrees`.`name` AS 'course_name', `departments`.`name` AS 'department_name' 
   FROM `students` 
   JOIN `departments` 
   JOIN `degrees` 
   ORDER BY `students`.`surname`,`students`.`name`;

- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
  - SELECT `degrees`.`name` AS `course_name`, `teachers`.`name` ,`teachers`.`surname`
    FROM `degrees`
    JOIN `teachers`;

- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
  - SELECT `teachers`.`surname`,`teachers`.`name` 
    FROM `teachers`
    JOIN `departments`
    WHERE `departments`.`name` = 'Dipartimento di Matematica'
    ORDER BY `teachers`.`surname`;

-BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

fine
