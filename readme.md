# macOS Cheatsheet

**Highly recommended:** [tldr-pages/tldr](https://github.com/tldr-pages/tldr)
([website](https://tldr.sh))

> collection of community-maintained help pages for command-line tools, that
> aims to be a simpler, more approachable complement to traditional man pages.

---

- [macOS Cheatsheet](#macos-cheatsheet)
  - [Shell](#shell)
  - [PDF](#pdf)
  - [Plist](#plist)
  - [Preview](#preview)
  - [Related Projects](#related-projects)

## Shell

- Fix `zsh`'s `compinit` error when initializing a new shell

  > zsh compinit: insecure directories, run compaudit for list.
  > Ignore insecure directories and continue [y] or abort compinit [n]?

  ```sh
  # Run the following command to fix the error above
  compaudit | xargs chmod g-w
  ```

  [Source](https://github.com/zsh-users/zsh-completions/issues/680#issuecomment-612960481)

## PDF

- Merge PDFs

  ```sh
  gs -q -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=merged.pdf *.pdf
  ```
  
  [Source](https://apple.stackexchange.com/a/293198)

  ```sh
  # Requires 'python' binary
  #
  # Alternative 
  # Merge multiple pdfs in current directory with prefix foo, e.g.
  # foo1.pdf foo2.pdf and foo3.pdf and create new PDF called merged.pdf
  \ls -larth foo*.pdf | xargs "/System/Library/Automator/Combine PDF Pages.action/Contents/Resources/join.py" -o merged.pdf {}
  ```

  [Source](https://apple.stackexchange.com/a/230447)

  ```sh
  # Requires 'python' binary
  #
  # Alternative
  # Merge all pdfs in current directory into merged.pdf
  "/System/Library/Automator/Combine PDF Pages.action/Contents/Resources/join.py" -o merged.pdf *.pdf
  ```

## Plist

- View and edit .plist files

  ```sh
  # Print file in human-readable format
  plutil -p foo.plist
  ```

  ```sh
  # Print file as XML
  /usr/libexec/PlistBuddy -x -c "Print" foo.plist
  ```

## Preview

- Exact string matching in search

  Quote string, as in Google search bar, e.g.

  > "my sentence in preview"

  [Source](https://apple.stackexchange.com/a/155411)

## Related Projects

- **[rodrigobdz/linux-cheatsheet](https://github.com/rodrigobdz/linux-cheatsheet)**
- [rodrigobdz/minimal-readme](https://github.com/rodrigobdz/minimal-readme)
