---
title: Xcode 13 Vim Mode
date: 2021-06-10T18:17:33.217Z
description: Xcode 13 (beta) introduced new Vim mode that simulates native Vim
  functionality and keybindings. It's a good start but some crucial features are
  still missing. Apple also added a nice visual twist to their implementation.
---
# Xcode 13 Vim Mode

## How to Turn it on

Enabling the functionality is **fairly simple** and there is no need to restart or otherwise tweak Xcode.

The mode can be enabled by going to `Settings -> Text Editing -> Editing (tab) -> Enable Vim key bindings.` When that's done, there is an immediate visual feedback telling the user that the Vim mode is active.

![Vim status line in Xcode](img/screenshot-2021-06-10-at-19.10.11.png "Vim Status Line in Xcode")

## What Works

So far only the most basic functionality has been implemented. It could be summarised into the following list:

* yank `y`, delete `d`, change `c`, delete char `x`, insert commands `i`, `a`, `o`
* visual, insert and normal modes
* basic movements and motions
* search (along with `n`, `N` and `*`)
* undo/redo functionality

The list is quite short but I believe that motions along with the editor's modality make Vim distinctive the most.

## What's Missing

Unfortunately the short list of available features above is pretty much it because a lot of useful stuff that makes editing in Vim more awesome is missing.

### Visual Line `⇧ + v` and Visual Block `⌃ + v` Modes

Visual line mode is just a matter of convenience because you can achieve the same in visual mode, your positioning just has to be more precise. That couldn't be said about visual block mode because some operations just cannot be done easily without it.

One could argue that Xcode already provides the block functionality so there is a workaround that can be used in the insert mode. But I think that it misses the point of using a modal editor in the first place.

### Auto Indent `=`

The binding doesn't work which is quite a shame because it could be added with a simple hotkey remap (the indent command already exists, just not in vim mode). Moreover the `<<` and `>>` indent commands work as expected so it's even weirder that the main indent command is missing.

### Command-line Mode `:`

I understand this limitation because it would probably be difficult to implement the entire power of this mode although I would really like to see at least the bare basics like writing a file, because most of vim users have a (bad?) habit of writing the file after almost every change!

### Others

I've also found those features to be missing:

* replacing single characters with `r`
* repeat operation command `.`
* marks (setting and navigating)

Of course there's probably more that I've missed through my limited knowledge of advanced Vim features.

## Visual Feedback

Apple introduced a form of visual feedback that becomes active after enabling the Vim keybindings. It indicates which mode is currently active along with color coding for different commands (yellow for yank, red for delete, blue for visual). This is mostly the equivalent to a classic Vim status line but it doesn't end there!

The awesome part is that it tells you what command you began without looking at the status bar because the current line is highlighted with the color that corresponds to the mode/command. Furthermore, it lists the available "followups" in the status line.

This is a great feature for someone who wants to try Vim but might feel overwhelmed by the amount of hotkeys one has to remember to do basic editing and movement.

![Visual Feedback on Vim Command](img/screenshot-2021-06-10-at-19.22.01.png "Visual Feedback after Beginning a Vim Command")

## Final Thoughts

Using **Vim** along with Xcode in a seamless way was a dream of mine for a long time. **XVim** filled that void for a while but after Apple made using third party plugins more difficult, I've stopped using it in a work environment where I do most of my programming.

So far I remain *a little disappointed* because I would probably still rather use editing without **Vim** rather than what Apple introduced in the current beta version (I'll try to make it work though!). That said, I remain optimistic that the list of features and keybindings is going to steadily grow and one day becomes powerful enough to be used comfortably by people that are already familiar with vim.

On the brighter side, Apple capitalised on their ability to create **beautiful user interfaces** and introduced a nice form of visual feedback that will allow **new users** to try **Vim** without the experience of spending an unreasonable amount of time trying to quit the editor.