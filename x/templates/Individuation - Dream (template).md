<%*
// Prompt for Date (Default to Today)
const today = tp.date.now("YYYY-MM-DD");
const dreamDate = await tp.system.prompt("Date of Dream (YYYY-MM-DD)", today);

// Handle Renaming
let title = tp.file.title;
if (!title.match(/^\d{4}-\d{2}-\d{2}/)) {
    if (title.startsWith("Untitled") || title.startsWith("Dream")) {
        const newTitle = await tp.system.prompt("Dream Title");
        title = newTitle || "Untitled";
    }
    await tp.file.rename(`${dreamDate} - ${title}`);
}
-%>
---
type: dream
project: individuation
status: stable
date: <% dreamDate %>
created: <% tp.file.creation_date("YYYY-MM-DD") %>
updated: <% tp.file.last_modified_date("YYYY-MM-DD") %>
lucidity: 1
intensity: 3
topics: []
---
# <% title %>

## Dream
Description...

## Interpretation
...
