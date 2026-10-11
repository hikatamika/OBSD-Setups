# Intro

Heyo, this is the basic version of my art tracker base. It helps me track on which days I did, and didn't draw.

Try and absorb it and its templates into the Daily Notes and template files of your actual vault!

This art tracker looks to see if the `habit_drewToday` checkbox property of a daily note is checked, and if there are any images in `habit_todaysArt` to display.

# Thumbnails

There are 3 filler thumbnails that appear when you haven't filled the `habit_todaysArt` property for a given day with the wiki-link to an image.

Customize them to your liking, or, in the [[Art Tracker.base|Art Tracker]], change the filetype to .PNG if you don't end up using .WEBPs for yours. 

| Thumbnail        | Situation                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| todaysArtGo.webp | There's a daily note for today's art, but you haven't drawn anything yet! Go draw something! /lh |
| todaysArtMissing | You have checked `habit_drewToday`, but have not filled `habit_todaysArt` with any images.       |
| todaysArtMissed  | The day of this daily note has passed, and you have not checked `habit_habitDrewToday`.          |


# Plugins
## Necessary Plugins

- Daily Notes (Core Plugin)

## Nice Plugins

- [Templater](https://community.obsidian.md/plugins/templater-obsidian)
	- A more powerful way to give your Daily Notes a template, with fields that can be customized with like… math and variables and JavaScript.
- [Image Converter](https://community.obsidian.md/plugins/image-converter)
	- I use these to make thumbnails of my art that are small in dimension, and filesize (WEBP).
- [Meta-Bind](https://community.obsidian.md/plugins/obsidian-meta-bind-plugin)
	- Interact with the properties at the top of your note with elegant UI elements like text fields and buttons.
- [Formula Forge](https://community.obsidian.md/plugins/formula-forge)
	- Unlike Meta-Bind, which I can only get to display images as absolute links, Formula Forge allows me to display them as wikilinks, so I like that.
- [Front-Matter Timestamps](https://community.obsidian.md/plugins/front-matter-timestamps)
	- I automatically date my notes with this one.