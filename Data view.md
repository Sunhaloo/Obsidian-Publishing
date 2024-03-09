---
Alias: Overview Obsidian Vault
Tag: dataview
Date: 2023-12-16
Author: S.Sunhaloo
---

>[!info] What is this file about?
>This file will hold and overview of all the files in my vault

# All Files

```dataview

TABLE Tag, Date
WHERE file.name != "Data view"
SORT Date ASC

```

# In-Progress

```dataview

TABLE Tag, Date
WHERE file.name != "Data view" AND Status = "In-Progress"
SORT Date ASC

```

# Completed


```dataview

TABLE Tag, Date
WHERE file.name != "Data view" AND Status = "Completed"
SORT Date ASC

```

# On HOLD


```dataview

TABLE Tag, Date
WHERE file.name != "Data view" AND Status = "HOLD"
SORT Date ASC

```


# Archived

```dataview

TABLE Tag, Date
WHERE file.name != "Date view" AND Status = "HOLD"
SORT file.name ASC

```

# Tags

```dataview

List Tag
WHERE file.name != "Data view"
SORT Tag ASC
SORT file.name ASC

```