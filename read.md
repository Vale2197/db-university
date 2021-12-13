Modellizzare la struttura di una tabella per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi dipartimenti, ciascuno con i propri corsi di laurea;
- ogni corso di laurea è formato da diversi corsi;
- ogni corso può essere tenuto da diversi insegnanti e prevede più appelli d'esame;
- ogni studente è iscritto ad un corso di laurea;
- per ogni appello d'esame a cui lo studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente


## Table (Diparimenti) :

- nome dipartimento (Dipartimento Chirurgico, Medico, Dipartimento di Agraria),

- zona (Napoli, Sassari, Campobasso),

- indirizzo,

<!--  -->

## Table (main_courses) :

- nome (Acquacoltura e igiene delle produzioni ittiche, Advanced design, Aerospace Engineering),

- livello (Corso di Laurea Magistrale, Corso di Laurea Triennale),

- test (si, no),

- periodo (from 21 February 2022 to 8 June 2022.),


## Table (Courses) :

- nome (BIOCHIMICA, MICROBIOLOGIA ED EPIDEMIOLOGIA VETERINARIA,  ANATOMIA DEGLI ANIMALI ACQUATICI),

- crediti (3, 6, 8),
<!--  -->


## Table (Teachers);
- nome
- cognome
<!--  -->


## Table (appelli_esami)
<!-- data fissata dal professore -->
- data   

## Table (Students)
- nome
- cognome
- data di nascita
- numero di telefono

