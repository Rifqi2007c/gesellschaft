if emerge keep failing to download doasedit. make it

- in `/usr/local/bin/`
- make file name `doasedit`
	- inside the file
```
#!/bin/sh
if [ -z "$1" ]; then
    echo "Usage: doasedit <file>"
    exit 1
fi

# Use user's preferred editor, fallback to nano
MY_EDITOR=${EDITOR:-nvim}

# Create a temporary file safely
TMPFILE=$(mktemp /tmp/doasedit.XXXXXXXX)

# Copy original file contents if it exists
if [ -f "$1" ]; then
    cat "$1" > "$TMPFILE"
fi

# Open the copy with user privileges
$MY_EDITOR "$TMPFILE"

# Write the changes back to the root destination using doas
doas cp "$TMPFILE" "$1"
rm -f "$TMPFILE"
```

- doas edit should be available
- export file editor preference if prefered other than nano editor
	- example with neovim: `export EDITOR="nvim"`
	- put this inside a shell or put it inside `.bashrc` or similar

---
#gentoo