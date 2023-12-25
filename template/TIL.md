---
<%*
const title = tp.file.title;
const today = moment(title).format("YYYY-MM-DD");
const yesterday = moment(title).subtract(1, 'days').format("YYYY-MM-DD");
const tomorrow = moment(title).add(1, 'days').format("YYYY-MM-DD");
-%>
created: <% tp.file.creation_date() %>
updated: <% tp.file.creation_date() %>
tag: ['TIL']
---
# <% today %>
<< [[<% yesterday %>]] | [[<% tomorrow %>]]>>
---

### 📅 Today I Learned
- <% tp.file.cursor(0) %>

- [ ]


# 📝 Notes
### Notes created today
```dataview

List FROM "" WHERE file.cday = date("<%today%>") SORT file.ctime asc

```

### Notes modified today
```dataview

List FROM "" WHERE file.mday = date("<%today%>") SORT file.mtime asc

```