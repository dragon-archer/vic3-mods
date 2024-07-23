<h1 align="center">P社Bug修复</h1>

<p align="center">
	<a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3277665729">
		<img src="https://img.shields.io/steam/views/3277665729" alt="Steam Views">
	</a>
	<a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3277665729">
		<img src="https://img.shields.io/steam/downloads/3277665729" alt="Steam Downloads">
	</a>
	<a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3277665729">
		<img src="https://img.shields.io/steam/subscriptions/3277665729" alt="Steam Subscriptions">
	</a>
	<a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3277665729">
		<img src="https://img.shields.io/steam/favorites/3277665729" alt="Steam Favorites">
	</a>
</p>

<p align="center"><a href="README.md">English</a> | 中文</p>

![Thumbnail](thumbnail.png)

## 功能

- 修复了各类游戏文件中超过50个 bug
- 快速获取最新版 bug 的修复
- 提升游戏性能（因为大幅减少了错误日志大小）
- 大量中文文本修正
- 兼容任意其它 mod

## Mod 顺序

本mod放在任何位置皆可工作，同时其它mod可以安全的覆盖本mod中的文件
建议将本mod放在播放集最上面，这样可以避免其它mod的文件被本mod覆盖而导致无法工作

## 支持的语言

所有语言都支持，但对于中文有额外的文本修正

部分文本修正也支持英语

## 修复 bug 列表

- common/
  - achievements/standard_achievments: Fix scope error
  - buildings/02_agro: Remove duplicate vineyard
  - character_interactions/00_character_interactions: Fix scope errors
  - character_templates/country_prg: Fix triggers for `PRG_juan_silvano_godoi` and `PRG_rafael_barrett`
  - company_types/00_companies_soi: Fix triggers for `company_moscow_irrigation_company`
  - diplomatic_actions/
    - 02_relations_actions: Auto break `Increase Relations` towards Power Bloc Leaders with 50+ relation if you're also an Power Bloc Leader
    - 42_subjects_request_market_control: Hide `Request Market Control` for market owner
  - flag_definitions/00_flag_definitions: Fix Brunei & Scandinavian flags
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

## 已知问题

- `强制国有化`战争目标仅会国有化**直接**由目标国家政府所控制的建筑等级，而那些由目标国家境内的所有权建筑控制的建筑等级**不会**被国有化

## 给其它 mod 作者的注意事项

欢迎大家将本 mod 的部分或者全部内容整合到你自己的 mod 中

如果想要查看本 mod 的修复细节可以直接搜索 `#PBF` ，大部分修改处都已用此标识标注，或者你也可以直接对比 mod 中的文件和同名的原版游戏文件来查看差异

此外，本 mod 所有修改都采用原文件名完整覆盖而不是创建一个 `zz_` 开头的文件局部覆盖是有意为之，这样其它 mod 如果修改了同一个文件（虽然这是一个坏习惯）但添加了新的功能的话可以安全的覆盖本 mod 中的文件

## 致谢

感谢 [CaesarVincens](https://forum.paradoxplaza.com/forum/members/caesarvincens.535173/) 和 [茶锈](https://steamcommunity.com/profiles/76561199017901516) 提供的许多P社bug线索

## 我的其它模组和工具

- GDP所有权显示 - 在国家面板显示选定国家的国内外GDP所有权比例
  - 可从 [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=3290552216) 或 [GitHub](https://github.com/dragon-archer/vic3-mods/tree/main/GDP%20Ownership%20Display) 获取
- Paradox Highlight - 一个为P社脚本提供语法高亮的VSCode插件
  - 可从 [GitHub](https://github.com/dragon-archer/paradox-highlight) 或 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dragon-archer.paradox-highlight) 获取，也可访问 [Paradox Forum](https://forum.paradoxplaza.com/forum/threads/modding-tool-paradox-highlight-a-vscode-extension-for-highlighting-paradox-scripts.1686066/) 获取更多信息
