
# Details

- [ ] Thumbnail
- [ ] Board
- [ ] Pencils
- [ ] Inks
- [ ] Tones
- [ ] Lettering

# Activity

```heatmap-tracker
heatmapTitle: Project Activity
property: log_workedOn
path: Planner/Dailies
filters:
  - property: log_workedOn
    operator: contains
    value: MicroComic - Thinking for Yourself
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
