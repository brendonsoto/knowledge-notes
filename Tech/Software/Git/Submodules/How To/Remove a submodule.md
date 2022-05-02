---
aliases: 
created: 2022-02-03, 1:42:41 pm (Thursday, February 3rd)
updated: 2022-02-03, 1:45:33 pm (Thursday, February 3rd)
---
- Delete the relevant section from the .gitmodules file.
- Stage the .gitmodules changes:
    - git add .gitmodules
- Delete the relevant section from .git/config.
- Remove the submodule files from the working tree and index:
    - git rm --cached path_to_submodule (no trailing slash).
- Remove the submodule's .git directory:
    - rm -rf .git/modules/path_to_submodule
- Commit the changes:
    - git commit -m "Removed submodule <name/>"
- Delete the now untracked submodule files:
    - rm -rf path_to_submodule

## Resources
- [Stack Overflow source](https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule)

## Related
- [[Tech/Git/Submodules/How To/Add a submodule]]