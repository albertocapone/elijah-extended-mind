<%*
// Prompt for Date (Default to Today)
const today = tp.date.now("YYYY-MM-DD");
const syncDate = await tp.system.prompt("Date of Synchronicity (YYYY-MM-DD)", today);

// Handle Renaming
let title = tp.file.title;
if (!title.match(/^\d{4}-\d{2}-\d{2}/)) {
    if (title.startsWith("Untitled")) {
        const newTitle = await tp.system.prompt("Title");
        title = newTitle || "Untitled";
    }
    await tp.file.rename(`${syncDate} - ${title}`);
}
-%>
---
type: synchronicity
project: individuation
status: stable
date: <% syncDate %>
created: <% tp.file.creation_date("YYYY-MM-DD") %>
updated: <% tp.file.last_modified_date("YYYY-MM-DD") %>
image: 

---
## Evento Interno

## Evento Esterno

## Significato
