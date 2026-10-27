# SaySay

Say it, then say it back. A calm shadowing app for more than one language, starting with Chinese and Spanish. Each sentence plays twice, then waits while you say it out loud. When you can say it easily, you tap Got it and it moves to Learned. SaySay is built on the same foundations as Shuo and Stay Counter, with its own terracotta accent.

## Principles

1. **One language, one sentence at a time.** The screen holds the sentence you are saying now, in the language you chose. The list, settings and forms wait in sheets.
2. **Eyes on the words, thumb on Play.** The sentence card is always the same height, so Play, previous, next and Got it never move. You can tap them without looking.
3. **Terracotta acts, everything else is quiet.** Terracotta is for Play, Got it, pinyin, the language pill and what you are on. Ink, muted and the warm white carry the rest.
4. **Nothing is lost.** Got it moves a sentence, it does not delete it. Undo stays for a few seconds. Only delete removes sentences, and it always asks first. Each language keeps its own sentences and progress.
5. **One way to do each thing.** Top left always closes a sheet, the bottom holds the one forward action.

## Color

| Role | Tokens | Use |
| --- | --- | --- |
| Action | `primary`, `accent-text`, `soft` | Play, Add, Got it, pinyin, the language pill, the status pill, the selected segment |
| Current | `current` | The sentence you are on in the list, the chosen language |
| Ground | `bg`, `surface`, `line` | Screens, cards, dividers |
| Text | `ink`, `muted` | Sentences, translations, labels and notes |
| Quiet | `chip`, `chevron` | Round buttons, the disabled previous button and quiet icons |
| Attention | `warn-text` | Delete sentence and Delete all sentences |
| Overlay | `backdrop` | Behind sheets |

Rules
- `primary` is a fill. Terracotta text always uses `accent-text`.
- Sentences are always `ink`, never terracotta. Terracotta is for what you hear and do, the sentence is what you read.
- `warn-text` is a true red, so delete never looks like a normal terracotta action.
- Text passes 4.5 to 1 everywhere it sits. The token notes list each pair.

## Typography

Outfit for Spanish and everything in Latin letters, Noto Serif SC for Chinese sentences, and Quicksand only for the name and the icon.

Five text styles like iOS, plus one style per language for the sentence. The same scale runs across SaySay, Shuo, Stay Counter and Manna.

| Style | Size | Weight | For |
| --- | --- | --- | --- |
| `sentence` | 40, 56 on laptop | Semibold serif | A Chinese sentence on the card |
| Spanish sentence | 34, 44 on laptop | Semibold Outfit | A Spanish sentence on the card |
| `section` | 20 | Semibold | Section headers, like Language and Playback. 32 above, 12 below |
| `title` | 17 | Semibold | Buttons, sheet titles |
| `body` | 17 | Regular | Pinyin, translations, labels, settings. Like iOS body text |
| `small` | 13 | Regular | The count, notes, field labels, the second line in lists |
| `list-han` | 17 | Semibold serif | Chinese in a list row. Spanish rows use Outfit |
| Name | 20 | Quicksand 700 | SaySay at the top left |

Text inputs use 17, so iOS does not zoom.

Rules
- Every sentence starts at the same height in its card, so your eye finds it in one place. Long sentences step down in size instead of growing the card. Chinese counts characters, Spanish counts letters.
- Translations into Chinese use Noto Sans SC, translations into Korean use the system Korean font.
- Large Latin text uses minus 0.02em letter spacing.

## Layout

- Phones use a 22 side margin on every screen and sheet.
- Pinch zoom always works. Buttons ignore double tap zoom so taps stay quick.
- The colour behind the page is `bg`, the same as the top of the screen, so the home screen app shows no fade under the time.
- One column everywhere. On laptops the column grows to 600 and sits in the vertical middle of the screen.
- On devices with a keyboard and mouse, a quiet hint under Got it shows the shortcuts.
- The main screen, top to bottom, is the title row, the sentence card, the play row, Got it and one note.
- Cards are white with a 1px `line` border and `radius-card`. No shadows.

## Languages

