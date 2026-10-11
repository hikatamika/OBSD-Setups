---
tags: []
timeCreated: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ssZ") %>
timeModified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ssZ") %>
connections:
---
# Details

- [ ] Thumbnails
- [ ] Boards
- [ ] Pencils
- [ ] Inks
- [ ] Tones
- [ ] Lettering

# Activity

<%*
const dailyNotes = "YOUR/DAILY/NOTES/PATH"
const noteTitle = tp.file.title;
const currentYear = tp.date.now("YYYY");

tR += `\`\`\`heatmap-tracker
heatmapTitle: Project Activity
property: log_workedOn
path: "${dailyNotes}"
filters:
  - property: log_workedOn
    operator: contains
    value: "${noteTitle}"
year: ${currentYear}
separateMonths: true
showCurrentDayBorder: true
disableFileCreation: true
colorScheme:
  paletteName: default
intensityConfig:
  scaleStart: 0
  scaleEnd: 1
\`\`\``;
%>

<%*
tR += `\`\`\`base
filters:
  and:
    - file.folder == "${dailyNotes}"
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

\`\`\``;
%>
