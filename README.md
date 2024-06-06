30K-4-All: A Horus Heresy + Panoptica Repository
============

[![Latest release](https://img.shields.io/github/release/LeonisAstra/30K-4-All.svg?style=flat-square)](https://github.com/LeonisAstra/30K-4-All/releases/latest)
[![Commits (since latest release)](https://img.shields.io/github/commits-since/LeonisAstra/30K-4-All/latest.svg?style=flat-square)](https://github.com/LeonisAstra/30K-4-All/releases)
[![Open bugs](https://img.shields.io/github/issues/LeonisAstra/30K-4-All/bug.svg?style=flat-square&label=bugs)](https://github.com/LeonisAstra/30K-4-All/issues?q=is%3Aissue+is%3Aopen+label%3Abug)


[![Chat on Discord](https://img.shields.io/discord/558412685981777922.svg?logo=discord&style=popout-square)](https://www.bsdata.net/discord)
[![Contributors](https://img.shields.io/github/contributors/LeonisAstra/30K-4-All.svg?style=flat-square)](https://github.com/LeonisAstra/30K-4-All/graphs/contributors)
[![Commit activity the past year](https://img.shields.io/github/commit-activity/y/LeonisAstra/30K-4-All.svg?style=flat-square)](https://github.com/LeonisAstra/30K-4-All/pulse/monthly)



## Overview ##

### What's this?

This is an independent BSData repository for the Horus Heresy with the inclusion of errata/rebalances/expansions provided by the [Panoptica Team's Fan-Made Publications](https://hh-ageofdarkness.itch.io/). It can be used with [BattleScribe](https://battlescribe.net/), [NewRecruit](https://www.newrecruit.eu/), and [BlueScribe](https://bluewinds.github.io/bluescribe/). Support for [Rosterizer](https://rosterizer.com/) is planned.

We strongly recommend you use NewRecruit over Battlescribe, as Battlescribe is considered abandonware.

**Please note, this is a Work in Progress.**

### How Do I Install It?

To install this repository and allow it to update whenever there is a new release, please include the following BSI file in the relevant location on your app of choice.

[https://github.com/LeonisAstra/30K-4-All/releases/latest/download/30K-4-All.latest.bsi](https://github.com/LeonisAstra/30K-4-All/releases/latest/download/30K-4-All.latest.bsi)

### Current Inclusions

As of the latest release, we have implemented:
- Errata & Balance Changes to all Core Rules
- Errata & Balance Changes to Liber Astartes Units & Related Special Rules
- All Additional Special Rules (pages 146-150)
- All Panoptica Weapon Profiles (pages 152-157)

### *I found a bug!* / *I have another request*

Great, thank you! Please [Report a bug][bug report] - you can also suggest enhancements and raise other issues there.

## Release Schedule ##

We are working towards quickly adapting all of the rules included within Liber Panoptica. Following this, our attention will focus on importing Liber Centura, then Liber Imperatus, and finally Liber Ignenium. After these core books are included, we will begin work on Liber Antiquia and future expansions.

When there is a major release of the BSData Horus Heresy repository, we will switch focus on rebasing this repository via their upstream changes.

## Thanks & Disclosures ##

This repository is a fork of the [BSData/horus-heresy](https://github.com/BSData/horus-heresy). This project would not be possible without the herclean effort put forward by this dedicated volunteer team. If you are interested in joining their team at their [Discord Community](https://www.bsdata.net/discord)

We'd also like to thank the Panoptica Team for all of their continued hard-work in providing the community a fantastic set of expansions; all of which have been playtested extensively by their international collaboration. 

We are not affiliated with the Panoptica Team nor their related [Discord Community](https://discord.gg/HH-Age-of-Darkness) in any way. This project was spurred on by an growing and immediate need for local community EOs and players to be able to utalize the fantastic additions made to the core system in a simple and quick manner. As such, please direct any commentary regarding the rules set via the above linked Discord Community. The group creating the ruleset have a deep passion for making this community better! ^_^

## Legal Notice

Liber Panoptica and related publications are shared under the provisions of the CC BY-NC-ND 4.0 Licence, more information on which can be [found here].

This ruleset is entirely community-made, unofficial, and not for profit. It is not to be sold, distributed for profit, or otherwise restricted in any way. It is shared entirely out of love for The Horus Heresy game system and our desire to for it to continue. Infringement on any legal rights is not intended. Some words, terms, and logos in this document are copyrighted – these are used in compliance with copyright laws and procedures, including this notice.


-------------------------------------
-------------------------------------


## BSData Standards

### Creating units
#### Names
In general, we remove the "Legion" prefix from units, unless that unit has a non-legion equivalent such as Legion Baneblade

We create a unit entry for each unit, and a model entry within that unit (even if it's a single model unit).
This allows us to get an accurate model count and keeps everything consistent.

On UNITS we default them to hidden and add a modifier with constraint to set "Hidden to False" if "Equal to 1 selection in force of <> on". Ensure "And all child selections is checked".
On UPGRADES, we default the option to not hidden, and set "Hidden to True" if the "off" condition is selected.

#### Important reminders:
These are requirements on a unit to maintain rites of war:
- Solar Auxillia and Imperialis Militia units need "SA or IM Unit" for rites of war that count that number of units.
- - Lords of war should be excluded from this as they won't be in the "allied detachment"

### .cattemplate? and what are all the template_id_ comments?
A .cattemplate file is a .cat file, renamed to .cattemplate, used by [BSCOPY](https://github.com/nstephenh/BSCopy)

We used bscopy to copy all 18 legions after implementing the first one. 
We didn't maintain the template so it's not recommended to re-run bscopy

## References

* Horus Heresy: Age of Darkness Rulebook
* Liber Astartes
* Liber Hereticus
* "Both Astartes Army books" refers to the first section of both of the above books, as they are identical
* Liber Mechanicum
* [Legacies of The Age of Darkness Legions v1.1 PDF](https://www.warhammer-community.com/wp-content/uploads/2022/09/RZRGS5ADYjwUb7Ry.pdf)
* [Legacies of The Age of Darkness: Mechanicum v1.0 PDF](https://www.warhammer-community.com/wp-content/uploads/2022/09/WJKYil2FehoZxrD9.pdf)
* [Exemplary Battles of Age of Darkness: Unit Update v1.1 PDF](https://www.warhammer-community.com/wp-content/uploads/2022/09/n10JM7pGRr4EyfIh.pdf)
* [Exemplary Battles - The Scouring of Gildens Star PDF](https://www.warhammer-community.com/wp-content/uploads/2022/06/TLbrp4me5GEfL37Q.pdf)
* [Exemplary Battles in the Age of Darkness: The Battle of Trisolian: Vengeful Spirit](https://www.warhammer-community.com/wp-content/uploads/2022/07/6i9CeSwKmbWmzac4.pdf])
* [Exemplary Battles in the Age of Darkness: The Axandrai IV Incident](https://www.warhammer-community.com/wp-content/uploads/2022/09/3mVvZrTG9XOWeVxv.pdf) 
* [Ka'bandha Rules](https://www.warhammer-community.com/wp-content/uploads/2022/07/4uwEurgnIRQCzWHE.pdf)
* Zone Mortalis (White Dwarf 477)
* [Warhammer: The Horus Heresy – Age of Darkness Rulebook Errata and FAQ V1.0](https://www.warhammer-community.com/wp-content/uploads/2022/09/7AX0peoK6m7C7uzw.pdf)
* [Liber Astartes Errata and FAQ V1.0](https://www.warhammer-community.com/wp-content/uploads/2022/09/yq5znaB0N5sLyARr.pdf)
* [Liber Hereticus Errata and FAQ V1.0](https://www.warhammer-community.com/wp-content/uploads/2022/09/3s4WA1UGgC15iDp2.pdf)
* [Liber Mechanicum Errata and FAQ V1.0](https://www.warhammer-community.com/wp-content/uploads/2022/09/RQ0Pcrm0LJB5BwSG.pdf)
* [Liber Panoptica v5.2](https://hh-ageofdarkness.itch.io/liberpanoptica)

## Links ##

* [BSData organization homepage][BSData.net]

[BSData.net]: https://www.bsdata.net/
[bug report]: https://github.com/LeonisAstra/30K-4-All/issues/new/choose
