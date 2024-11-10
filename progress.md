TODO: make this a nice task tracker

# Core logic
- recipient, minister, and ceremony seem to be done
- next is basic building blocks for faculties section
- after that, show/hide logic for various pieces; after that, logic to generate instructions for user, register output, warnings/errors about inconsistent info, etc

# Styling
- add 'unknown' option to the yes/no choices: this will keep the relevant info boxes visible for print mode
    - eg: user doesn't know before meeting whether or not person has been baptised
    - as an extra here: add logic for printed version that gives instructions like 'if yes, cross out section B'
- use `hide-print` and `hide-web` classes instead of messing with `display` in the JS
    - reason: some things are visible in one mode but not the other
    - conveniently, this will also automatically restore the correct `block`, `inline`, etc
    - set up a helper function to do this
- printing of `select`s
    - one idea: replace with checkboxes or radio buttons
    - another idea: use JS to generate an `ul` with the same options that only shows when printing
        - unless user has chosen yes or no, in which case we need only print that option
        - and can omit 'unknown' option from print version, since that's really only useful for the show/hide code of the web version

# Desired extensions

# Optional extras

# Public domain
This file is released to the public domain and is marked with [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).
