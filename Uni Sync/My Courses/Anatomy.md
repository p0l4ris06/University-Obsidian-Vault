---
sticker: emoji//1f52c
banner: https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/64c79653-8106-46e6-ab9e-9b2561fd338d/d74ygco-3b709aaa-70a6-4633-80a7-7331eaff839d.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzY0Yzc5NjUzLTgxMDYtNDZlNi1hYjllLTliMjU2MWZkMzM4ZFwvZDc0eWdjby0zYjcwOWFhYS03MGE2LTQ2MzMtODBhNy03MzMxZWFmZjgzOWQuanBnIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.-VBEL2eifTrfBxB-_zd_7lAYw5PcZ9TCYY5PoGKiGuM
banner_y: "6"
---
```dataviewjs
const targetFolder = "My Units/AS1A"; // Full path to the AS1A folder
const foldersToOmit = new Set(["AS1A Definitions", "AS1A Diagrams"]); // Folders to exclude
const folders = new Set();

// Iterate through all pages/files in the target folder
for (const page of dv.pages(`"${targetFolder}"`)) {
    const folderPath = page.file.folder;

    // Check if the file is inside the target folder
    if (folderPath.startsWith(targetFolder)) {
        const relativePath = folderPath.slice(targetFolder.length).split("/")[1];
        
        // Add to the set only if it's not in the omit list
        if (relativePath && !foldersToOmit.has(relativePath)) {
            folders.add(relativePath);
        }
    }
}

// Convert to an array and sort alphabetically
const sortedFolders = Array.from(folders).sort();

// Display sorted folders in a table
dv.table(["Folder"], sortedFolders.map(folder => [folder]));

```
