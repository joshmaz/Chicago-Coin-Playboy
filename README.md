This WAV Trigger configuration is being composed for:

1947 Chicago Coin Play Boy pinball machine
Music theme should be upbeat jazzy 40's big-band

Configuration v1.5

Physical switch mapping (16 avail):

On-board test button - Always track 001
01 - New game (Reset bar) - Random music track
02 - New game alternate* - Random alternate track
03 - Kickout holes - Play random kickout track
04 - Kickout holes altnerate*
05 - Rollovers - Play random rollover track
06 - Rollovers alternate*
07 - Tilt relay - Play random tilt track, non-polyphonic
08 - Tilt relay alternate*, non-polyphonic

09 - Information button - Play informational voice track
10 - Quiet button - Stop music tracks
11 - 1K score relay
12 - 10K score relay
13-16 - Undefined

# WAV Trigger Configuration - 1947 Chicago Coin Play Boy

## Overview
Configuration for a 1947 Chicago Coin Play Boy pinball machine with 1940s big-band jazz theme.
Version 1.5

## Physical Switch Mapping (16 available)

| Switch | Function | Description |
|--------|----------|-------------|
| Test Button | Track 001 | On-board test button |
| 01 | New game | Reset bar - Random music track |
| 02 | New game alt* | Random alternate track |
| 03 | Kickout holes | Random kickout track |
| 04 | Kickout holes alt* | Alternate kickout track |
| 05 | Rollovers | Random rollover track | 
| 06 | Rollovers alt* | Alternate rollover track |
| 07 | Tilt relay | Random tilt track (non-polyphonic) |
| 08 | Tilt relay alt* | Non-polyphonic alternate |
| 09 | Info button | Play informational voice track |
| 10 | Quiet button | Stop music tracks |
| 11 | 1K score relay | Score tracking |
| 12 | 10K score relay | Score tracking |
| 13-16 | Undefined | Reserved for future use |

## Notes & Considerations

### Toggle Configuration
- Pair of 2PDT toggles create primary/alternate versions of music and sounds
- Primary/alternate New game triggers are non-polyphonic (one song at a time)
- Primary/alternate Tilt triggers are non-polyphonic (all tracks halt on tilt)

### Active interfaces

Made lots of progress using optocouplers and a custom cicuit to signal the WAV Trigger.
The signal line is usually high and is pulled low when the opto closes.
Triggers for these acelectronic interfaces I'm using:

- Active interface
- Edge trigger
- Invert cleared (trigger high to low)
- Re-trigger cleared (to help with de-bouncing)

### Future Ideas
- Extend Quiet button to include informational tracks
- Consider removing sample sounds from final product
- Implement three-position DPDT for bell settings:
  - Mechanical bell on
  - No bell (off)
  - Digital bell on
- Use optocoupler for game timer status monitoring
  - Play power up on game state
  - Play power down on inverted state

## WAV File Naming Convention

| Track Range | Purpose |
|-------------|---------|
| 001 | Self-test / welcome track |
| 009 | Information track |
| 011 | Small score wheel |
| 012 | Large score wheel |
| 020-029 | Primary kickout sounds |
| 030-039 | Alternate kickout sounds |
| 040-049 | Primary rollover sounds |
| 050-059 | Alternate rollover sounds |
| 060-069 | Primary tilt sounds |
| 070-079 | Alternate tilt sounds |
| 100-199 | Primary music tracks |
| 200-299 | Alternate music tracks |
| 001-018 | Sample files (for troubleshooting) |

## Current WAV Trigger Configuration


Considerations and ideas:
Make the Quiet button include the informational tracks
Consider purging the sample sounds from the final product
Use a three-position DPDT for bell settings... mechanical bell on, no bell (off), digital bell on
Use an optocoupler to gain visibility to the game timer's status. 
Game state opto-coupler - Play power up, Game state opto-coupler inverted - Play power down sound

Note*: 
A pair of 2PDT toggles are used to create primary and alternate versions of music and sounds.
The pri/alt New game (start music) triggers are non-polyphonic so that only one song at a time is playing. 
The pri/alt Tilt triggers are non-polyphonic so that all tracks halt when a tilt occurs.

WAV file naming guide:

001 - Self-test / welcome track (i.e. 001_Digital_Sounds_Loaded.wav)
009 - Information track
011 - Score wheel, small
012 - Score wheel, large
020-029 - Kickout hole sounds (Primary)
030-039 - Kickout hole sounds (Alternate)
040-049 - Rollover lane sounds (Primary)
050-059 - Rollover lane sounds (Alternate)
060-069 - Tilt relay sounds (Primary)
070-079 - Tilt relay sounds (Alternate)
100-199 - Music tracks (Primary)
200-299 - Music tracks (Alternate)
001-018 - Corresponding numbers (sample files, left for troubleshooting undefined triggers)


The last wavtrigr.ini file I copied into this file:
--
#TRIG 01, 1, 0, 1, 1, 0, 4, -10, 101, 199
#TRIG 02, 1, 0, 1, 1, 0, 4, -10, 201, 299
#TRIG 03, 2, 0, 1, 0, 1, 4, 0, 21, 29
#TRIG 04, 2, 0, 1, 0, 1, 4, 0, 31, 39
#TRIG 05, 2, 0, 1, 0, 1, 4, 0, 41, 44
#TRIG 06, 2, 0, 1, 0, 1, 4, 0, 51, 53
#TRIG 07, 1, 0, 1, 0, 0, 4, 0, 61, 66
#TRIG 08, 1, 0, 1, 0, 0, 4, 0, 71, 73
#TRIG 09, 1, 0, 1, 0, 1, 1, 0, ,
#TRIG 10, 1, 1, 1, 0, 0, 7, 0, 100, 299
#TRIG 11, 1, 0, 1, 1, 1, 1, 0, ,
#TRIG 12, 1, 0, 1, 1, 1, 1, 0, ,
******************************************************************
This file was generated by the Robertsonics Configurator v2.20
for use with the WAV Trigger firmware. It is only required if
you wish to over-ride default settings. You may add your own
comments below this line -->
Config 1.7