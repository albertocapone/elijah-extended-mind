---
type: log
project: vault-meta
status: stable
topics: [system-design, obsidian, documentation]
created: 2025-12-21
updated: 2025-12-22
---
# Vault Properties & Architecture

## Filosofia Core
Questo vault utilizza un sistema di proprietà "Project-Centric".
- **project**: Definisce il contesto di *creazione* (Perché sto creando questa nota?).
- **topics**: Definisce il contesto del *contenuto* (Di cosa parla questa nota?).
- **type**: Definisce la *struttura* (Che forma ha questo dato?).

**Atlas vs Progetti:**
Le note di "Conoscenza Generale" (es. Storia della Psicologia) vivono nell'**Atlas** e **NON** devono avere un `project`. Sono verità universali.
I progetti (es. `uni-fstp`) linkano queste note, ma non le possiedono.

---

## 1. Global Properties
Ogni nota nel vault dovrebbe contenere queste chiavi.

### `type`
Definisce l'identità strutturale della nota. Determina quale template è stato usato.
*   `concept` - Idee astratte, teorie, definizioni.
*   `source` - Libri, articoli, video, paper.
*   `person` - Esseri umani del mondo reale.
*   `character` - Entità fittizie (tue o di altri).
*   `location` - Luoghi (reali o fittizi).
*   `faction` - Gruppi, aziende, gilde, organizzazioni.
*   `event` - Eventi storici o narrativi.
*   `system` - Set di regole (Magia, Tecnologia, Legge, Biologia).
*   `dream` - Entry del diario notturno.
*   `log` - Pensieri generali, meeting, meta-note.
*   `software` - Applicazioni, tool, specifiche tecniche.
*   `planning` - Pianificazione attività o progetti.
*   `project` - Un file che definisce un progetto stesso.

### `project`
Lo sforzo attivo a cui appartiene questa nota. Se `null`, è Conoscenza Generale.
*   `misteri-di-harrondill` - Worldbuilding: I misteri di Harrondill.
*   `uni-fstp` - Università: Scienze e Tecniche Psicologiche.
*   `domnia` - Lavoro: Progetti Domnia.
*   `individuation` - Self-analysis, Sogni, Diario personale.
*   `vault-meta` - Manutenzione del sistema e design.

### `topics`
Una lista di tag/keyword "Alto Livello". Non usare per dettagli effimeri.
*   *Good:* `[psychology, coding, magic]`
*   *Bad:* `[green-hair, time-travel-paradox]`

---

## 2. Management Properties
Per tracciare il ciclo di vita della nota.

*   `status`:
    *   `seed` - Solo un'idea o uno stub.
    *   `draft` - In fase di scrittura attiva.
    *   `stable` - Finito / Materiale di riferimento.
    *   `archived` - Non più rilevante.
*   `created`: `YYYY-MM-DD` (Gestito da Templater)
*   `updated`: `YYYY-MM-DD` (Gestito da Linter/Plugin)

---

## 3. Specific Properties
Usate solo per `type` specifici.

| Type | Property | Description |
| :--- | :--- | :--- |
| **source** | `author` | Lista di link: `["[[Person]]"]`. |
| | `year` | Anno di pubblicazione. |
| | `url` | Link esterno (Web). |
| | `media` | `book`, `paper`, `video`. |
| **dream** | `lucidity` | Scala 1-5. |
| | `intensity` | Scala 1-5. |
| **character** | `role` | `protagonist`, `npc`, villain. |
| | `affiliation` | Link a `[[Faction]]`. |
| | `author` | Opzionale. Se esterno (es. Stephen King). |

---

## 4. Folder Structure (Reference)

*   **Atlas 🧿**: Conoscenza Generale (No Project).

*   **Efforts**: Progetti Attivi (`misteri-di-harrondill`, `uni`, `work`).

*   **Calendar 📅**: Entry basate sul tempo (`individuation`).

*   **x**: Centralized Assets & System Files.

    *   `templates/`

    *   `docs/`

    *   `images/`

    *   `bases/`


