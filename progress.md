# Core logic
- [ ] layout of information (mostly HTML)
    - [x] recipient section
    - [x] minister section
    - [x] ceremony section
    - [ ] faculties section
    - [ ] output (registers and notification) section
- [ ] processing of information (mostly JS)
    - [ ] show/hide display pieces based on input
        - [ ] complete `hide-print` and `hide-web` setup described below first
    - [ ] generate registers and notification instructions
    - [ ] show warnings/errors about inconsistent information

# Styling
- [ ] add 'unknown' option to the yes/no choices: this will keep the relevant info boxes visible for print mode
    - eg: user doesn't know before meeting whether or not person has been baptised
- [ ] use `hide-print` and `hide-web` classes instead of messing with `display` in the JS
    - reason: some things are visible in one mode but not the other
    - conveniently, this will also automatically restore the correct `block`, `inline`, etc
    - set up a helper function to do this
- [ ] figure out display of `select`s in print mode
    - one idea: replace with checkboxes or radio buttons
    - another idea: use JS to generate an `ul` with the same options that only shows when printing
        - unless user has chosen yes or no, in which case we need only print that option
        - and can omit 'unknown' option from print version, since that's really only useful for the show/hide code of the web version
- [ ] make sure links and buttons are suitably displayed in print mode

# Release considerations
- [ ] set up hosting on github.io
- [ ] some clear way of indicating beta/draft until it's in reasonably good shape
- [ ] error checking
    1. [ ] forum
    2. [ ] a few priests in parishes

# Desired extensions
- [ ] well-designed borders, colours, etc
    - should probably be different for print v web
- [ ] citations to canon law
    - [ ] set up code for a suitable footnote or margin note system
    - [ ] insert the citations
    - [ ] write explanatory notes about interpretation of the law where appropriate

# Optional extras
- [ ] instructions only for printed version
    - eg: 'If yes, cross out section B.'
- [ ] page(s) with brief descriptions of non-initiation sacraments that are recorded
    - or not recorded, for confession
- [ ] page(s) about recording a funeral
    - probably a brief description rather than a full form, since the law doesn't indicate anything in particular
- [ ] notes about places that are commonly modified by particular law

# Public domain
This file is released to the public domain and is marked with [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).
