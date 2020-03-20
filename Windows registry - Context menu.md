# How-To

Choose a target, create a unique key, then fill in the values and subkeys.

Data type of all values should be String (`REG_SZ`).



# Targets in `HKCR`

| Location | Whose context menu? |
| -------- | ----------- |
| `Directory\shell`         | Folder |
| `Directory\Background\shell`         | "Background" of the folder (i.e. enter a folder, then open its context menu) |
| `Drive\shell`         | Drive |
| `LibraryFolder\shell` | Folder in Libraries |



# Key

| Name                 | Description/Default Value                                    |
| -------------------- | ------------------------------------------------------------ |
| `@` (Default key)    | Name of the item in menu[^1]                                 |
| `NoWorkingDirectory` | Empty string                                                 |
| `NeverDefault`       | Empty string                                                 |
| `Icon`               | Path to executable (first icon, or `,0`, will be used), DLL, or icon file |
| `command`            | **Important**                                                |
| `command\@`          | Command to execute[^2]                                       |



[^1]: `&` = underlined letter (for keyboard navigation)
[^2]: Environment/Context-dependent variables for `command\@` might be required. See [MSDN "Extending Shortcut Menus"](https://web.archive.org/web/20111002101214/http://msdn.microsoft.com/en-us/library/windows/desktop/cc144101(v=vs.85).aspx) for more details.

| Variable | Description                                                  |
| -------- | ------------------------------------------------------------ |
| `%V`     | Windows Explorer variable. Loosely understood as "current directory" |
| `%1`     | First file parameter                                         |
| `%L`     | First file parameter, "Long path" (legacy)                   |

