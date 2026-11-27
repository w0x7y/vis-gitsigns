# vis-gitsigns

git signs for [vis](https://github.com/martanne/vis): marks lines added, changed or removed since the git index, updated as you type

### install

needs vis `0.9` or later and `git`

```sh
git clone https://github.com/w0x7y/vis-gitsigns ~/.config/vis/plugins/vis-gitsigns
```

then in `visrc.lua`:

```lua
require("plugins/vis-gitsigns")
```

### how it works

~ diffs the buffer in lua (myers' diff) against the file's version in the git index (`git show :./<file>`)\
~ added lines are green, changed lines blue, and the line below removed lines red\
~ three display styles, switchable at runtime with `:set gitsigns <display>`: `number` (colored line number), `bar` (tinted gap before the text) and `background` (tinted block behind the number)\
~ the index is read on open and save, so a `git add` from a shell shows up after the next save

### config

```lua
local gitsigns = require("plugins/vis-gitsigns")
gitsigns.display = "background" -- "number", "bar" or "background"
gitsigns.opacity = 0.1          -- 0 to 1, how much of the color a tint keeps (default 0.35)
gitsigns.base = "#23272e"       -- background #rrggbb tints fade into
gitsigns.colors = { add = "#9ad8ac", change = "#7aa4e4", removed = "#d98a9c" }
```

without `#rrggbb` colors and `base`, tints stay solid named colors

_license: [mit](./LICENSE)_
