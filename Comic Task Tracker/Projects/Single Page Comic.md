
# Details

- [ ] Thumbnails
- [ ] Boards
- [ ] Pencils
- [ ] Inks
- [ ] Tones
- [ ] Lettering

# Activity

```heatmap-tracker
heatmapTitle: Project Activity
property: log_workedOn
path: "Daily Notes"
filters:
  - property: log_workedOn
    operator: contains
    value: "Single Page Comic"
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
    - file.folder == "Daily Notes"
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
