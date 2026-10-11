# Intro

This is how I track comic work in my Obsidian! Copy the [Templater](https://community.obsidian.md/plugins/templater-obsidian) templates into your vault's template folder, and the `log_workedOn` list property into the Daily Notes of your vault.

Then, you can make your own comic projects and track them.

# Plugins

## Required

These plugins are required for the core workflow!

- Daily Notes (Core)
	- How the Heatmap and Calendar trackers see which days you worked on a comic, through a `log_workedOn` list property linking to that comic's project file.
- [Templater](https://community.obsidian.md/plugins/templater-obsidian)
	- Needed to generate both the Base checklist and the Heatmap Tracker specific to your specific comic project.

## Used, but not Necessary

These ones improve functionality and visualizations.

- [Folder Notes](https://community.obsidian.md/plugins/folder-notes)
	- I make each Multi-Page comic a folder note. In other words, a note with the same name as its parent folder. This makes the folder operate much like Notion or Scrivener.
	- The base that shows you what parts of the comic process you've finished for each page is within an .MD with the same name as its parent folder, that looks for *all other files in that folder* that ***aren't*** itself.
- [Heatmap Tracker](https://community.obsidian.md/plugins/heatmap-tracker)
	- Displays the "did I work on this comic today" *heatmap*.
		- This one requires [Dataview](https://community.obsidian.md/plugins/dataview) to run.
- [Calendar Bases](https://community.obsidian.md/plugins/calendar-bases)
	- Displays the "did I work on this comic today" _calendar_.
	- Soon, Obsidian will have an official Bases Calendar View and this won't be needed.

## I Use These in My Personal Version, but not in This Demo

These ones are for productivity and streamlining.

- [TaskNotes](https://community.obsidian.md/plugins/tasknotes)
	- In my real version, each comic is a TaskNote. TaskNotes is a great Obsidian task manager.
- [Tasks](https://community.obsidian.md/plugins/obsidian-tasks-plugin)
	- I use these for subtask-checklists that I don't need to be managed to the same degree as a TaskNote. Typically because I don't need it to have any YAML properties.
- [Meta-Bind](https://community.obsidian.md/plugins/obsidian-meta-bind-plugin)
	- I use it for a more elegant insert into the `log_workedOn` property, like so:

````MetaBind
```meta-bind
INPUT[list:log_workedOn]
```
`````

# Usage

> [!warning]
> Ensure _**YOUR**_ obsidian considers `log_workedOn`, or whatever you want to call this property, a `list` property instead of a `text` property, or else the Obsidian calendar base (if you choose to use it) will fail to parse it later.

## Project Tracking

1. Put the templates in your templates folder. Tell Templater where that is, if you haven't.
2. If you're making a one-page comic, make a new note and name it after your comic.
3. If you're making a multipage comic, make a new folder named after your comic, with a note inside sharing the folder's name.
	- Or, use [Folder Notes](https://community.obsidian.md/plugins/folder-notes) to do that automatically.
	- Multi-page comic projects should look like the following:

```
My Comic/
├── My Comic.md
├── Page 1.md
├── Page 2.md
└── Page 3.md
```

4. In your note, run Templater's `insert template` modal (via the command palette, or the ribbon icon, or a shortcut, or…) and choose:
	- `task onepage comic` for the project tracker file of a one-page comic,
	- `task multipage comic` for the main project tracker file of a multiple-page comic,
		- `task comic page` for individual pages within a multiple-page comic folder. The multiple-page-comic project tracker file will read from these.
	- When running `task onepage comic` or `task multipage comic`, an activity heatmap and calendar are generated specifically to that project, within the project's note.

## Daily Notes

1. Add a property called `log_workedOn` to your Daily Note and ensure it's a **list** property type before continuing.
2. For days you worked on your comic, open the corresponding Daily Note and insert a wiki-link to the comic's project note into your `log_workedOn` property, which should be in list format.
3. If the Calendar Base gives you an error, make sure your `log_workedOn` looks like the following when viewed in source mode:

```yaml
---
log_workedOn:
- "[[Multi Page Comic]]"
- "[[Single Page Comic]]"
---
```
