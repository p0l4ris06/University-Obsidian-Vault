---
sticker: emoji//1f468-200d-1f393
banner: https://www.purina.co.uk/sites/default/files/2020-12/Understanding%20Your%20Cat%27s%20Body%20LanguageTEASER.jpg
banner_y: "44"
---

```dataviewjs
const targetFolder = "My Units/PPVN"; // Full path to the PPVN folder
const files = [];

// Iterate through all pages/files in the target folder
for (const page of dv.pages(`"${targetFolder}"`)) {
    files.push({ Name: page.file.name, Path: page.file.path });
}

// Display files in a table
dv.table(["File Name", "Path"], files.map(file => [file.Name, file.Path]));

```
