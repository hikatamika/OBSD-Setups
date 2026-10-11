---
tags: []
timeCreated: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ssZ") %>
timeModified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ssZ") %>
connections:
---
# Details

<%*
const thisFolder = tp.file.folder(true);

tR += `\`\`\`base
summaries:
  Completed: ((values.filter(value == true).length / values.length) * 100) + "%"
filters:
  and:
    - file.folder == "${thisFolder}"
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

\`\`\``;
%>

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
