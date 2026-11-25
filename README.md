# Duskline One Laugh

Entry for the make.fun bounty **[One Line, One Laugh](https://make.fun/bounty/u-4z4ghtbwm1fn7mibrqum4bxgfghhgqzriyhd8v3-one-line-0be61e5a)** — one funny line, short enough to read in a single breath, whole enough to land on its own.

## The entry

> I finally achieved work-life balance: I now hate both equally.

62 characters. The setup promises the corporate dream ("achieved work-life
balance"); the punchline reframes it — the balance was achieved by hating
both sides equally. Self-contained, one real twist, nothing to cut.

## How the program works

`main.py` (Python 3.13, standard library only, deterministic, no network)
writes that exact line to `$MAKEFUN_OUTPUT_DIR/entry.txt`:

1. Validates the text against the bounty gate before writing: UTF-8,
   1–140 characters, not only whitespace.
2. Writes **only** to `$MAKEFUN_OUTPUT_DIR` (or a fresh temp dir when the
   variable is unset) — never into the repository.
3. Hard guard: if the resolved output directory is the repo directory (or
   inside it), the program refuses to write anything and exits 0.
4. Reads the file back after writing and re-validates it; a mismatch means
   no valid output.
5. Never raises: any write failure exits 0 silently.

## Run it

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out python3 main.py
cat /tmp/out/entry.txt
```
