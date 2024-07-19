# Paradox Bug Fix

中文版简介请见[此处](README.zh.md)

![Thumbnail](thumbnail.png)

## Features

- Fixed 50+ bugs in all kinds of game files
- Updated frequently for latest fixes
- Boosted performance due to massively reduced error logs
- Special fixes for the localization of Simplified Chinese
- Compatible with all other mods

## Placement order

This mod can be placed at any order to function and is safe to be overwritten by other mods, but it's recommended to place it on top of all mods, in case other mods may be affected and/or corrupted

## Supported languages

All languages are supported, with special localization fixes for Simplified Chinese

Some localization fixes are also available in English

## List of fixed bugs

- common/
  - achievements/standard_achievments: Fix scope error
  - buildings/02_agro: Remove duplicate vineyard
  - character_interactions/00_character_interactions: Fix scope errors
  - character_templates/country_prg: Fix triggers for `PRG_juan_silvano_godoi` and `PRG_rafael_barrett`
  - company_types/00_companies_soi: Fix triggers for `company_moscow_irrigation_company`
  - diplomatic_actions/
    - 02_relations_actions: Auto break `Increase Relations` towards Power Bloc Leaders with 50+ relation if you're also an Power Bloc Leader
    - 42_subjects_request_market_control: Hide `Request Market Control` for market owner
  - flag_definitions/00_flag_definitions: Fix Brunei flag
  - ideologies/
    - Fix the icon of `Feminist IG`
    - Remove duplicate law stances from `Socialist` ideology since it can only be applied to TU who already have `Proletarian` ideology
    - Fix a trigger for `Radical` ideology (`NOT` -> `NOR`)
    - Add missing law stances for `Proletarian`, `Modernizer`, `Bonapartist`, `Orléanist` and `Market Liberal`
    - Correct agitator check for `Enlightened Royalist`
    - Correct agitator weight for `Enlightened Royalist` and `Humanitarian`
  - journal_entries/
    - Enable AI countries to activate & complete techonology JEs
    - Fix Opium JE as Opium Plantation is **NOT** a potential resource
    - Reduce the requirement of Munitions Factories from 5 munition plants to 2 as it's not possible for most countries to own 250+ infantry at early game
    - Hide `The Acquisition of Alaska` if you already owns Alaska
    - Invaliadate lobby JEs if the relevant lobby is disbanded
  - laws/
    - Fix pop_support for Bureaucracy & Children Rights laws
    - Fix state religion changes for Atheism related laws
    - Fix slavery laws
      - Add missing closing bracket
      - Fix scope errors
      - Slaves **SHOULD NOT** support Debt Slavery!!!
  - mobilization_options/: Add missing comment
  - modifier_type_definitions/
    - Make `interest_group_ig_armed_forces_approval_add` have 1 decimal to keep in line with similar modifier types
    - Make `power_bloc_income_transfer_to_leader_factor` a percentage
  - objective_subgoals/01_subgoals_player_objectives_egalitarian: Remove non-exists scope `slavery_objective_target`
  - on_actions/00_code_on_actions: Fix church ideology
  - parties/
    - Correct `from_powerful_communists` for `Social Democratic Party`
    - Fix several `from_serfdom` triggers
    - Always allow forming parties if it's the only valid party
  - pop_types/: Reorder the calculation of `political_engagement_mult` & `qualifications` to boost perfomance (Thanks the idea of PBO mod)
  - production_methods/
    - 02_agro: `pm_fertilization_building_rice_farm` should consume only 20 fertilizer
    - 11_private_infrastructure: `pm_trade_center_principle_external_trade_2` should also have basic clerk employments
  - script_values/
    - Fix liberty desire display
    - Increase the reduction of `East Indies` from 0.2 to 0.4
  - scripted_buttons/00_colonial_administration_buttons
    - Create `vassal` instead of `puppet` for unrecognized countries to avoid auto-independence
    - Check only direct subjects when expanding colonial administration
  - scripted_effects/
    - Cleanup variables instead of setting it to `no`
    - Handle expedition location for expedition progress < 1
    - Fix `calculate_caudillo_progress` calculation
  - scripted_triggers/
    - Fix typo in `is_brazil_northeast_state` (correct STATE_PAUAI to STATE_PIAUI)
    - Check for the existence of scopes in `ai_has_enact_weight_modifier_journal_entries`
    - Check for the existence of `ruler` in `chinese_manchu_queue_hairstyle_character_trigger`
- events/
  - agitators_events/
    - revolution_events_02: Fix scope error in `revolution_pulse_events.9`
    - revolution_events_03: Fix scope error in `revolution_pulse2_events.4`
  - american_civil_war/acw_events: `acw_events.3` should be restricted to USA-owned Mexican states
  - brazil/
    - coffee_with_milk: Check for scope existence & fix typo in `coffee_with_milk.6`
    - pedro_brazil_events: Correctly save `isabel_scope` in `pedro.12`
  - election_events/communist_facist_election_events: Fix scope error in `communist_elections.1` and `communist_elections.3`
  - expedition_events/niger_river_expedition_events: Avoid improve relation with your own country in `expedition_events.130`
  - law_events/slavery_laws: Fix a trigger in `slavery_law_events.7` (`NOT` to `NOR`)
  - german_unification: Allow forming `NGF` and `SGF` as principality or below
  - oil_rush_events: Avoid permanent funding oil pipelines in `oil_rush.4`
  - red_scare_events: Fix scope error in `red_scare.14`
  - victoria_events: Check for the existence of `c:HAN`
- gfx/portraits/
  - portrait_animations/animations: Check for the existence of character owner in `smoker_character_idle`
  - portrait_modifiers/01_headgear: Check for the existence of character owner in `korean_empire_military_headgear`
- gui/states_panel: Translate for `Inactive Treaty Port`
- localization/: Fix the rank in `POWER_BLOC_COHESION_WORST_INFAMY` (English and Simplified Chinese)

## Note for modders

You're welcome to integrate part or all of this mod in your own mod

For modification details, most modifications are marked with `#PBF`, and you can always compare the file with the vanilla one to find the difference

Plus, it's intended to overwrite the whole vanilla file instead of creating a new file starting with `zz_` in this mod, as it only fix bugs and should simply be replaced by other mods that actually change the content

## Credits

Thanks [CaesarVincens](https://forum.paradoxplaza.com/forum/members/caesarvincens.535173/) and [茶锈](https://steamcommunity.com/profiles/76561199017901516) for providing many Paradox bug clues

## My other mods & tools

- GDP Ownership Display - Display GDP ownership ratio at home and abroad on country panel
  - Get it on [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=3290552216) or [GitHub](https://github.com/dragon-archer/vic3-mods/tree/main/GDP%20Ownership%20Display)
- Paradox Highlight - A VS Code extension that provides syntax highlight for Paradox Games
  - Get it on [GitHub](https://github.com/dragon-archer/paradox-highlight) or [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dragon-archer.paradox-highlight), or visit [Paradox Forum](https://forum.paradoxplaza.com/forum/threads/modding-tool-paradox-highlight-a-vscode-extension-for-highlighting-paradox-scripts.1686066/) for more information
