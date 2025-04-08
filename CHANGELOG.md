# WAV Trigger Configuration Changelog

## [1.9] - 2025-04-08

### Changed
- Updated trigger 10 (Shhh) to stop the full range of files (1-4096), reset edge trigger and cleared invertion to match current physical switch.
- Fought with a bug in the WTConfig software in where the UI was displaying extra text (a pair of '500's) in the ini file view. Worked through updating each trigger back to the ini file until the extra data was at the top, then manually removed the extra lines and resaved the file.

### Added
- New Presentation markdown file for speaking to an overview of the project.

## [1.8] - 2025-04-05

### Changed
- Updated triggers 7 & 8 (Tilt) to use Active 3.3V/5V interface type
- Cleared invert flag on triggers 7 & 8
- Extended track ranges for triggers 7 & 8 to include full scopes
- Extended track ranges for triggers 5 & 6 (Rollovers) to include full scopes
- Updated triggers 1 & 2 (Music) to use lock-voice functionality
- Updated configuration documentation to reflect changes and improved understanding of .ini file data encoding
- Converted changelog file from text to markdown format

## [1.7] - 2025-04-04

### Changed
- Reset trigger 7 (tilt primary) to clear Polyphonic setting
- Confirmed trigger 8 (tilt secondary) was correctly non-polyphonic
- Cleared re-trigger from triggers 7 & 8 to address potential bouncing issues
- Adjusted music track (triggers 1 & 2) volumes from -7 dB to -10 dB for better balance
- Removed erroneous -15 dB volume from config file header
- Reset system volume to 0 dB

### Added
- Added WAV Trigger Configuration markdown document

## [1.6] - 2025-04-01

### Changed
- Disabled re-trigger on kickout and rollover triggers (3, 4, 5, 6) to address bouncing on solenoid monitor circuit
- Extended file ranges for triggers 1, 2, 3, 4 to full scope instead of just populated files

## [1.5] - 2025-03-19

### Changed
- Updated triggers 3, 4 (kickouts) and 5, 6 (rollovers) to use Active hardware interface
- Cleared invert flag on triggers 3, 4, 5, 6 to accommodate optocoupler prototype
- Extended trigger 2 (alt music tracks) range to be inclusive from 201-299 