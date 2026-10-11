
# Details

```base
summaries:
  Completed: ((values.filter(value == true).length / values.length) * 100) + "%"
filters:
  and:
    - file.folder == "Projects/Multi Page Comic"
    - file.path != this
properties:
  note.comic_thumb:
    displayName: Thumbnails
  note.comic_board:
    displayName: Storyboards
  note.comic_pencil:
    displayName: Pencils
  note.comic_ink:
    displayName: Inks
  note.comic_tone:
    displayName: Tones
  note.comic_letter:
    displayName: Letters
views:
  - type: table
    name: View
    order:
      - file.name
      - comic_thumb
      - comic_board
      - comic_pencil
      - comic_ink
      - comic_tone
      - comic_letter
    sort: []
    summaries:
      comic_thumb: Completed
      comic_board: Completed
      comic_pencil: Completed
      comic_ink: Completed
      comic_tone: Completed
      comic_letter: Completed

```

# Activity

```heatmap-tracker
heatmapTitle: Project Activity
property: log_workedOn
path: Planner/Dailies
filters:
  - property: log_workedOn
    operator: contains
    value: Multi Page Comic
year: 2026
separateMonths: true
showCurrentDayBorder: true
disableFileCreation: true
colorScheme:
  paletteName: default
intensityConfig:
  scaleStart: 0
  scaleEnd: 1
```

```base
filters:
  and:
    - file.folder == "Planner/Dailies"
    - file.properties.log_workedOn.contains(this.file)
formulas:
  dailyNote: date(file.name)
views:
  - type: calendar
    name: Calendar
    order:
      - file.name
      - formula.dailyNote
    startDate: formula.dailyNote

```