- First open asks one question, what do you want to practice. Nothing is chosen until you tap, then Start.
- The language pill next to the name shows what you are practicing, like 中文 or Español. Tapping it opens Language, the same list as first open.
- Each language keeps its own sentences, learned list and place.
- Chinese shows pinyin under the characters. Spanish shows only the sentence and its translation.
- Translate into offers English, 中文 and 한국어, without the language you are practicing. It starts on the phone's language and each language remembers its own choice.
- Spanish from offers Latin America and Spain, and only shows for Spanish. Latin America is the default. It picks a voice from that region.
- Starter sentences carry all three translations, so changing Translate into updates them. Your own sentences keep the translation they were saved with.

## Navigation

- No tabs. The main screen is the app.
- Three round buttons at the top right. + opens New sentence, then Sentences and Settings.
- Every round button is the same flat grey circle. `chip`, 44 wide, a 20 icon with a 2 line in `ink`. A disabled button keeps its circle and only fades its icon to `chevron`.
- Destructive actions always go last. A single one is plain red text, centered. Two or more related ones are grouped in one card. They always ask first.
- Sheets have one rule. Top left leaves. × closes a first screen, ‹ goes back one step. The bottom holds one forward action, like Add sentence or Add. Settings has no bottom button, changes save as you tap.
- Settings starts with Language, then Playback with Listen, Speed, Time to repeat and Voice, then Backup, About and the sentence actions for the current language.
- On laptops sheets open in the middle over a dimmed page.

## Practice

- Play reads each sentence as many times as chosen in Listen, once, twice or 3 times, then pauses for the time chosen in Settings, then moves on. Twice is the default. It stops at the end of the list.
- The pill on the card says where you are. While listening it shows one dot per listen, filled for done and pulsing for now, then Your turn in solid terracotta. With Once there are no dots.
- Previous and next keep playing if Play was on.
- Got it moves the sentence to Learned and shows a toast with Undo for 4 seconds.
- SaySay opens on the language and sentence you were on last time.
- On a keyboard, Space plays or pauses, the left and right arrows move, Enter is Got it, and Escape closes a sheet. Keys do nothing while you type, while a sheet is open or on first open.

## Sentences

- The Sentences sheet has two tabs, Practice and Learned, each with its count. Chinese rows show pinyin, Spanish rows show the translation.
- Add a sentence with + on the main screen or Add sentence in the Sentences sheet. New sentences go to the top of Practice.
- The form follows the language. Chinese has Chinese, Pinyin and the translation. Spanish has Spanish and the translation.
- Pinyin fills in on the phone as you type. The translation comes from the free MyMemory service a moment later. Both stay editable, and once you type in a field yourself SaySay stops filling it.
- Edit on the card, or the pencil on a row, opens Edit sentence with Save, and Delete sentence below.
- Settings has Start over and Delete all sentences for the current language. Each says how many it affects, and both ask first.

## Backup

- Sentences live only in the browser, so Settings has a Backup section with Export sentences and Import sentences, and a note to export now and then.
- Export saves one file, like saysay-2026-10-27.json, with every language, Practice and Learned, translations and the language you were practicing. Speed, voice and other playback settings stay on the device. On phones it opens the share sheet, elsewhere it downloads.
- Import never changes anything until you confirm. It shows the file name and date, then one row per language with how many are in the file and how many are new. The button says what will happen, like Add 44 sentences.
- Import adds, it never removes. Sentences you already have are skipped, learned ones stay learned. A file that is not a SaySay backup gets a calm toast and nothing changes.
- First open has a quiet Have a backup? Import it link under Start. After importing it opens on the language the backup was practicing.
- A backup restores every language at once, because it is mostly used after something went wrong.

## Icon

- Two S letters in Quicksand 700, one faded and one solid, like a voice and its echo. Say, then say back.
- White on `primary`, a full square. Phones round the corners themselves.
- The letters are traced as shapes and centred by their own edges, not by the font baseline, so they sit in the true middle.
- `icon.svg` is the source. The PNG sizes are made from it.

## Writing

- Plain words, sentence case, short. No colons, semicolons or dashes in UI text.
- Talk about the person's action, like Got it, Your turn, Practice again.
- Language names appear in their own language in the pill and pickers, like 中文, Español and 한국어.
- Calm words for problems, with what to try next. When no voice is found, Settings explains which browsers work best instead of showing an error.

## Files

`tokens.json` holds every colour, type style, spacing, radius and size. `tokens.css` is made from it and the app loads it, so the app and this book never drift. Each folder in `components` has a guide and a live preview. Run `node scripts/build-design-system.mjs` after changing anything here to rebuild `tokens.css` and the page at `/saysay/design-system/`.
