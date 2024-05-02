Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.


# Table name: Department

- id | INDEX | PK | AI | UNIQUE | BIGINT
- name | VARCHAR(150) | NOT NULL
- address | VARCHAR(100) | NULL

# Table name: degree

- id | INDEX | PK | NOT NULL | AI | UNIQUE | BIGINT
- title | VARCHAR(255) | NOT NULL
- length | VARCHAR(15) | NULL
- department_id | FK

# Table name: courses

- id | INDEX | PK | AI | UNIQUE | BIGINT
- title | VARCHAR(150) | NOT NULL
- hours | TINYINT | NULL
- start_date | DATE | NULL
- degree_id | FK
- teacher_id

# Table name: appeals

- id | INDEX | PK | AI | UNIQUE | BIGINT
- date | DATETIME | NOT NULL
- student_id | FK
- registration_id | FK

# Table name: students
- id | INDEX | PK | AI | UNIQUE | BIGINT
- name | VARCHAR(100) | NOT NULL
- lastname | VARCHAR(100) | NULL
- email | VARCHAR(255) | NOT NULL
- birthday| DATE | NULL
- student_id_number | VARCHAR(6) | NOT NULL
- degree_id |FK
- exame_id | FK

# Table name: exame_registration
- id | INDEX | PK | AI | UNIQUE | BIGINT
- vote | TINYINT | NOT NULL
- student_id | FK
- appel_id | FK


# Table name: teachers
- id | INDEX | PK | AI | UNIQUE | BIGINT
- name | VARCHAR(100) | NOT NULL
- lastname | VARCHAR(100) | NULL
- email | VARCHAR(255) | NULL
- course_id | FK

