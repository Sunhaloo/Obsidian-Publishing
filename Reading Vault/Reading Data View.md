---
Alias: Reading Road-Map
Tag: books, dataview
Author: S.Sunhaloo
Type: Road-Map
Date: 16-09-2023
---

# Reading Vault

## All Files

```dataview
TABLE Status, Type, Rating
FROM "Reading Vault"
WHERE file.name != "Reading Data View"
SORT file.name ASC
```

---

## Anime Folder

### Anime - Manga Folder

#### To Read

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Manga"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Not-Started"
```

#### Currently Reading

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Manga"
WHERE file.name != "Reading Data View Folder Test" AND Status = "In-Progress"
```

#### Completed

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Manga"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Completed"
```

### Anime - Anime Books Folder

#### To Read

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Books"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Not-Started"
```

#### Currently Reading

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Books"
WHERE file.name != "Reading Data View Folder Test" AND Status = "In-Progress"
```

#### Completed

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Anime/Books"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Completed"
```

---

## Productivity Folder

### To Read

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, Rating, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Productivity"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Not-Started"
```

### Currently Reading

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Productivity"
WHERE file.name != "Reading Data View Folder Test" AND Status = "In-Progress"
```

### Completed Books

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Productivity"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Completed"
```

---

## Religion Folder

### To Read

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Theological"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Not-Started"
```

### Currently Reading

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Theological"
WHERE file.name != "Reading Data View Folder Test" AND Status = "In-Progress"
```

### Completed

```dataview
TABLE Author, Type, Date_Started, Date_Finished, Pages, ("![|50](" + cover + ")") as Cover
FROM "Reading Vault/Theological"
WHERE file.name != "Reading Data View Folder Test" AND Status = "Completed"
```

# Linking Files

## Why am I Doing This?

So that, in the *graph view*, I get to link all related **reading** files in one place.

# People

This is a document where I keep all the people that have said a quote.

- [[Authors]]

# Recommended Books to Read

- [[Reading Recommendations]]

# Anime Folder

## Manga Folder

## Anime Books Folder

- [[Rascal Does Not Dream of Bunny Girl-Senpai]]

# Productivity Folder

- [[Steal Like An Artist Notes]]
- [[How to Take Smart Notes]]
- [[Building a Second Brain]]
- [[The Subtle Art of Not Giving a Fuck Notes]]
- [[Exile]]
	- [[Exile Definitions]]

# Religion Folder

- [[The Holy Qur'an Notes]]