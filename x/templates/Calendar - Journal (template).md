<%*
// Prompt for Date
const today = tp.date.now("YYYY-MM-DD");
const journalDate = await tp.system.prompt("Date (YYYY-MM-DD)", today);

// Handle Renaming
let title = tp.file.title;
if (!title.match(/^\d{4}-\d{2}-\d{2}/)) {
    if (title.startsWith("Untitled")) {
        const newTitle = await tp.system.prompt("Title");
        title = newTitle || "Untitled";
    }
    await tp.file.rename(`${journalDate} - ${title}`);
}
-%>
---
type: log
status: stable
date: <% journalDate %>
created: <% tp.file.creation_date("YYYY-MM-DD") %>
updated: <% tp.file.last_modified_date("YYYY-MM-DD") %>

---
## Pensieri

## Eventi

## Note
