Training alias that allows players to train in various proficiencies. Allows for customization of training settings. This does take into account Fey Wanderer Ranger's ability to add their wisdom modifier to charisma ability checks. You can also manage what proficiencies players can learn and what ability score is used for each.

This does require cvar `subclass` to contain `Fey Wanderer`, otherwise the bonus will need to be manually done.

## Settings
- [Settings](#settings)
    - [Settings Dictionary Variable](#settings-dictionary-variable)
    - [Tool Settings Dictionary](#tool-settings-dictionary)
    - [Language Settings Dictionary](#language-settings-dictionary)
    - [Weapon Settings Dictionary](#weapon-settings-dictionary)
    - [Instrument Settings Dictionary](#instrument-settings-dictionary)
    - [Gaming Set Settings Dictionary](#gaming-set-settings-dictionary)
    - [Skill Settings Dictionary (README)](#skill-settings-dictionary-readme)
    - [Armor Settings Dictionary (README)](#armor-settings-dictionary-readme)
- [License Notice](#license-notice)
- [Requests](#requests)
- [Ko-fi](#ko-fi)

### Settings Dictionary Variable
The `training_settings` server variable uses a json to customize the settings with training. This is not required, instead it will use default values. Here are the following settings:

- max_val: Integer that sets the max number of successes necessary - relevant ability score (i.e. 10 - CharismaMod (+3) = 7 successes) Default: 10

- disp_type: Shows what kind of counter type is shown, here are the following options:
  - None
  - "bubble"
  - "square"
  - "hex"
  - "star" (default)

- jack_of_trades: Says whether or not Jack of All Trades is used in the ability check.
  - 1: True (default)
  - 0: False

- thresholds: Determines how many successes you get based upon what you roll. By default, any roll below 10 constitutes as 0 successes, 10-19 is 1 success, and 20+ is 2 successes.
  - {"-999": 0, "10": 1, "20": 2}

- time_cooldown: Determines how often someone can train in seconds. By default, the cooldown is 65000 seconds (6.5 days).

[Example Dictionary](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/settings.json)


### Tool Settings Dictionary
This server variable uses a json to determine what tool proficiencies can be learned and what ability scores are used for each. Within the `tool_dict` svar, any tools left out of the svar will become tools that players are not allowed to learn through the training alias.

If you do not have the `tool_dict` svar created, it will default to the below settings:

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/tools.json)

|                         | Strength | Dexterity | Intelligence | Wisdom | Charisma |
|:-----------------------:|:--------:|:---------:|:------------:|:------:|:--------:|
|   Alchemist's Supplies  |          |           |       X      |    X   |          |
|    Brewer's Supplies    |          |           |       X      |    X   |     X    |
| Calligrapher's Supplies |          |     X     |       X      |        |     X    |
|    Carpenter's Tools    |     X    |     X     |       X      |    X   |          |
|     Cobbler's Tools     |     X    |     X     |       X      |    X   |     X    |
|       Cook's Tools      |          |     X     |       X      |    X   |          |
|   Glassblower's Tools   |          |     X     |       X      |        |          |
|     Jeweler's Tools     |          |     X     |       X      |        |     X    |
|  Leatherworker's Tools  |     X    |     X     |              |    X   |          |
|      Mason's Tools      |     X    |           |       X      |        |          |
|    Painter's Supplies   |          |     X     |              |    X   |     X    |
|      Potter's Tools     |          |     X     |              |    X   |          |
|      Thieves' Tools     |          |     X     |       X      |        |          |
|      Tinker's Tools     |          |     X     |       X      |        |          |
|      Weaver's Tools     |          |     X     |       X      |    X   |          |
|    Woodcarver's Tools    |          |     X     |       X      |    X   |          |
|      Smith's Tools      |     X    |     X     |              |        |          |

### Language Settings Dictionary
This server variable uses a json to determine what languages can be learned and what ability scores are used for each. Within the `lang_dict` svar, any languages left out of the svar will become languages that players are not allowed to learn through the training alias.

If you do not have the `lang_dict` svar created, it will default to the below settings:

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/languages.json)

|                      | Intelligence | Wisdom | Charisma |
|:--------------------:|:------------:|:------:|:--------:|
|        loxodan       |       X      |    X   |     X    |
|       aarakocra      |       X      |    X   |     X    |
|         artuk        |       X      |    X   |     X    |
|      abanasinian     |       X      |    X   |     X    |
|        abyssal       |       X      |    X   |     X    |
|       angulotl       |       X      |    X   |     X    |
|      ankeshelian     |       X      |    X   |     X    |
|         aquan        |       X      |    X   |     X    |
|         auran        |       X      |    X   |     X    |
|       birdfolk       |       X      |    X   |     X    |
|     black speech     |       X      |    X   |     X    |
|       blink dog      |       X      |    X   |     X    |
|        bothii        |       X      |    X   |     X    |
|       bullywug       |       X      |    X   |     X    |
|       celestial      |       X      |    X   |     X    |
|        cervan        |       X      |    X   |     X    |
|       citlanes       |       X      |    X   |     X    |
| common sign language |       X      |    X   |     X    |
|        daelkyr       |       X      |    X   |     X    |
|        dalish        |       X      |    X   |     X    |
|       darakhul       |       X      |    X   |     X    |
|      deep speech     |       X      |    X   |     X    |
|       demodand       |       X      |    X   |     X    |
|         derro        |       X      |    X   |     X    |
|       djaynaian      |       X      |    X   |     X    |
|        dohwar        |       X      |    X   |     X    |
|       draconic       |       X      |    X   |     X    |
|        druidic       |       X      |    X   |     X    |
|       dwarvish       |       X      |    X   |     X    |
|        elvish        |       X      |    X   |     X    |
|         eonic        |       X      |    X   |     X    |
|         ergot        |       X      |    X   |     X    |
|         erina        |       X      |    X   |     X    |
|    feather speech    |       X      |    X   |     X    |
|         giant        |       X      |    X   |     X    |
|      giant eagle     |       X      |    X   |     X    |
|       giant elk      |       X      |    X   |     X    |
|       giant owl      |       X      |    X   |     X    |
|         gith         |       X      |    X   |     X    |
|         gnoll        |       X      |    X   |     X    |
|        gnomish       |       X      |    X   |     X    |
|        goblin        |       X      |    X   |     X    |
|      godstongue      |       X      |    X   |     X    |
|         grell        |       X      |    X   |     X    |
|        grippli       |       X      |    X   |     X    |
|         grung        |       X      |    X   |     X    |
|        hadozee       |       X      |    X   |     X    |
|       halfling       |       X      |    X   |     X    |
|         halri        |       X      |    X   |     X    |
|         hedge        |       X      |    X   |     X    |
|      hook horror     |       X      |    X   |     X    |
|    huginn's speech   |       X      |    X   |     X    |
|       ice toad       |       X      |    X   |     X    |
|         ignan        |       X      |    X   |     X    |
|       infernal       |       X      |    X   |     X    |
|       istarian       |       X      |    X   |     X    |
|     ixitxachitil     |       X      |    X   |     X    |
|        jerbeen       |       X      |    X   |     X    |
|      kenderspeak     |       X      |    X   |     X    |
|       kharolian      |       X      |    X   |     X    |
|         khur         |       X      |    X   |     X    |
|        kothian       |       X      |    X   |     X    |
|         kraul        |       X      |    X   |     X    |
|        kruthik       |       X      |    X   |     X    |
|       kuran'zol      |       X      |    X   |     X    |
|       lemurfolk      |       X      |    X   |     X    |
|        leonin        |       X      |    X   |     X    |
|        loxodon       |       X      |    X   |     X    |
|        mapach        |       X      |    X   |     X    |
|      marquesian      |       X      |    X   |     X    |
|        maynah        |       X      |    X   |     X    |
|       minotaur       |       X      |    X   |     X    |
|        modron        |       X      |    X   |     X    |
|       n'warian       |       X      |    X   |     X    |
|         naush        |       X      |    X   |     X    |
|       nerakese       |       X      |    X   |     X    |
|       netherese      |       X      |    X   |     X    |
|      nordmaarian     |       X      |    X   |     X    |
|    northern tongue   |       X      |    X   |     X    |
|         ogre         |       X      |    X   |     X    |
|         olman        |       X      |    X   |     X    |
|          orc         |       X      |    X   |     X    |
|        orkish        |       X      |    X   |     X    |
|        otyugh        |       X      |    X   |     X    |
|      primordial      |       X      |    X   |     X    |
|        quirapu       |       X      |    X   |     X    |
|         quori        |       X      |    X   |     X    |
|        riedran       |       X      |    X   |     X    |
|       sahuagin       |       X      |    X   |     X    |
|        sensan        |       X      |    X   |     X    |
|        shankhi       |       X      |    X   |     X    |
|       sindarin       |       X      |    X   |     X    |
|     skitterwidget    |       X      |    X   |     X    |
|         slaad        |       X      |    X   |     X    |
|       solamnic       |       X      |    X   |     X    |
|        sphinx        |       X      |    X   |     X    |
|        sylvan        |       X      |    X   |     X    |
|        terran        |       X      |    X   |     X    |
|        thayan        |       X      |    X   |     X    |
|     thieves' cant    |       X      |    X   |     X    |
|      thri-kreen      |       X      |    X   |     X    |
|     tletlahtolli     |       X      |    X   |     X    |
|       tlincalli      |       X      |    X   |     X    |
|        tosculi       |       X      |    X   |     X    |
|      troglodyte      |       X      |    X   |     X    |
|       trollkin       |       X      |    X   |     X    |
|      umber hulk      |       X      |    X   |     X    |
|        umbral        |       X      |    X   |     X    |
|      undercommon     |       X      |    X   |     X    |
|       vedalken       |       X      |    X   |     X    |
|       vegepygmy      |       X      |    X   |     X    |
|      void speech     |       X      |    X   |     X    |
|        vulpin        |       X      |    X   |     X    |
|      warg-speech     |       X      |    X   |     X    |
|        westron       |       X      |    X   |     X    |
|      winter wolf     |       X      |    X   |     X    |
|         worg         |       X      |    X   |     X    |
|        xingyu        |       X      |    X   |     X    |
|         yeti         |       X      |    X   |     X    |
|        yikaria       |       X      |    X   |     X    |
|        zabaani       |       X      |    X   |     X    |
|        zemnian       |       X      |    X   |     X    |
|       ziklight       |       X      |    X   |     X    |

### Weapon Settings Dictionary
This server variable uses a json to determine what weapons can be learned and what ability scores are used for each. Within the `weapon_dict` svar, any weapons left out of the svar will become weapons that players are not allowed to learn through the training alias.

If you do not have the `weapon_dict` svar created, it will default to the below settings:

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/weapons.json)

|                | Strength | Dexterity |
|:--------------:|:--------:|:---------:|
|      Club      |     X    |           |
|     Dagger     |     X    |     X     |
|    Greatclub   |     X    |           |
|     Handaxe    |     X    |           |
|     Javelin    |     X    |           |
|  Light Hammer  |     X    |           |
|      Mace      |     X    |           |
|  Quarterstaff  |     X    |           |
|     Sickle     |     X    |           |
|      Spear     |     X    |           |
|      Yklwa     |     X    |           |
| Light Crossbow |          |     X     |
|      Dart      |          |     X     |
|    Shortbow    |          |     X     |
|      Sling     |          |     X     |
|    Battleaxe   |     X    |           |
|      Flail     |     X    |           |
|     Glaive     |     X    |           |
|    Greataxe    |     X    |           |
|   Greatsword   |     X    |           |
|     Halberd    |     X    |           |
|      Lance     |     X    |           |
|    Longsword   |     X    |           |
|      Maul      |     X    |           |
|   Morningstar  |     X    |           |
|      Pike      |     X    |           |
|     Rapier     |     X    |     X     |
|    Scimitar    |     X    |     X     |
|   Shortsword   |     X    |     X     |
|     Trident    |     X    |           |
|    War Pick    |     X    |           |
|      Whip      |     X    |     X     |
|     Blowgun    |          |     X     |
|  Hand Crossbow |          |     X     |
| Heavy Crossbow |          |     X     |
|     Longbow    |          |     X     |
|       Net      |     X    |           |

### Instrument Settings Dictionary
This server variable uses a json to determine what instruments can be learned and what ability scores are used for each. Within the `instrument_dict` svar, any instruments left out of the svar will become instruments that players are not allowed to learn through the training alias.

If you do not have the `instrument_dict` svar created, it will default to the below settings:

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/instruments.json)

|               | Strength | Dexterity | Constitution | Intelligence | Wisdom | Charisma |
|:-------------:|:--------:|:---------:|:------------:|:------------:|:------:|:--------:|
|    Bagpipes   |          |           |              |       X      |        |     X    |
|      Drum     |          |           |              |       X      |        |     X    |
|    Dulcimer   |          |           |              |       X      |        |     X    |
|     Flute     |          |           |              |       X      |        |     X    |
|      Lute     |          |     X     |              |       X      |        |     X    |
|      Horn     |     X    |           |              |       X      |        |     X    |
|   Pan Flute   |          |           |              |       X      |        |     X    |
|     Shawm     |          |           |              |       X      |        |     X    |
|      Lyre     |          |     X     |              |       X      |        |     X    |
|      Viol     |          |     X     |              |       X      |        |     X    |
|   Bird Pipes  |          |           |              |       X      |        |     X    |
|     Glaur     |          |           |       X      |              |        |     X    |
|   Hand Drum   |          |     X     |              |              |        |     X    |
|    Longhorn   |          |           |              |              |    X   |     X    |
|    Songhorn   |          |           |              |       X      |        |     X    |
|     Tantan    |          |     X     |              |              |        |     X    |
|    Thelarr    |          |           |              |       X      |        |     X    |
|     Tocken    |          |     X     |              |              |        |     X    |
|    Wargong    |     X    |           |              |              |        |     X    |
| Whistle-stick |          |           |              |              |    X   |     X    |
|    Yarting    |          |     X     |              |              |        |     X    |
|    Zulkoon    |          |           |       X      |              |        |     X    |

### Gaming Set Settings Dictionary
This server variable uses a json to determine what gaming sets can be learned and what ability scores are used for each. Within the `gaming_dict` svar, any gaming sets left out of the svar will become gaming sets that players are not allowed to learn through the training alias.

If you do not have the `gaming_dict` svar created, it will default to the below settings:

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/gaming.json)

|                       | Dexterity | Intelligence | Wisdom | Charisma |
|:---------------------:|:---------:|:------------:|:------:|:--------:|
|        Dice Set       |     X     |       X      |    X   |     X    |
|    Dragonchess Set    |           |       X      |    X   |     X    |
|    Playing Card Set   |     X     |       X      |    X   |     X    |
| Three-dragon Ante Set |           |       X      |    X   |     X    |

### Skill Settings Dictionary (README)
This server variable uses a json to determine what skills can be learned. This is **NOT** RAW. 

If you do not have the `skill_dict` svar created, it will be (by default) turned off.

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/skills.json)

### Armor Settings Dictionary (README)
This server variable uses a json to determine what skills can be learned. This is **NOT** RAW. 

If you do not have the `armor_dict` svar created, it will be (by default) turned off.

[Dictionary Example](https://github.com/Shadow-Draconic-Development/Avrae-Training-Manager/blob/main/Data/dictionary%20examples/armor.json)

## License Notice

This work includes material taken from the System Reference Document 5.1 (“SRD 5.1”) by Wizards of the Coast LLC and available at https://dnd.wizards.com/resources/systems-reference-document. The SRD 5.1 is licensed under the Creative Commons Attribution 4.0 International License available at https://creativecommons.org/licenses/by/4.0/legalcode.

This work includes material written by Seth Hartman (aka ShadowsStride) and is licensed under the Creative Commons Attribution 4.0 International License available at https://creativecommons.org/licenses/by/4.0/legalcode.

## Requests
Requests can be made at this [link.](https://forms.gle/YYkyPcBb1WHXWMYE6)

All requests can be viewed at this  [link.](https://docs.google.com/spreadsheets/d/1OyW78hh1ARDHeDu4hF4X2TxcpYSrrArprs8pkQB3zo4/edit?usp=sharing) All requests are viewable by all, if I have any problems I will restrict access to these links.

## Ko-fi
You can click the button below to view my ko-fi page. Donations like this help me write more aliases and donators do get priority on feature requests.

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/F2F6MG4NH)