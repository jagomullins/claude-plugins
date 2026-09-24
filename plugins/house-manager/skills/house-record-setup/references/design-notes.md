# The record page's design

The page ships styled. Change it only if the user asks, and keep it consistent with these tokens.

## Colour (light / dark)

| Token | Light | Dark | Use |
| --- | --- | --- | --- |
| ground | `#F7F2E9` | `#1A1512` | the page |
| surface | `#FFFCF6` | `#231D18` | cards, tables |
| surface-sunk | `#EFE6D7` | `#2E2620` | hovers, count pills |
| surface-field | `#FBF6EE` | `#282119` | inside inputs |
| ink | `#2A1F18` | `#F2EAE0` | headings, answers |
| ink-muted | `#6B5B4C` | `#B3A392` | sentences, values |
| ink-quiet | `#786755` | `#9A8878` | uppercase labels, "Unknown" |
| line | `#E3D8C6` | `#362D25` | borders, rules |
| line-soft | `#EEE5D6` | `#2C2520` | dividers inside a card |
| clay | `#9E5B39` | `#D4906A` | the one accent |
| clay-soft | `#F3E3D6` | `#35251C` | attention block, doc chips |
| olive | `#47603D` | `#9DB88B` | filed, covered, done |
| amber | `#7E5813` | `#DFAC62` | ends soon |
| brick | `#9C3B2B` | `#E08D7C` | overdue, expired, destructive |

Every text pairing clears 4.5:1 in both themes. `ink-quiet` is the floor for text.

## Type

Petrona (serif) for what is kept — house name, section titles, record names, question text. Karla (sans) for what is operated — body, values, labels, buttons, tables. Both from Google Fonts; no font files.

## Shape and space

4px base scale: 4, 8, 12, 16, 22, 30, 34, 72. Card padding 22px, section gap 34px, side gutter never under 16px. Radii: 10 inputs, 12 textareas, 16 cards, pill on every button, chip and tag. One nearly invisible card shadow — this system separates with lines, not depth.

## Rules that matter

- Unknown is a state, not a blank: show every field a record kind can hold, and say *Unknown* in quiet italic where nothing is known.
- One accent per view. If two things are clay, neither reads as the next thing to do.
- State colour never decorates: with nothing overdue, no brick appears anywhere.
- Phone first: one column, two only past 700px.
