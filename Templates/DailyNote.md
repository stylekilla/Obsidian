---
type: dailynote
created: <% tp.file.creation_date() %>
---
# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>
**Tags:** #dailynote

---

### 📅 Daily Questions

##### 🙌 One thing I've excited about right now is...
-<% tp.file.cursor(1) %>

##### 🚀 One+ thing I plan to accomplish today is...
- [ ] <% tp.file.cursor(2) %>

##### 👎 One thing I'm struggling with today is...
- <% tp.file.cursor(3) %>

---

# Todo
- <% tp.file.cursor(4) %>

---

### Notes created today
```dataview

List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc

```

### Notes last touched today
```dataview

List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc

```