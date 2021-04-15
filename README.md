# CleanRepo

This command-line tool helps you clean up a DocFx-based content repo. It can:

- Find and delete markdown files that aren't linked from a TOC file.
- Find and delete orphaned image (.png, .jpg, .gif, .svg) files.
- Map images to the files that reference them.
- Find and delete orphaned "shared" markdown files (includes).
- Find and replace links to redirected files.
- Replace site-relative links with file-relative links (includes image links).

## Usage

| Command | Description |
| - | - |
| --start-directory | Top-level directory in which to perform clean up (for example, find orphaned markdown files). |
| --docset-root | The full path to the root directory for the docset, e.g. 'c:\users\gewarren\dotnet-docs\docs'. |
| --repo-root | The full path to the local root directory for the repository, e.g. 'c:\users\gewarren\dotnet-docs'. |
| --delete | True to delete orphaned files. |
| --orphaned-topics | Use this option to find orphaned articles. |
| --orphaned-images | Find orphaned .png, .gif, .svg, or .jpg files. |
| --orphaned-snippets | Find orphaned .cs and .vb files. |
| --orphaned-includes | Find orphaned INCLUDE files. |
| --catalog-images | Map images to the markdown/YAML files that reference them. This option generates a JSON file with the output. |
| --format-redirects | Format the redirection JSON file by deserializing and then serializing with pretty printing. |
| --replace-redirects | Find backlinks to redirected files and replace with new target. |
| --relative-links | Replace site-relative links with file-relative links.  You must also specify the docset name for the repo. |

## Usage examples

- Find orphaned articles recursively (that is, in the specified directory and any subdirectories):

  ```
  CleanRepo.exe --orphaned-topics
  
  -or-
  
  CleanRepo.exe --orphaned-topics --start-directory c:\repos\visualstudio-docs-pr\docs\ide
  ```

- Find and delete orphaned .png/.gif/.jpg/.svg files (recursive):

  ```
  CleanRepo.exe --orphaned-images --start-directory c:\repos\visualstudio-docs-pr\docs\ide
  ```
