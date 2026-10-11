# Intro

This is how I track comic work in my Obsidian! Absorb the [Templater](https://community.obsidian.md/plugins/templater-obsidian) templates into the templates of your vault, and the `log_workedOn` list property into the Daily Notes of your vault.

Then, you can make your own comic projects and track them.

# Plugins

## Required

- Daily Notes (Core)
	- How the Heatmap and Calendar trackers see which days you worked on a comic, through a `log_workedOn` list property linking to that comic's project file.
- [Templater](https://community.obsidian.md/plugins/templater-obsidian)
	- Needed to generate both the Base checklist and the Heatmap Tracker relevant to your specific comic project.

## Used, but not Necessary

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

- [TaskNotes](https://community.obsidian.md/plugins/tasknotes)
	- In my real version, each comic is a TaskNote. TaskNotes is a great Obsidian task manager.
- [Tasks](https://community.obsidian.md/plugins/obsidian-tasks-plugin)
	- I use these for subtask-checklists that I don't need to be managed to the same degree as a TaskNote. Typically because I don't need it to have any YAML properties.

# Usage

1. Put the templates in your templates folder. Tell Templater where that is, if you haven't.
2. If you're making a one-page comic, make a new note and name it after your comic.
3. If you're making a multipage comic, make a new folder named after your comic, with a note inside sharing the folder's name.
	1. Or, use [Folder Notes](https://community.obsidian.md/plugins/folder-notes) to do that automatically.
4. In your note, run Templater's `insert template` modal and choose:
	- `task onepage comic` for the tracker file of a one-page comic,
	- `task multipage comic` for the main tracker file of a multiple-page comic,
		- `task comic page` for an individual pages within a multiple-page comic folder.
5. For days you worked on your comic, open the corresponding Daily Note and insert a wiki-link to the comic's project note into your `log_workedOn` property, which should be in list format.