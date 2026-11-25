# Descrizione Dati

- entità:
    - Evento
    - Sede

- campi di ciascuna entità:
    - sedi (`sedi.json`):
        - id (number)
        - nome (string)
        - indirizzo (string)
    - eventi (`eventi.json`):
        - id (number)
        - titolo (string)
        - data (string)
        - orario (string)
        - categoria (string)
        - descrizione (string)
        - immagine (string)
        - immagine_alt (string)
        - sede_id (number)

- chiave primaria:
    - sedi: id (numerico, univoco nell'entità e stabile)
    - eventi: id (numerico, univoco nell'entità e stabile)

- relazione:
    - una sede può ospitare più eventi
    - ogni evento si svolge in una sola sede
    - `Evento.sede_id` fa riferimento a `Sede.id`

- quantità:
    - 6 eventi
    - 3 sedi

- chi aggiorna i dati e come:
    - modifica manuale dei file `dati/eventi.json` e `dati/sedi.json` nella repository e successiva pubblicazione del sito

- che cosa mostra la pagina:
    - il programma dei 6 eventi (con titolo, data, orario, categoria, descrizione, immagine e sede collegata tramite `sede_id`) e le informazioni delle 3 sedi

---

# Scheda Sedi

- Sede 1:
    - id: 1
    - nome: Officina Nord — Sede centrale
    - indirizzo: Corso Duca degli Abruzzi 24, Torino

- Sede 2:
    - id: 2
    - nome: Spazio Forma — Politecnico al Valentino
    - indirizzo: Viale Mattioli 39, Torino

- Sede 3:
    - id: 3
    - nome: Cortile Comune — Sede di Mirafiori
    - indirizzo: Corso Luigi Settembrini 178, Torino

---

# Scheda Eventi

- Evento 1:
    - id: 1
    - titolo: Lettere in movimento
    - data: 2026-06-12
    - orario: 10:00
    - categoria: Incontro
    - descrizione: Come cambia un messaggio quando cambiano le lettere? Un incontro su tipografia, ritmo e comunicazione visiva.
    - immagine: assets/foto programma/1.png
    - immagine_alt: Due forme geometriche che si toccano
    - sede_id: 1 (Officina Nord — Sede centrale)

- Evento 2:
    - id: 2
    - titolo: Materia seconda
    - data: 2026-06-12
    - orario: 14:00
    - categoria: Laboratorio
    - descrizione: Un laboratorio per osservare materiali di recupero e immaginare nuovi utilizzi attraverso piccoli esperimenti.
    - immagine: assets/foto programma/2.png
    - immagine_alt: Forma geometrica con spigoli
    - sede_id: 2 (Spazio Forma — Politecnico al Valentino)

- Evento 3:
    - id: 3
    - titolo: La città in un manifesto
    - data: 2026-06-12
    - orario: 17:00
    - categoria: Mostra
    - descrizione: Una raccolta di manifesti immaginari racconta quartieri, incontri e abitudini della città attraverso forme e colori.
    - immagine: assets/foto programma/3.png
    - immagine_alt: Forma geometrica arrotondata
    - sede_id: 3 (Cortile Comune — Sede di Mirafiori)

- Evento 4:
    - id: 4
    - titolo: Oggetti in dialogo
    - data: 2026-06-13
    - orario: 10:00
    - categoria: Incontro
    - descrizione: Designer e artigiani discutono come nascono gli oggetti quotidiani, tra funzione, cura dei dettagli e possibilità di riparazione.
    - immagine: assets/foto programma/4.png
    - immagine_alt: Forma geometrica arrotondata e tagliata
    - sede_id: 1 (Officina Nord — Sede centrale)

- Evento 5:
    - id: 5
    - titolo: Mappe da abitare
    - data: 2026-06-13
    - orario: 14:00
    - categoria: Laboratorio
    - descrizione: Disegniamo una mappa fatta di percorsi, punti di incontro e luoghi da riscoprire, partendo dall'esperienza di chi li attraversa.
    - immagine: assets/foto programma/5.png
    - immagine_alt: Forma geometrica arrotondata con bordi lineari
    - sede_id: 2 (Spazio Forma — Politecnico al Valentino)

- Evento 6:
    - id: 6
    - titolo: Progettare insieme
    - data: 2026-06-13
    - orario: 17:00
    - categoria: Mostra
    - descrizione: Una selezione di progetti collettivi mostra come idee diverse possano diventare un risultato condiviso.
    - immagine: assets/foto programma/6.png
    - immagine_alt: Forme geometriche orizzonatali spigolose intersecate tra di loro
    - sede_id: 3 (Cortile Comune — Sede di Mirafiori)

---

# Schema Evento–Sede

```mermaid
erDiagram
    SEDE ||--o{ EVENTO : ospita
    SEDE {
        number id PK
        string nome
        string indirizzo
    }
    EVENTO {
        number id PK
        string titolo
        string data
        string orario
        string categoria
        string descrizione
        string immagine
        string immagine_alt
        number sede_id FK
    }