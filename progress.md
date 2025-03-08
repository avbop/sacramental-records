# Core logic
- [x] layout of information (mostly HTML)
    - [x] recipient section
    - [x] minister section
    - [x] ceremony section
    - [x] faculties section
    - [x] output (registers and notification) section
- [x] processing of information (mostly JS)
    - [x] show/hide display pieces based on input
        - [x] complete `hide-print` and `hide-web` setup described below first
        - possible restructuring:
            - tag elements with something like `data-ifbaptised`, `data-iftobaptise`, `data-ifpriorfullcommunion`, `data-ifadopted`, etc
            - in code, calculate which sacraments are to be administered, which past conditions apply, etc, and set true/false booleans corresponding to the `data-if*` conditions
            - then, show/hide based on `data-if*` and the calculated booleans
            - probably still a few edge cases that need to be handled manually, especially where the order matters or more than one condition needs to be considered
    - [x] show/hide registers and notification instructions
    - [x] show/hide sponsor fields
- [x] `orthodox` baptism should ignore a later change to `protestant` when considering ascription (per forum opinion)

# Styling
- [ ] add 'unknown' option to the yes/no choices, and treat 'unknown' as 'display the relevant item'
    - this will keep the relevant info boxes visible for print mode
    - eg: user doesn't know before meeting whether or not person has been baptised
- [x] use `hide-print` and `hide-web` classes instead of messing with `display` in the JS
    - reason: some things are visible in one mode but not the other
    - conveniently, this will also automatically restore the correct `block`, `inline`, etc
    - set up a helper function to do this
    - when needed, select with `.hide #elementid` for particular cases that depend on print v web
- [ ] figure out display of `select`s in print mode
    - one idea: replace with checkboxes or radio buttons
    - another idea: use JS to generate an `ul` with the same options that only shows when printing
        - unless user has chosen yes or no, in which case we need only print that option
        - and can omit 'unknown' option from print version, since that's really only useful for the show/hide code of the web version
- [x] make sure links and buttons are suitably displayed in print mode

# Release considerations
- [x] set up hosting on github.io
    - <https://avbop.github.io/sacramental-records/>
- [x] some clear way of indicating beta/draft until it's in reasonably good shape
- [ ] error checking
    1. [ ] forum
    2. [ ] a few priests in parishes

# Desired extensions
- [ ] well-designed borders, colours, etc
    - should probably be different for print v web
    - [ ] choose a font better suited to the web (Charter has strange baseline spacing)
- [ ] citations to canon law
    - [ ] set up code for a suitable footnote or margin note system
    - [ ] insert the citations
    - [ ] write explanatory notes about interpretation of the law where appropriate
- [ ] instructions only for printed version
    - eg: 'If yes, cross out section B.'
- [ ] floating, clickable table of contents
    - this might be unnecessary if each section has a useful background color

# Low-priority possible modifications
- [ ] page(s) with brief descriptions of non-initiation sacraments that are recorded
    - or not recorded, for confession
- [ ] page(s) about recording a funeral
    - probably a brief description rather than a full form, since the law doesn't indicate anything in particular
- [ ] notes about places that are commonly modified by particular law
- [ ] formatting for mobile
- [ ] `<select>` for options for ascription
    - see <https://www.catholic-hierarchy.org/rite/>
- [ ] show warnings/errors about inconsistent information
- [ ] provide some means of save and restore
    - must be client-side only: if the user wants to move it to another computer, he must do so himself and thereby take responsibility for data privacy
    - include warnings about data privacy (eg don't save on public machines)
    - probably a query URL that is parsed client-side: this could be easily bookmarked or copy/pasted
    - maybe: localStorage, indexedDB, or the like (but this is probably too invisible/confusing for most users, and wouldn't easily transfer eg from laptop to office desktop)
- [ ] partial and/or asynchronous data parsing and UI updates
    - standard of urgency: if there's no visible delay in updating the form, this remains low priority

# Public domain
This file is released to the public domain and is marked with [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).
