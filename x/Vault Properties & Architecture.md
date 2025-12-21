---
type: log
project: vault-meta
status: stable
topics: [system-design, obsidian, documentation]
---

# Vault Properties & Architecture

## Filosofia Core
Questo vault utilizza un sistema di proprietà "Project-Centric".
- **project**: Definisce il contesto di *creazione* (Perché sto creando questa nota?).
- **topics**: Definisce il contesto del *contenuto* (Di cosa parla questa nota?).
- **type**: Definisce la *struttura* (Che forma ha questo dato?).

Le note senza un `project` sono considerate parte dell'**Atlas** (General Knowledge Base).

---

## 1. Global Properties
Ogni nota nel vault dovrebbe contenere queste chiavi.

### `type`
Definisce l'identità strutturale della nota. Determina quale template è stato usato.
*   `concept` - Idee astratte, teorie, definizioni.
*   `source` - Libri, articoli, video, paper.
*   `person` - Esseri umani del mondo reale.
*   `character` - Entità fittizie (mie o di altri).
*   `location` - Luoghi (reali o fittizi).
*   `faction` - Gruppi, aziende, gilde, organizzazioni.
*   `event` - Eventi storici o narrativi.
*   `system` - Set di regole (Magia, Tecnologia, Legge, Biologia).
*   `dream` - Entry del diario onirico.
*   `log` - Pensieri generali, meeting, meta-note.
*   `project` - Definisce un progetto stesso.

### `project`
Lo sforzo attivo a cui appartiene questa nota. Se `null`, è Conoscenza Generale.
*   `misteri-di-harrondill` - Worldbuilding: I misteri di Harrondill.
*   `uni-fstp` - Università: Scienze e Tecniche Psicologiche.
*   `domnia` - Lavoro: Progetti Domnia.
*   `individuation` - Self-analysis, Sogni, Diario personale.
*   `vault-meta` - Manutenzione del sistema e design.

### `topics`
Una lista di tag/keyword che descrivono il contenuto. Sostituisce i `#tags` inline.
*   *Examples:* `[neuroscience, epistemology, magic, coding, psychology, jung, horror]`

---

## 2. Management Properties
Per tracciare il ciclo di vita della nota.

*   `status`:
    *   `seed` - Solo un'idea o uno stub.
    *   `draft` - In fase di scrittura attiva.
    *   `stable` - Finito / Materiale di riferimento.
    *   `archived` - Non più rilevante.
*   `created`: `YYYY-MM-DD`
*   `updated`: `YYYY-MM-DD`

---

## 3. Specific Properties
Usate solo per `type` specifici.

| Type | Property | Description |
| :--- | :--- | :--- |
| **source** | `author` | Link a `[[Person]]`. |
| | `year` | Anno di pubblicazione. |
| | `media` | `book`, `paper`, `video`. |
| **dream** | `lucidity` | Scala 1-5. |
| | `intensity` | Scala 1-5. |
| **character** | `role` | `protagonist`, `npc`, etc. |
| | `affiliation` | Link a `[[Faction]]`. |

---

## 4. Folder Structure (Reference)
*   **Atlas 🧿**: Conoscenza Generale (No Project).
*   **Efforts**: Progetti Attivi (`harrondill`, `uni`, `work`).
*   **Calendar 📅**: Entry basate sul tempo (`individuation`).
