# Liber import review: what was in the repo, what was missing, what was changed

Reviewed: `LeonisAstra/30K-4-All` (HEAD `9c511ff`) against Liber Panoptica v5.3,
Liber Centura v1.6, Liber Imperatus v1.2, Liber Ingenium v1.3 and Liber Antiquia v1.6.

## 1. Headline finding

Most of the Liber data **is** in the repo, but a large part of it is not reachable.
Of the 277 units defined in the Liber-derived catalogues, **220 had no `entryLink` anywhere**,
so they could not be added to a roster at all. This, more than missing data, is why the
books looked absent in the app.

| Catalogue | Units defined | Reachable before | Reachable now |
|---|---:|---:|---:|
| Centura Library (generic units, pp.6-60) | 31 | 0 | 31 (in all 18 Legion catalogues) |
| PO - Mechanicum (Ingenium) | 44 | 4 | 44 |
| PO - Solar Auxilia (Imperatus) | 36 | 0 | 35 (Aethon skipped, see below) |
| PO - Imperialis Militia (Imperatus) | 44 | 0 | 44 |
| PO - Questoris Knights (Ingenium) | 3 | 0 | 3 |
| PO - Asuryani (Antiquia) | 57 | 0 | **0 (not done)** |
| PO - Saedath (Antiquia) | 8 | 0 | **0 (not done)** |
| PO - Legio Custodes / Sisters of Silence / Traders Militant | 54 | 53 | 53 (already wired) |

## 2. What I changed (22 catalogue files, all additive, 0 lines removed)

**A. Wired the orphaned units** (follows the existing `[Imperatus] Custodes` pattern):
catalogue link to the library + root `entryLink`s carrying the force-org category
(taken from each unit's own primary category). Possessed Legionnaires and Mutated Spawn
are hidden unless the force is Traitor (the book restricts them).
Hosts: all 18 `2022 - LA - *.cat`, `2022 - Mechanicum.cat`, `2022 - LI - Solar Auxilia.cat`,
`2022 - Imperialis Militia.cat`, `2022 - Questoris Household.cat`.
`Solar Auxilia Aethon Heavy Sentinel Squadron` was skipped because the official free-rules
version already exists in the repo.

**B. Added 28 Legion-specific characters from Centura pp.98-213** to their Legion catalogues,
each with stat line, wargear, weapon profiles, special rules (linked to existing rules where
one exists), once-per-force limits for Unique/0-1 units, and a root link in HQ:
Luther, Merir Astelan | Fabius Bile, Solomon Demeter, Marius Vairosean | Barabas Dantioch,
Volk-Sa'ra'ram, Barban Falk, Warsmith Berossus, Berossus Interred, Warsmith Toramino |
Targutai Yesugei, Shiban Khan | Nassir Amit, Azkaellon | Castrmen Orth, Iron-Father Kardozia,
Lord Crius, Gabriel Santar | Delvarus | Aeonid Thiel | Tarik Torgaddon | Hol Beloth,
Sor Talgron | Artellus Numeon | Nykona Sharrowkyn, Navar Hef | Omegon.

**C. (v3) Added 30 Legion squads and vehicles from Centura pp.101-209**, linked into their
Legion catalogues: Inner Circle Indomitus Squad, Terata Enhanced Warriors, Dominator Tartaros
Cohort, Rhino Castellan (defined only, see below), Ebon Keshig Cataphractii Cohort, Varagyr
Tartaros Terminators, Huscarl Indomitus Terminators, Contekar Cataphractii Terminators,
Sanguinary Guard, Helfather Covenant, Iron Revenants, Triarii Phalanx, Devourers Terminators,
Red-Marked Squad, Deathshroud Cataphractii, Grave Warden Tartaros, Khenetai Isirian Cabal,
Sekhmet Tartaros Cabal, Luperci Squad, Rukal Breacher Squad, Rhetorka Mher Squad, Anointed
Cohort, Infernus Strike-Clade, Ar'Kan Attack Speeder, Firestorm Bombard Squadron, Infernus
Predator Squadron, Raptors (Proto-Astartes and Mutated), Deliverers Tartaros, Darkwing Gunship.
Modelling follows the repo convention: unit cost is the base, the main body model carries the
per-model cost (min = starting size, max = start + "up to N additional"), option groups sit
inside the model entry with max 1 and costed links. Known limits of that convention: "for every
five models" caps and "per model" costs are not enforced by constraints/multipliers. Option
items with no shared entry (about 60) were created as costed name-only entries. Rhino Castellan
is a Dedicated Transport and has no root link; Gendor Skraivok (p.140) was skipped because its
options page has a multi-column layout that needs hand entry. Huscarl-Master Indomitus has no
stat row of its own in the book text, so it shares the Huscarl profile (please check p.136).
Stats and points were spot-checked against the PDF for five squads/vehicles.

**D. (v4) Added Consul upgrades and Rites of War from Centura.**
- 8 Legion Consul upgrades in the shared "Legiones Consularis" group of `2022 - Legiones Astartes.cat`,
  hidden until that Legion is selected: Lord Cypher (DA, +50), Kakophonix Prime (EC Hereticus, +40),
  Priest of Iron (SW, +45), Seraphim Majoris (BA, +45), Lanistus (WE, +35), Alchymus (DG, +35),
  Pyre Guard (Sal, +35), Animatus (AL, +50). Plus 2 generic ones: Terran-Born Crusader (Loyalist,
  +30) and Lodge Master (Traitor, +30). Each carries the page's rules text as an Ability profile and
  the weapon profiles from its table (Xenobane Cannons, Sonic weapons, Helfrost Pistol,
  Conflagration meltas, Hydra's Teeth). Rules and weapon swaps that affect OTHER units (for example
  "upgrade all Heavy Bolters to Xenobane Cannons") are described in the text but not wired as
  automatic option changes.
- 9 Rites of War in the shared "Rites of War" group of `2022 - Horus Heresy.gst`, modelled the same way as
  Panoptica's The Stone Gauntlet (text-only Effects/Limitations, hidden unless the Legion is
  selected): The Iron Without (Loyalist only), Bolt From Blue Skies, The Gates of Hel, The Red Marked,
  Rukal Breacher Battalion (Traitor only), and four unaligned rites: Breacher Spearhead, Destroyer
  Company, Tactica Obliqua, Storm-Lance Tumen (named "(Unaligned)"). Force-organisation effects are
  in the text, not enforced.
