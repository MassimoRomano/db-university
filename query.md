# ESERCIZIO

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le query del file allegato.
Cosa consegnare?
Dopo aver testato le vostre query con phpMyAdmin, riportatele in un file query.md e caricatelo nella vostra repo.
Selezionare tutti gli studenti nati nel 1990 (160)
Selezionare tutti i corsi che valgono più di 10 crediti (479)
Selezionare tutti gli studenti che hanno più di 30 anni
Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
Selezionare tutti i corsi di laurea magistrale (38)
Da quanti dipartimenti è composta l'università? (12)
Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

# SVOLGIMENTO

# Selezionare tutti gli studenti nati nel 1990 (160)

- SELECT * FROM `students` WHERE `date_of_birth` LIKE '1990-%';

# Selezionare tutti i corsi che valgono più di 10 crediti (479)

- SELECT `cfu` FROM `courses` WHERE cfu > 10; 
  - sono 479 corsi in totale

# Selezionare tutti gli studenti che hanno più di 30 anni
- SELECT * FROM `students` WHERE `date_of_birth` <= '1994';
  -sono 3646 studenti che hanno piu di 30 anni

# Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
- SELECT * FROM `courses` WHERE `period` = 'I semestre' AND `year` = '1';
  - sono 286 corsi

# Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
- SELECT * FROM `exams` WHERE `hour` >= '14:00:00' AND `date` = '2020-06-20';
  - sono 21 esami in totale

# Selezionare tutti i corsi di laurea magistrale (38)
- SELECT * FROM degrees WHERE level = 'magistrale';
  - sono 38 in totale


# Da quanti dipartimenti è composta l'università? (12)
- SELECT COUNT(*) AS id FROM `departments`;
  - sono 12 in totale 

# Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
- SELECT * FROM teachers WHERE phone is null;
  - sono 50


finito