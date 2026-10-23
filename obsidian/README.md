# Anti-Gravity // Obsidian

Neo-cyberpunk theme for Obsidian. Wide display headings, chamfered plates, mono labels, one highlight colour. Light (Bone) and dark (Void) modes.

## Usage
### Install
1. Download and extract the zip to `<vault>/.obsidian/themes/`, so that the themes folder contains the `Anti-Gravity` folder.
2. Settings → Appearance → Themes → select **Anti-Gravity**.

### Fonts
Embedded in `theme.css`. No install, no network fetch, works on mobile and through sync.

- Michroma: headings
- Chakra Petch (500, 600, 700, plus italics): interface and body
- Share Tech Mono: code and labels

Subset to Latin, Latin-1, punctuation, arrows and geometric shapes. All three are SIL Open Font Licence 1.1; see `OFL.txt`.

### Highlight
Install the **Style Settings** community plugin to switch highlight, glow, chamfers and heading case.

| Name   | Void      | Bone      |
| ------ | --------- | --------- |
| Signal | `#FF2A3D` | `#E0102A` |
| Neon   | `#FF3FA4` | `#DE0075` |
| Jensen | `#FA5C00` | `#C64900` |
| 2077   | `#F5CC00` | `#727272` |
| Hack   | `#39FF14` | `#158400` |
| Gibson | `#00D9FF` | `#007D93` |

A CSS snippet works too. Add a `.css` file to `.obsidian/snippets/` and enable it:

```css
body { --ag-accent-dark: #00D9FF; --ag-accent-light: #009EB9; --ag-accent-deep: #007D93; }
```

### Colour highlights
Obsidian 1.14+ colours a highlight from the emoji at its start. Each maps to an Anti-Gravity colour; plain `==text==` keeps the active highlight. Text on a highlight is always dark, so every colour uses its brightest (Void) shade in both modes.

| Write         | Colour                      |
| ------------- | --------------------------- |
| `==🔴 text==` | Signal                      |
| `==🟠 text==` | Jensen                      |
| `==🟡 text==` | 2077                        |
| `==🟢 text==` | Hack                        |
| `==🔵 text==` | Gibson                      |
| `==🟣 text==` | Neon                        |

### Text, Hazard tape, alerts and brackets

| Write this           | You get                                                              |
| -------------------- | -------------------------------------------------------------------- |
| `**Bold**`           | **Bold**                                                             |
| `_italic_`           | _italic_                                                             |
| `~~strikethrough~~`  | ~~strikethrough~~                                                    |
| `==Highlight==`      | ==Highlight==                                                        |
| `---`                | Flat 2px rule                                                        |
| `> [!hazard]`        | Hazard tape strip (`> [hazard\|thick]` for a heavier band)           |
| `> [!warning] Title` | Alert box: hazard edge in the tone colour, display title, tone glyph |
| `> [!frame]`         | Corner brackets, no title bar                                        |
| `> [!frame\|accent]` | Corner brackets in the highlight colour                              |
|                      |                                                                      |

Alert tones: `tip` `success` `done` → OK (✓). `warning` `caution` → Warn (!). `question` `faq` → Warn (?). `danger` `error` `bug` `failure` → Danger (✕). `note` `todo` → highlight. `info` `abstract` `summary` → neutral (i). `example` → cyan. `quote` and `cite` stay calm: no hazard edge.

Style Settings options: **Classic callouts** (plain bracket bar instead of the hazard edge) and **Hazard tape rules** (turns every `---` into tape).

## PDF export

Exports use the dark Void palette, even though Obsidian normally forces light output.

- In the export dialog, set **Margin** to **None**. The theme adds its own gutter on every page; any other margin leaves a white border.
- For paper, turn on **Light PDF export** in Style Settings.

## Notes

- Code blocks stay Void in both modes. Deliberate.
