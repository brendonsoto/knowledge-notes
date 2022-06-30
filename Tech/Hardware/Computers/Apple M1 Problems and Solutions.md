---
aliases: 
created: 2022-06-30, 3:41:33 pm (Thursday, June 30th)
updated: 2022-06-30, 3:46:20 pm (Thursday, June 30th)
---
## brew: installed apps can't run due to arch

Problem may look like:
```
Error: package or namespace load failed for ‘commonmark’ in dyn.load(file, DLLpath = DLLpath, ...):
 unable to load shared object '/Users/nico/test/erna_analysis/renv/staging/1/00LOCK-commonmark/00new/commonmark/libs/commonmark.so':
  dlopen(/Users/nico/test/erna_analysis/renv/staging/1/00LOCK-commonmark/00new/commonmark/libs/commonmark.so, 0x0006): tried: '/Users/nico/test/erna_analysis/renv/staging/1/00LOCK-commonmark/00new/commonmark/libs/commonmark.so' (mach-o file, but is an incompatible architecture (have 'arm64', need 'x86_64')), '/usr/local/lib/commonmark.so' (no such file), '/usr/lib/commonmark.so' (no such file)
```

Notice near the end: `(mach-o file, but is an incompatible architecture (have 'arm64', need 'x86_64'))`

To get around this:
- Install Rosetta2: `softwareupdate --install-rosetta`
- Re-download Homebrew: `arch -x86_64 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
- Setup alias for convenience: `alias brew="arch -x86_64 brew"`

## zsh: bad CPU type in executable: node
Run `softwareupdate --install-rosetta`

[source](https://stackoverflow.com/questions/71122488/zsh-bad-cpu-type-in-executable-node)