## v0.2.4
- **New:** Parameter `fade` for `show` -> `fill` option, makes the fill fade out (#45)
- **Fixed:** History entries with `null` state breaking graph (#46)
- **Fixed:** compatibility issues with the custom swiper-card
- **Fixed:** Broken extrema

## v0.2.3
- **New:** Option `color_thresholds` (#45)
- **New:** Color thresholds now changes dynamically with the history (#45)
- **New:** Options `lower_bound` & `upper_bound` added (#40)
- **New:** Option `color` to entity object, overrides other color options
- **Change:** `entities` option now always requires a list, changed in order to be compatible with "Unused entities" UI (#44) **(BREAKING CHANGE)**
- **Change:** Default value for `points_per_hour` changed from `1` to `0.5`.
- **Fixed:** Updated lit-element to v2.0.1
- **Fixed:** Zero values show up as current value when hovered over (#41)
- **Fixed:** Added additional checks for empty history
- **Removed:** `entity` option, which was previously deprecated since v0.2.0, use `entities` option (#44) **(BREAKING CHANGE)**.
- **Removed:** `line_color_above` and `line_color_below`, see new `color_thresholds` option (#45) **(BREAKING CHANGE)**

## v0.2.2
- **New:** Label design (#35)
- **New:** Entity name now visible in title when graph point is hovered over (#39)
- **New:** `hover` parameter for labels
- **New:** Now rendering missing history as a horizontal line up to the first available history entry (similar to the default history-graph)
- **Change:** Made labels visible on hover by default
- **Change:** Label font size now has a min size and scales relative to the `font_size` option
- **Fixed:** Significantly improved accuracy of graph point values
- **Fixed:** Only fetch history for updated entities, use cache to update rest
- **Fixed:** Graph points not applying threshold color from `line_color_above` / `line_color_below` (#38)
- **Fixed:** Invalid timestamps when combining `points_per_hour` & `hours_to_show` (#37, #36)
- **Fixed:** Misaligned legend text
- **Fixed:** Missing bottom padding when graph is hidden
- **Fixed:** Invisible lines when graph was updated after not covering the full width on load
- **Fixed:** Align timestamps right when `align_state` is set to `right`

## v0.2.1
- **Added:** New `hour24` option to choose time format between 12-hour/24-hour clock
- **Added:** Support for showing multiple sensor states, see new `show_state` option for the entity object (#33)
- **Added:** Ability to press/click on entities in the graph legend to bring up their "more info" dialog (#31)
- **Fixed:** Responsive design of the graph legend
- **Fixed:** NaN values in extrema (#34)
- **Fixed:** Extrema not rendering (#32)
- **Fixed:** Times on points going backwards (#30)

## v0.2.0
- **UI redesign**
- **Added:** support for multiple entities (**BETA**) #28
- **Added:** support for multiple `line_color` entries
- **Added:** graph data points with information on hover, see `points` option under the `show` option
- **Added:** `animate` option to have the graph animated on initial load
- **Added:** `points_per_hour` option to specify amount of data points that should be rendered for each hour (basically the graph detail/accuracy).
- **Added:** support for multiple color thresholds with new `line_color_above` & `line_color_below` options
- **Added:** allocated space for the graph -> less jerky movements when loading in
- **Added:** graph legend, visible if multiple entities is present
- **Added:** `align_header`, `align_icon` & `align_state` options #27
- **Added:** `show` option, to manage visible/hidden UI elements
- **Added:** `entities` option
- **Added:** `group` option to remove paddings/box-shadow #26 (@iantrich)
- **Fixed:** bug were history data would be fetched when graph was hidden
- **Fixed:** `decimals` option not being applied to labels #19
- **Fixed:** Y-scale based on absolute extrema causing inconsistent results, now based on moving average same as the rest of the graph.
- **Deprecated:** `entity` option, use new `entities`, accepts string or list (**deprecated**)
- **Removed:** `detail` option, use new `points_per_hour` option (**Breaking change**)
- **Removed:** `hide` options, use new `show` option (**Breaking change**)
- **Removed:** `labels` option, use `labels` in new `show` option (**Breaking change**)
- **Removed:** `line_value_above`, `line_color_above`, `line_value_below` & `line_color_below` options (**Breaking change**)

## v0.1.0
- Added `hide` option to hide specific UI elements
- Removed `hide_icon`, use new `hide` option (**Breaking change**)
- Minor UI changes
- Fixed issue causing errors if all available history entries had the exact same state
- Updated dependencies

## v0.0.9
- Added `decimals` option to display specified amount of decimals for the current state #18
- Fixed issue where `line_value_above` and `line_value_below` would not work when set to `0` #13

## v0.0.8
- Major rework of the graph calculation, now taking moving average and timestamps into account
- Added bundle version
- Added `detail` option, to specify the detail level of the graph
- Added `labels` option to display min/max labels
- Removed `accuracy` option in favor for `detail`
- Changed the reported size of the card

## v0.0.7
- Improved responsive design
- Fixed overflow issue when stacking several cards in horizontal-stack #11
- Fixed default font-size when not specified in config

## v0.0.6
- Improved handling of unknown/unavailable history entries #8
- Fixed issue where `<path>` error would appear in some scenarios
- Refactored code responsible for building the line graph #9

## v0.0.5
- Added `hide_icon` option #5
- Fixed issue where unknown/unavailable history would make the graph not render #6
- Fixed issue where graph line would rendering outside svg boundary and get clipped
- Made graph line ends rounded
- Adjusted line Y-scale
- Updated to lit-element 0.6.2

## v0.0.4
- Added options to have the line change color if the state is above/below specified values
- Fixed graph when setting accuracy option to a higher value than the available data points in history

## v0.0.3
- Added option `font_size` to modify the font size scale of the state #4
- Fixed `<path> attribute d: Expected number` errors.
- Decreased the default font size slightly #4
- Changed default graph height from 150 to 100;
- Improved compatibility with other custom cards like vertical-card-stack #3

## v0.0.2
- Added option to set hours to show

## v0.0.1
- Initial release
