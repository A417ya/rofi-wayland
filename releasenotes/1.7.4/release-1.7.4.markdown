# 1.7.4:

Another maintenance and small features expansion release. A lot of small
annoyances have been fixed and ignored errors are now more visually flagged to
the user. In the past typos in the theme could result into broken themes
without any warning to the user, if an unknown link is found it will now throw
an error. Also to help the user, manpages are further split up into sub-pages
and are expanded

A massif speedup has been implemented in the async input reading of dmenu.
It turned out glib's GInputStream async functions where very slow, so a custom
implementation has been made. Background loading is now close to the same speed
as loading at start before displaying. A million item list is now near instant.
On very large lists, the instant filtering automatically changes to be
postponed until the user stops typing. This severely reduces system load.

On the new feature front, you can now change the flow in the listview from
vertical first to horizontal first. Making it mimic tables.

{screenshot  vertical }  { screenshot horizontal }

You can now set a fallback icon individual for each mode.

You can now add a separate icon or textbox widget to the UI that displays the
current selected item.

In dmenu mode (and script) you can now make (some) changes to the theme, for
example modifying the background color of the entry box.

You can now put users scripts (for script mode) into
`$XDG_CONFIG_HOME/rofi/scripts` directory and those are automatically available
in rofi.


Below is a more complete list of changes:

# Changelog

* [Script] Add keep-selection flag that keeps the current selection. (#1064)
* [Debug]  Add '-log' flag to redirect debug output to a file.
* [XCB]    Try to deduce rotated monitors.
* [Doc]    Add rofi-dmenu to 'See also' in rofi(1).
* [Options] Mark offset(s) as deprecated.
* [Modes] Support loading multiple icon sizes.
* [View]  Add textbox|icon-current-entry widget.
* [Doc]   Add ascii manpage to rofi-script(5).
* [Script] Print user-scripts in -h
* [Script] Look into $XDG_CONFIG_HOME/rofi/scripts/ for user scripts.
* [Dmenu|Script] Allow (some) theme modification from script/dmenu.
* [Textbox] Fix some pango alignment.
* [FileBrowser] Bind 'kb-accept-custom-alt' to directory up.
* [Build] Add desktop files as per complaint (rofi theme selector and rofi itself).
* [Dmenu] Code cleanups.
* [Themes] Remove broken themes.
* [Modes] Allow fallback icon per mode. (#1633)
* [View] Fix broken anchoring behaviour. (#1630)
* [Rofi] Move error message on commandline to UI.
* [Listview] Option to hide listview elements when not filtered. (#1622,#1079)
* [DMenu] Speed up reading async in of large files from stdin.
* [FileBrowser] Make accept-alt open folder if selected.
* [Helper] Add XDG_DATA_DIRS to the theme search path. (#1619)
* [Doc] Split up manpages and extend them with examples.
* [Doc] Highlight use of `-dump-config` in config. (#1609)
* [Config] Workaround for in data type passed to string option.
* [Listview] Allow flow of elements to be set. (#1058)
* [Script] Add data field that gets passed to next execution. (#1601)
* Change modi to modes to avoid confusion.
* [Theme] When links are unresolvable throw an error to the user.
* [DMenu] Document the `display-columns` and `display-column-separator` option.

# Thanks

Big thanks to everybody reporting issues.
Special thanks goes to:

* Iggy
* Morgane Glidic
* Danny Colin

Apologies if I mistyped or missed anybody.