- Checked and not needed: 22 of 23 Centura armoury weapons (pp.84-89) already exist in the repo.

**E. (v5) Centura completion pass.**
- Gendor Skraivok (p.140) added to the Night Lords (the page has no options; the earlier skip was a
  text-extraction problem).
- Pater Consularis (pp.74-77): a shared "Pater Consularis" group of 7 costed upgrades (Librarian +50,
  Master of Signals +40, Forge Lord +50, Siege Breaker +55, Chaplain +50, Armistos +30, Herald +40)
  linked into the Contemptor and Castra Ferrum Centurions (one must be chosen).
- Special rules (pp.78-83): the 4 that were missing (Unstable Internment, Volatile Ordnance, Vox
  Override, Whispercutter) added and attached to their units; Battle-Hardened and Master of the Legion
  linked to the existing rules. The other Centura special rules already existed.
- Legiones Wargear (pp.90-93): Legion Saturnine Terminator Armour and the Aspectum-Pattern Occularis
  Array added with their appendix text; Ferromantic Deflector added name-only (the book gives no rules
  text for it anywhere). The rest of the appendix already existed.
- Missing default wargear and option entries restored on the generic Centura units (Contemptor and
  Castra Ferrum Centurions, Cortus Talon, Land Raiders, Sicaran Incinerator, Basilisk, and 47 option
  entries taken from the book's lists with their costs). The Assault Support Squad and both Heavy
  Destroyer Squads were imported with no sizing or options at all and have been rebuilt.
- Additional Wargear Options for existing units (pp.14, 23, 32, 38, 50, 151) added as unit-level
  option groups on 12 official units (Cataphractii/Tartaros Praetor, Castra Ferrum Talon, Terminator
  Indomitus, Spatha Attack Bike, Primaris-Lightning, Tarantula, Deredeo, Achilles, Minotaur, Macharius,
  Medusan Immortal). Not added: Whirlwind "up to two additional" and the Spatha Attack Bike Sergeant
  upgrade (they change unit sizing/model structure).
- Thousand Sons: Psychic Discipline Sinistrum and Geomancy (revealed only for the Thousand Sons),
  Achea Force Stave.
- Iron Hands: Ghola sub-type rule (linked to the three Ghola units), Medusan Zweihander.
- Rites: the 4 "Modifications to Existing Unaligned Rites" (Angel's Wrath, Sky-Hunter Phalanx, Pride of
  the Legion, Fury of the Ancients) added as an extra rule on each existing rite.
- 16 of the 20 placeholder rule texts on the new Legion units now carry the real text (copied from the
  page or from the identical official rule in the repo); two were plain links to existing rules
  (Counter-attack, Battle-Hardened). Four still say "See Liber Centura": Order Exemplars, Deathshroud
  Retinue, Huscarl Retinue and Ferromantic Deflector, because the PDF gives no text for them.
- Centura Library now has only 2 cost-multiplier notes and 25 "in two option lists" merge notices left.

**F. (v6) Liber Panoptica v5.3 pass.** The repo was tagged V5.2; the publication entry in the game system
is now V5.3 (December 2024) and the README reference is updated.
- Weapon profiles (pp.134-142): all 91 PDF profiles were compared with every profile of the same name in
  the repo. 51 were already identical; the 40 that differed (stat or wording changes between 5.2 and 5.3,
  e.g. Adrathic Destructor/Devastor, Demolisher, Macharius Rotary Bolt Cannon, Heavy Chainsword, Krak, Plasma
  Blastgun, Volkite Veuglaire, Charonite Claws, Stormhammer, Hellhammer) were updated in place, both the
  Panoptica Library copies and the official copies of the same weapon, as the document instructs. All
  PDF profiles now match, except Krak Grenades (p.139), which the PDF gives as a melee profile while the
  repo models krak grenades as a wargear rule; left for a maintainer decision.
- Extrinsica Melee Weapons (p.140): the 8 weapons were entirely absent and are now shared entries in the
  Panoptica Library with their class cost (Incipere +20, Calcare +25, Extremis +30). They are not yet
  offered in the Paragon Blade option lists (47 places) and the "one per army" limit is text only.
- Additional Special Rules (pp.126-131): 7 new rules added (Daemonic Hordes, Lords of the Ruinstorm, Rupture (X),
  Sensor Flare, Shattered Legionary, Tank Desant (X), The Black Shield); 3 rules with changed wording updated
  (Artillery Spotters, Inertia Suppression Clamps, Psychic Mastery (X)). Rupture (X) lives in the game system
  and is linked from the 10 weapon entries that use it (the base game cannot see Panoptica Library rules).
- Centurion game mode (pp.54-62): 8 Centurion Rites of War added to the shared Rites of War group; 4 Centurion
  Cohort Doctrines added to the Solar Auxilia Cohort Doctrines group; 4 Mechanicum War-Covenants and 5 Asuryani
  World-Runes added as new shared groups (Mechanicum and Asuryani have no container for them, so they are defined
  but not yet reachable from an army list). All are text-only, like the existing Rites.
- Errata (pp.74-123, 533 entries): only 37 are mechanical (base point costs, characteristic values) and 6 were out of
  date and are fixed: Legion Shadowsword 550, Legion Stormsword 525 and Front 14, Solar Auxilia Shadowsword 525,
  Macrocarid Explorator Move 12; plus the rewording of Born Survivor, Hexagrammatic Wards and Sentry Protocols.
  The rest are free-text clarifications and wording changes that cannot be applied or verified automatically;
  spot checks (Tarantula profile, Castra Ferrum Talon, the super-heavy tanks) showed the repo already carries them.
- Not modelled: Decurion and Praetorian game modes (new force organisation charts, per-model pricing, vehicle bans),
  the Allies Matrix, missions, and the Solar Auxilia Artillery Battery base-cost change (price split across base and
  per-model costs, needs a maintainer check).

Centura items intentionally not wired: the Rhino Castellan (Dedicated Transport, no root link), cross-unit
weapon swaps (Xenobane, Sonic, Shrapnel, Conflagration, Helfrost, Angelus Jump Pack, Magma Plating; the
weapon profiles exist but the "all Heavy Bolters may be upgraded" rules are text only), the Iron
Hands "Keys of Hel" Iron-Father upgrade, the Medusan Zweihander and Achea Force Stave as selectable
options on specific units (profiles exist as shared entries), and the base sizing chart.

Checks run: every file parses as XML; no new duplicate IDs (the repo already has 110
duplicates, unchanged); every new link target exists. **Not tested in BattleScribe /
NewRecruit** (not available here), so please load a roster and click through before merging.

## 3. Still missing from the PDFs

### Centura, Legion section (pp.98-213), units not yet entered
**Superseded in v3:** all of the pages below have since been entered (section 2C) except
Gendor Skraivok (p.140, hand entry needed). The original list is kept for reference. Pages: Inner Circle Indomitus Squad (101), Terata Enhanced
Warriors (108), Dominator Tartaros Cohort (119), Rhino Castellan (120), Ebon Keshig
Cataphractii Cohort (127), Varagyr Tartaros Terminators (133), Huscarl Indomitus
Terminators (136), Gendor Skraivok (140; page has a multi-column options layout),
Contekar Cataphractii Terminators (141), Sanguinary Guard (147), Helfather Covenant (156),
Iron Revenants (157), Triarii Phalanx (162), Devourers Terminators (163), Red-Marked Squad
(168), Deathshroud Cataphractii (173), Grave Warden Tartaros (174), Khenetai Isirian Cabal
(180), Sekhmet Tartaros Cabal (181), Luperci Squad (186), Rukal Breacher Squad (187),
Rhetorka Mher Squad (192), Anointed Cohort (193), Infernus Strike-Clade (198), Ar'Kan Attack
Speeder (199), Firestorm Bombard Squadron (200), Infernus Predator Squadron (201), Raptors
Proto-Astartes (206), Raptors Mutated (207), Deliverers Tartaros Squad (208), Darkwing
Gunship (209).

### Centura, non-unit content
- Legiones Consularis (Consul upgrades): Lord Cypher + Xenobane Cannons (98), Kakophonix
  Prime + Sonic weapons (104), Olympian Shrapnel Weapons (112), Priest of Iron + Helfrost
  Pistol (132), Seraphim Majoris + Angelus Jump Pack (144), Lanistus (160), Alchymus (172),
  Pyre Guard + Conflagration Melta + Magma Plating (196), Animatus (212), plus the generic
  Legiones Consularis / Pater Consularis chapters (pp.70-77).
- Rites of War: The Iron Without (112), Bolt From Blue Skies (124), Gates of Hel (150),
  The Red Marked (166), Rukal Breacher Battalion (184); unaligned Rites pp.64-69.
- Thousand Sons psychic disciplines + Achea Force Stave (178-179), Ghola Sub-type and Medusan
  Zweihander (151), Power Tulwars rules text.
- Appendices: Legiones Special Rules (78), Armoury (84), Wargear (90), and every
  "Additional Wargear Options for Existing ... Units" page (14, 23, 32, 38, 50).
- Six rules on the new characters carry a placeholder description ("See Liber Centura p.N")
  because their text is defined elsewhere: Choir of Screams (Marius), Ferromantic Deflector
  (Berossus Interred), Artisans of War (Azkaellon), The Keys of Hel (Lord Crius), Never Back
  Down (Delvarus), Distrusted By Our Own (Aeonid Thiel). 25 unique wargear items were created
  as name-only entries because no shared weapon profile exists (details in the PDF pages).

### Other books
- **Ingenium:** Septekar Siege-Automata Maniple (p.56) is absent. "Additional options" for
  Questoris Households and the Titan Legions (pp.70-78) not checked line by line.
- **Imperatus:** Aegis Militant Detachments + FOC chart (pp.8-9) and Warrants of Trade (p.10);
  Solar Auxilia Armoured Marshals, additional Cohort Doctrines/Warlord Traits, Provenances of
  War (pp.120-126, 194-199) not confirmed present.
- **Antiquia:** Asuryani (57) and Saedath (8) units exist but are **not wired**: they need a
  new faction (force entry + allegiance entry), which is a design decision. Traders Militant
  is the working template. Aspect Shrines, World-Runes, Runes of the Asuryani, Saedathii
  Detachments and Aeldari Unit Types are not present as rules.
- **Panoptica:** repo is tagged **V5.2**; the PDF is **V5.3** (24 Dec 2024), so v5.3 errata
  and balance changes are not applied. Game modes (Decurion, Centurion incl. Rites of War,
  War-Covenants, Cohort Doctrines, World-Runes; Praetorian) and the errata for Liber
  Mechanicum / Imperium / Militia / Daemons sections (pp.96-122) are not implemented.

## 4. Existing units that are present but partly broken

**Update (placeholder pass):** of the original 983 import warnings, 155 are now fixed and
removed from the comments (**828 remain**): 86 unit-type warnings (Cavalry, Automata, Third-Line,
Super-Heavy, Close-Order, Dreadnought, Transport now get the right category), 20 "Independent
Character" warnings (now the category link), and 49 base-wargear warnings that resolve
unambiguously to an existing entry (Searchlights, Breacher Charge, Haywire Grenade, Melta Bomb,
Servo-Arm, Terminator armours, Mirage Launcher, plus vehicle weapons with a mount prefix, which
keep their mount wording as the link name). Counts of 2+ are only applied where the target is
singular. Composite names ("X or Y", "X (with Y)") and options missing from a choice group were
deliberately left alone because they need cost/rule data from the books. Still open: 388 base
wargear, 272 options inside choice groups, 92 rules, 49 "in two option lists" merges, 7
"multiply by number of models", 7 profiles, 5 types (Battlements, Paragon, Armiger and two
mis-parsed). The list below is the original breakdown; the counts have dropped as above.

The Panoptica-derived files were bulk-converted and contained **983 unresolved import
warnings (`!BSC Errors` comments)** across 581 distinct items. Wiring the units in (section 2A)
makes these visible, so expect some options not to work yet. The most common:
`Could not find type or subtype 'Third-Line'` (25), `'Cavalry'` (22), `rule Independent Character`
(20; it is a category in this system, not a rule), wargear `Searchlight` (13), `Melta Bombs`
(12), `Laspistol or Autopistol` (12), `rule One Use` (10), `Haywire Grenades` (8),
`Breacher Charges` (7). These are mostly one-time shared definitions that, once added,
fix dozens of entries. Per-file counts: Centura Library 81, PO - Asuryani 109, PO - Mechanicum
97, PO - Imperialis Militia 96, PO - Solar Auxilia 87, Panoptica Library 21, Saedath 19.

## 5. Suggested next steps (in value order)
1. Load a roster for one Legion and one army (Mechanicum) and sanity-check the wiring.
2. Resolve the shared placeholders in section 4 (largest effect per edit).
3. Enter the 31 squad/vehicle pages and the Legiones Consularis/Rites of War content.
4. Decide the Aeldari faction structure, then wire Asuryani/Saedath.
5. Rebase Panoptica content from v5.2 to v5.3.

## G. Liber Ingenium v1.3 pass

**Mechanicum "Army Book could not be loaded" (New Recruit): fixed.** Cause: my earlier wiring
added a catalogue link `2022 - Mechanicum` -> `[Ingenium] Mechanicum` while that library already
linked back to `2022 - Mechanicum`. That was the only circular catalogue link in the repo. The
back-link from `PO - Mechanicum.cat` was removed (it used nothing from the army catalogue). There
are now no cycles in the catalogue link graph (`validate_closure.py` checks this).

**What was already right.** All 44 Ingenium units existed; unit statlines (288 values), points
(base + per-model) and squad size caps all match the PDF. 88 of 88 armoury weapon profiles
matched. Most special rules and wargear already existed in `Panoptica Library.cat`.

**What was added or changed.**
- Rules reworded to the PDF: Attack Wing, Datasphere Uplink (protocol list restored),
  Overseer Transport (stray Paired Weapons text removed).
- New group "The Orders of Lesser Techno-Arcana" (Lachrimallion, Macroteknia, Malaghrae, Myrmidae,
  Ruinor, with Machinatus Primus and Mech-Assassin) linked into Magos Prime and Magos Prime on
  Abeyant. New High Techno-Arcana "Skitariiax-Primus" added to the Archmagos group.
- Option lists: 60 missing options added to 40-odd groups, 2 missing groups created, 35 new
  shared wargear/weapon entries (Eradication Beam Cannon, Hydraulic Claw, Arcana Potentis, composite
  mounts such as "Twin-Linked Phosphor Cannon", Stealth Suite Module, Aggression Stim-Injectors,
  Preysight Cogitators, Master-Crafted, Void Shield (1) ...). Costs come from the PDF.
- Character pages (Arkhan Land, Remiare, Koriel Zeth, Kelbor-Hal): unique weapons (Solius Excinda,
  Sapien's Sting, Prenzlaur Null-Pistol, Excoriator, Electroscourge Whip, Ruptor Heraldis,
  Disintegration Beamer, Exiguo Maelifica) and their rules (Master Cybertheurgist, High
  Techno-arcana, Personal Void, Magno-Gravitic Thrusters, Null-Rounds, Warlord: Accursed Scrapcode).
- Default wargear that was missing on a dozen units is now linked.
- "Additional wargear options for existing units": Archmagos/Magos Dominus (+ Abeyant), Arcuitor,
  Vultarax, Tarantula, Thanatar, Krios, Macrocarid Explorator, Ordo Reductor Minotaur.
- `!BSC Errors` in `PO - Mechanicum.cat`: 159 -> about 32 entries still carrying warnings.

**Not done yet (Ingenium).**
- Questoris Crusader Host detachment (force-organisation chart) is not modelled; nor are the
  additional options for Questoris Knights (Armiger Warglaive/Helverin, Questoris, Acheron, Acastus)
  or the Titan Legions units (Warhound/Reaver/Warlord).
- Tech-Priest Auxilia dedicated transport additions; Arcuitor's alternative Hunter-Killer escorts.
- Conditions on "Mechadendrite Hive" for Abeyant variants ("who does not select a Servo-Arm ...")
  are not enforced.
- Ordinatus-Exemplar module-slot system is only cost/text (Hover Nacelles, Four Module Slots).
- Unit warlord traits that point at Liber Mechanicum are not reproduced.
- "Combi-Weapon (Any Type)" on the Oppressor is an empty option (no profile).
- No test in BattleScribe/New Recruit: structural checks only (well-formed XML, ids, link targets,
  no catalogue cycles).

## H. Panoptica errata, second pass (v9)

The first pass only applied 37 hand-picked items. This pass parsed all 533 FAQ/errata entries with a
rule-based reader and compared each unit-sheet instruction to the unit it names.

**Applied (this pass).**
- Point costs: Legion Glaive 575, Fellblade 600, Falchion 625 (were all 650); Macharius squadrons
  (Legion 350 / additional 335, up to 2 additional; Solar Auxilia same); Excindio 300; Ordinatus
  Aktaeus 700; Legion Tarantula 60; Scyllax 100; Solar Auxilia Artillery Battery 100; Invictarus
  Suzerain 200 (+35 each); Castellax-Achea 100; Custodian Venatari 190 (+60 each); Pursuer Cadre 35;
  Militia Reconnaissance 35, Sentinel 40 (+40); Ruinstorm Beasts 70 (+20), Harriers 100.
- Upgrade costs (19): Aethon weapons, Contemptor Kheres Assault Cannon, Lernaean Power Fist and
  Chainfist, Spatha Multi-Melta, Arlatax Arc Scourge, Pursuer Execution Blade, Carnodon sponsons.
- Characteristics (9): Optae A3, Arquitor Front 13, Deathstorm Drop Pod BS4, Tormentor Front 14,
  Ursarax S5, Venatari A3, Lifeward Protector WS5, Culexus WS5.
- Rules added to unit sheets (22): e.g. Outflank, Shattered Legionary, Emperor's Chosen, Field
  Officer, Chosen Warriors, Artillery Spotters, Transport Bay, Lords of the Ruinstorm; Swarm
  replaced by Daemonic Hordes. Rule wording: Blind, Souls of Iron, Ungainly, Implacable.
- Daemons of the Ruinstorm catalogue now links the Panoptica Library (needed for the new rules).

**Already correct in the repo (verified, no change):** 50 of 53 matched unit totals, Legion tank
costs (Stormblade 500 ... Stormsword 525), tank Front 14, Macharius Heavy Support slot,
Tarantula and Artillery Platform statlines, Dedicated-transport-free items.

**Still not applied.** About 200 free-text unit edits ("replace the Dedicated Transport text",
"replace the option to ...", wargear rewrites) and the rule rewrites whose PDF text contains
tracked-change artefacts (Rocket Barrage, Provenances, Grim Purpose). Also not found by name:
Solar Auxilia Stormhammer, Dracosan Armoured Transport, Locutarus per-model cost (+30), Leman Russ
Demolisher Rear 11 (repo has one Leman Russ profile). Duplicate "Ruinstorm Daemon X" stub entries in
the Legion/Militia/Word Bearers catalogues were not repriced.

## I. Errata third pass (v10): everything in the FAQ / errata

The errata PDF marks removed text in red and added text in green, so the final wording of every entry
was read exactly (all 533 entries, about 800 separate instructions). `ERRATA-STATUS.md` lists each
instruction and what happened to it.

Applied in this pass: rule, Rite of War, Provenance, Warlord Trait, Reaction, Psychic Power and wargear
text rewrites (about 110 texts, including FAQ clarifications appended to the rule they clarify);
Dedicated Transport lists rebuilt for 11 units (Proteus/Dreadclaw limited to 5 models, Spartan any
size, etc.); unit sub-types added/removed; default wargear added or swapped; option names and costs;
stat tables (Tarantula, Artillery Platform, Gun Carriage, Cassian Dracos...); rule parameters (Hammer of
Wrath (3), Void Shields (8)); Veletaris and Line Command Section size caps (up to 15 additional).
Core-rule corrections that have no unit sheet in the data are stored as 96 shared rules named
"Errata/FAQ: ...". Items that could not be matched with confidence are listed at the end of
`ERRATA-STATUS.md`.


## J. Panoptica and Centura completion pass (v12)

**Panoptica**
- Panoptica has no wargear section of its own and no unit sheets (its armoury is Special Rules plus
  Weapon Profiles, both already imported; Daemon wargear additions and Sovereign / Arch-Daemon costs verified).
- Game modes that change how a list is built (Decurion Warband chart, per-model Hero/Leader/Trooper
  pricing, Praetorian Toughness-6+ wound budget, Allies Matrix) cannot be expressed in BattleScribe
  force-organisation data. Their full rules are stored as shared rules named "Game Mode: Decurion - ...",
  "Game Mode: Praetorian - ..." and "Allies Matrix (Liber Panoptica)..." in the game system. The Allies
  Matrix chart itself and the Decurion deployment-map diagrams are graphics and are not reproduced.
- Missions (standard, Apocalypse, Zone Mortalis) are not modelled; they are table-top procedure.
- Extrinsica Melee Weapons: the 8 weapons now live in the game system (+20 / +25 / +30 by class) and are
  offered next to every Paragon Blade option (35 sites). Only one Extrinsica weapon may be taken per roster.
- Krak Grenades: the Panoptica melee profile (S6 AP3, Detonation, Unwieldy, Breaching (6+)) added to the wargear entry.
- Mechanicum Centurion War-Covenants are now selectable. Asuryani Centurion World-Runes sit in the
  Antiquia Asuryani catalogue and will be wired when Antiquia is processed.

**Centura**
- Order Exemplars, Deathshroud Retinue, Huscarl Retinue and Ferromantic Deflector appear in Centura v1.6
  only as names in wargear / special-rule lists; the PDF contains no rule text for them, so the
  "See Liber Centura p.X" pointers stay.
- Centura has no errata section of its own; it defers to the Panoptica FAQ / Errata (already applied).
- All 81 Centura unit headings were matched to a repo entry by name.

## K. Armoury of the Age of Darkness audit (v13)

Every row of the Panoptica weapon tables (pp. 134-142, 105 rows incl. ammunition sub-profiles) and all 42
Additional Special Rules (pp. 128-133) were compared against every copy in the repo. Earlier comparison
accepted a match on any one copy; this pass flags any copy that differs. Fixed: Earthshaker Battery/Cannon
(Breaching 5+), Medusa Mortar (Rending 5+), Thunderblast Cannon (+Rupture 5+), Mars-Colossus Bombard (AP3, Shell
Shock, Wrecker), Nemesis Quake Cannon (+Breaching 4+), Nemesis Volcano Cannon (Ignores Cover instead of Sunder),
Proteus Laser Destroyer (Ordnance 2, Exoshock 5+), Talonis HE Missile (AP6, Ignores Cover, Pinning, Shell Shock),
Graviton Crusher (Two-Handed), Rupture (X) rule text (example and Gets Hot note), Pyrithite Spear name typo.
Remaining differences are formatting only (spacing, range dash style). Rule text differences found were
flavour text printed with each rule in the PDF, which is not carried into the data.

## L. v14: errata re-verification, Panoptica library links, Centura check

- Panoptica Library: 11 weapons that carried "Could not find rule" import comments now link the existing
  rules (One Use/One Shot, Graviton Collapse, Concussive). Paired Weapons and The Venem live in the Legion catalogue and cannot be linked from a library. Apocalyptic Blast (10"),
  Apocalyptic Mega-Blast and Harrower have no rule entry anywhere in the data.
- Centura: all 101 unit stat lines in Centura v1.6 match the repo; the Legion Spatha Attack Bike Sergeant upgrade
  (page 40) was missing and has been added; all 12 Centura Rites of War are present.
- Centura Library import notes (duplicate option lists, "multiply by number of models") are BattleScribe
  importer warnings telling a human to merge option lists by hand; they do not affect loading.

## M. v15: the four Centura rule placeholders

- Gems (from the errata introduction): pink = FAQ, yellow = Errata, blue = Balance Change. Errata and Balance Change instructions are applied to the data; FAQ rulings are reference only.
- Apocalyptic Blast / Apocalyptic Mega-Blast are sub-headings of the Blast rule, so weapons now link the Blast rule renamed to "Apocalyptic Blast (10")" / "Apocalyptic Mega-Blast". Harrower still has no rule entry.
- Ferromantic Deflector is the existing core wargear profile; the Centura Library option and Berossus, Interred now link to it instead of carrying a placeholder rule.
- Order Exemplars (Dark Angels): rule text added and the Inner Circle Indomitus Squad now has a required choice of one of the six Orders of the Hekatonystika at no cost.
- Huscarl Retinue / Deathshroud Retinue: the Huscarl Indomitus Terminator Squad is now also offered in the Imperial Fists Retinue group and the Deathshroud Cataphractii Terminator Squad in the Death Guard Retinue group. The rule texts are written from this description of how a Retinue works, not from a book (Centura gives only the rule names). The "only one Huscarl Squad or Huscarl Indomitus Squad" limit is stated in the rule text, not enforced by a constraint.

## N. v16: Iliastus Assault Cannon and Tainted Weapon

- Iliastus Assault Cannon (Balance Change, p.87 of Panoptica): Dreadnought and Vehicle exchanges for a Heavy Flamer now cost +10 per weapon (was +20). Option costs in the data are absolute, so each Iliastus cost was recomputed as (Heavy Flamer cost in that option list) + half of the previous difference, e.g. a single pintle 25 -> 15, a sponson pair 40 -> 20, a hull weapon 20 -> 10. Infantry and Cavalry options already cost +10. Not changed: Blood Angels Contemptor-Incaendius (inbuilt weapon, 15) and the Twin-Linked Heavy Flamer exchange (no unit with a Twin-Linked Heavy Flamer option list was found to attach it to).
- Tainted Weapon: the errata strikes "+10" (red) and adds "+5" (green), so the final cost is +5, which the data already carries.

## O. v17: feedback round (Centura play-test)

- Removed: all Centurion Rites of War / War-Covenants / Cohort Doctrines / World-Runes, and the Incursio Force Organisation Chart (plus the three Traders Militant conditions that referred to it).
- Extrinsica weapons: the 8 weapons had been cloned onto default-equipped Paragon Blade links (Nassir Amit, Abaddon, Loken, Torgaddon, Optae, Ireton Masade, Draykavac, Custodes and others) where they became mandatory. Clones removed from every site where Paragon Blade is default equipment (88 links); they remain only where it is a purchase option.
- Default wargear: 61 Centura wargear entries that were optional tick-boxes (e.g. Kardozia's fists, Santar's Cataphractii armour, Helfather Missile Launchers, Melta Bombs, Chain Axes, Force weapons) are now required (min 1). 
- Iron Hands: added The Keys of Hel (+30, hidden if Ferrus Manus is in the force) under the Iron-Father upgrade, a "Ghola Sub-type (The Keys of Hel)" option (+5 per model) on 15 Legion infantry squads, and moved the Helfather Covenant into the Iron Hands Retinue group (needs Keys of Hel). The Warlord-only restriction on Keys of Hel is stated in the rule text but not enforced.
- Consul upgrades: Legion Indomitus Centurion now offers the full Legiones Consularis list; Legion Saturnine Centurion offers Forge Lord, Siege Breaker and Mortificator only (per Centura p.8).
- Iron Warriors: the Rhino Castellan is now offered as a Dedicated Transport wherever a Legion Rhino is (it was never linked).
- Dedicated Transports: 24 Centura units had no transport option; each now has one built from its datasheet text, with the model-count limits (no more than N / more than N). The Legion Whispercutter transport rule is not modelled.
- Rites of War: Tactica Obliqua now includes the Shifting Tides doctrines and The Iron Without the Olympian Shrapnel Weapons text. All other Centura rites and unaligned-rite modifications were compared with the PDF and match.
- Not reproduced: Centurions showing as 2 models. Every Centura Centurion/Praetor has exactly one model entry in the data; the cause may be in how the app counts, so please tell me which Centurion and where you see "2".

## P. v18: Emperor's Children consul and sonic weapons, Warpfire Cannon

- Kakophonix Prime was only visible for "III: Emperor's Children (Legion Hereticus)"; it is now visible for either Emperor's Children entry with the Traitor Allegiance (as on Centura p.104).
- Sonic Blaster / Sonic Pulveriser / Sonic Decimator are now real weapon entries, offered (hidden until a Kakophonix Prime is in the force) next to every Heavy Bolter (+5), Gravis Bolt Cannon (+10), Gravis Heavy Bolter Battery and Anvilus Autocannon Battery (+10) option. "All weapons in the unit must be exchanged" is not enforced.
- Warpfire Cannon was shown to every Traitor force; it is now Word Bearers only.

## Q. v19: Warlord selection for Centura characters

- The 24 Centura characters whose datasheet has a "Warlord: X" special rule (Nassir Amit, Azkaellon, Luther, Merir Astelan, Fabius Bile, Solomon Demeter, Marius Vairosean, Castrmen Orth, Kardozia, Lord Crius, Gabriel Santar, Barabas Dantioch, Volk-Sa'ra'ram, Barban Falk, Warsmith Toramino, Nykona Sharrowkyn, Navar Hef, Artellus Numeon, Tarik Torgaddon, Aeonid Thiel, Targutai Yesugei, Shiban Khan, Hol Beloth, Sor Talgron) now carry the shared "Warlord" option, with their own Warlord rule attached to it (same pattern as Sevatar, Loken etc.), so the trait applies when they are chosen as Warlord and no other trait group is offered.
- Warlord option added (no named trait) to the Indomitus Praetor, Indomitus / Saturnine / Contemptor / Castra Ferrum Centurions, Gendor Skraivok, Delvarus and both Berossus entries.
- Trailing PDF page numbers and a stray weapon table fragment were removed from the Warlord rule texts.

## R. v20: full Liber Centura audit

Method: every datasheet (87) had its Wargear and Special Rules compared with what is applied by default in the data; every option line in the PDF (659 option lines, generic and legion-specific) was compared by name and points cost; unit starting totals (90 units) were compared with the printed points.
Fixes: 32 "exchange X for ..." option lists inside model entries now default to X (Combi-Bolter, Power Weapon, Bolt Pistol, Chainsword, Bolter, ...) so the base weapon is applied unless exchanged; Power Armour added as default to Assault Veterans, Hussars and Sky-Seekers; Early Great Crusade Havoc Squad pricing corrected (base 40, Havoc Master 30, up to 2 Masters); Legion Mastodon pintle weapons (up to two) and Flare Shield (+50); Vindicator Thunderer extra shell types; Legion Vexilla for Javelin and Proteus Land Speeder squadrons; Targutai Yesugei Shamshir Jetbike (+30, entry name was corrupted); Sekhmet Inceptor psychic discipline (+25); Wind Rider Melta Bombs (+5); Land Raider Dionysus Warlord (Fist of the Legion).
Result: all totals match the PDF; remaining unmatched lines are PDF layout artefacts or entries that exist under a different name.

## S. v21: Lord Cypher

- Lord Cypher now carries two Bolt Pistols (each independently exchangeable for Volkite Serpenta +2, Hand Flamer +2, Plasma Pistol +5, Inferno Pistol +5, Archaeotech Pistol +10, Disintegrator Pistol +15) and a Calibanite Warblade by default; only one per army.
- The Xenobane Cannon weapons were showing on the Lord Cypher himself. They are now real weapon options on every Dark Angels unit that has a Heavy Bolter (+2), Twin-Linked Heavy Bolter (+2), Gravis Bolt Cannon (+5) or Gravis Heavy Bolter Battery (+5), shown whenever a Dark Angels force is selected (the page does not require a Lord Cypher). "Exchange all in the unit" is not enforced.

## T. v74: Liber Ingenium second pass

- Option groups: merged "may take a / any of / either or both / select any of" groups were split or re-capped (Augury Scanner, Nuncio-Vox, Omnispex and Enhanced Data-Tether are now separate one-of-each groups; Alpha melee and pistol choices are separate groups; Magos Prime has separate Laspistol and Power Weapon exchange groups). 8 extra Sisterhood weapons that are not in the PDF were removed. "Exchange X for" groups now default to X, "must select" groups are min 1 / max 1, and "any of" groups no longer cap at one.
- Oppressor: Baneblade Cannon is the default turret weapon (the Co-axial Autocannon is hidden when it is exchanged), the sponson options must be the same choice (the Laser Destroyer pair is its own entry), and Void Shields are a separate group from the pintle weapons.
- Ordinatus-Exemplar: motive, primary, secondary and auxiliary groups corrected (module slots shown in the option names). Ordinatus-Minoris: hull (rear) Volkite Culverin and the Ordinatus Dispersion Shield added.
- Skitarii Decimator: Corpus Skitarii on both models, Volkite Charger / Frag Grenades on the Alpha, Relentless and Support Squad, and the squad-wide weapon swap is priced per model (Alpha included) and replaces the Volkite Charger.
- Rules: Surveillance Protocols (Herax), Thanatar Maniple (Thanatar-Cynis), Marksman Teams (Liquidator, Vectorii Team), Void Shields (2) (Kaban), Broad-Spectrum Data-Tether (Onager), "Two Prenzlaur Null-Pistols" naming.
- Dedicated Transports: Kill-Clade (Dunerider up to 5, Triaros up to 10), Vanguard and Ranger (Dunerider up to 10, Triaros up to 20), Decimator and Electro-Priest (Dunerider up to 10, Triaros any), Sisterhood (Dunerider or Porphetian). Tech-Priest Auxilia gained the Dunerider (any size) and Porphetian (up to 8).
- Warlord: the 7 Ingenium characters and Kelbor-Hal can be your Warlord; the 3 Legiones Skitarii Warlord Traits are offered to the Skitarii Centurius and Sicarian Clademaster instead of the generic list.
- Questoris Knights: Moirax weapon slots are two separate exchange groups, Dominus arm weapons are exactly two, and its three Siegebreaker Cannons are real (reduced when exchanged).
- Questoris Crusader Host Detachment (PDF p.70) added as a force organisation chart in 2022 - Questoris Household.cat: 1+ Lords of War (up to 10), up to two Troops per Lord of War, no 25% Lords of War limit. The Allied Detachment uses the existing Allied Detachment chart; "primary only" is not enforced.
- Additional wargear for existing Questoris Household and Titan Legions units (PDF pp.74-78) added: Searchlights on every Armiger/Knight, Warglaive and Helverin weapon replacements, Questoris Laser Lance / Breacher Maul / Draconis Glaive / Dual Vulcanis Blades, Porphyrion Carronades / Arkadia Array, and the Warhound, Reaver and Warlord Titan weapon swaps. The Ingenium weapons these need were moved from Panoptica Library into Mech Library (same ids).
- Moirax Talon (Ingenium) reuses the official Greuso Protocol, Armiger and Moirax Talons, Armiger Unit-Type and Stubborn; the 0-3 limit is a force-scope max on the Household entryLink.
- Exemplar module slots: hidden gst cost type "Module Slots" on the nine slot-using option links (Hover 1, Strato-Cannon 1, Culverin 1, Mauler 1, Lascannon 2, Self-Repair 1, Reactor 2, Superstructure 2, Cascade 2) with a max 4 constraint on the unit.
- Crusader Host is primary-only: it hides when Crusade, Mortalis, Household, Aegis Militant or Titan Maniple is in the roster, and those charts hide once it is added. LoW and Allied detachments are unaffected. The "no other chart" restriction on its units is not enforced.
