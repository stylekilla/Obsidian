<%*
	let name = await tp.system.prompt("Note Title");
	if (name == null) { name = "Untitled"; }
	let title = tp.file.creation_date("YYYY-MM-DD") + " " + name;
	const folders = this.app.vault.getAllLoadedFiles().filter(i => i.children).map(folder => folder.path);
	let project = await tp.system.suggester(folders, folders);
	if (project == null) { project = "Everything Else"; }
	await tp.file.rename(title);
	await tp.file.move("/" + project + "/" + title);
 -%>
---
type: note
project: <% project %>
created: <% tp.file.creation_date() %> 
---

# <% title %>
**Tags:** <% tp.file.cursor(1) %>

---

# <% tp.file.cursor(2) %>
<% tp.file.cursor(3) %>