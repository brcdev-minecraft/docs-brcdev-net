 # Placeholders

Remember to get the placeholders from a list corresponding to the placeholders plugin you're using.

## PlaceholderAPI

<p class="warn"><b>Note:</b> PAPI expansion isn't required and it even may break the plugin placeholders.</p>

Plugin versions required to use these placeholders:

| Plugin         | Version         |
|----------------|-----------------|
| Gangs+         | 2.27.0 or newer |
| PlaceholderAPI | 2.10.3 or newer |

### Placeholders

| Placeholder name                                                                                                                                                       | Description                                                   |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| %gangsplus_in_gang%                                                                                                                                                    | Returns whether a player is in a gang                         |
| %gangsplus_gang_name%                                                                                                                                                  | Returns player's gang name                                    |
| %gangsplus_gang_name_formatted%                                                                                                                                        | Returns formatted player's gang name                          |
| %gangsplus_gang_rank%                                                                                                                                                  | Returns name of player's in-gang rank                         |
| %gangsplus_gang_rank_number%                                                                                                                                           | Returns numeric representation of player's in-gang rank       |
| %gangsplus_gang_friendly_fire%                                                                                                                                         | Returns whether friendly fire is enabled in player's gang     |
| %gangsplus_gang_online_members_list%                                                                                                                                   | Returns list of online players from player's gang             |
| %gangsplus_gang_online_members_count%                                                                                                                                  | Returns number of online players from player's gang           |
| %gangsplus_gang_offline_members_list%                                                                                                                                  | Returns list of offline players from player's gang            |
| %gangsplus_gang_offline_members_count%                                                                                                                                 | Returns number of offline players from player's gang          |
| %gangsplus_gang_members_list%                                                                                                                                          | Returns list of all members of player's gang                  |
| %gangsplus_gang_members_count%                                                                                                                                         | Returns number of all members of player's gang                |
| %gangsplus_gang_leader%                                                                                                                                                | Returns the name of player's gang leader                      |
| %gangsplus_gang_level%                                                                                                                                                 | Returns the player's gang level                               |
| %gangsplus_gang_wins%                                                                                                                                                  | Returns the player's gang fights won count                    |
| %gangsplus_gang_losses%                                                                                                                                                | Returns the player's gang fights lost count                   |
| %gangsplus_gang_wlr%                                                                                                                                                   | Returns the player's gang fight win/lose ratio                |
| %gangsplus_gang_wlr_raw%                                                                                                                                               | Returns the player's gang fight win/lose ratio (raw number)   |
| %gangsplus_gang_kills%                                                                                                                                                 | Returns the player's gang kills                               |
| %gangsplus_gang_deaths%                                                                                                                                                | Returns the player's gang deaths                              |
| %gangsplus_gang_kdr%                                                                                                                                                   | Returns the player's gang fight kill/death ratio              |
| %gangsplus_gang_kdr_raw%                                                                                                                                               | Returns the player's gang fight kill/death ratio (raw number) |
| %gangsplus_gang_bank%                                                                                                                                                  | Returns the player's gang bank balance                        |
| %gangsplus_gang_bank_raw%                                                                                                                                              | Returns the player's gang bank balance (raw number)           |
| %gangsplus_gang_money%                                                                                                                                                 | Returns the player's gang members balance sum                 |
| %gangsplus_gang_money_raw%                                                                                                                                             | Returns the player's gang members balance sum (raw number)    |

### Leaderboard Placeholders

Leaderboard Placeholders are in the format of ``%gangsplus_gangs_top_<statistic>_<position>_<gang_property>%``.

> ``statistic`` is the rank order of the leaderboard. (eg. most kills)
> 
> ``position`` is the leaderboard position number. (eg. '1' for 1st place)
> 
> ``gang_property`` is the Gang's statistic you want to display. (eg. gang's kills)

#### Statistics

| Statistic Name | Description               |
|----------------|---------------------------|
| kills          | Gang Kill Count           |
| deaths         | Gang Death Count          |
| kdr            | Gang Kill/Death Ratio     |
| wins           | Gang Wins                 |
| losses         | Gang Losses               |
| wlr            | Gang Fight Win/Loss Ratio |
| level          | Gang Level                |
| members        | Gang Member Count         |
| members_online | Gang Online Member Count  |
| bank           | Gang Bank Balance         |
| balance        | Gang Balance              | 
| homes          | Gang Home Count           |

#### Gang Properties

| Gang Property Name | Description                     |
|--------------------|---------------------------------|
| bank               | Gang Bank Balance Formatted     |
| bank_raw           | Gang Bank Balance               |
| deaths             | Gang Death Count                |
| homes_count        | Gang Home Count                 |
| kdr                | Gang Kill/Death Ratio Formatted |
| kdr_raw            | Gang Kill/Death Ratio           |
| kills              | Gang Kill Count                 |
| leader             | Gang Leader's username          |
| level              | Gang Level                      |
| loss               | Gang Loss Count                 |
| members_count      | Gang Member Count               |
| members_list       | Gang Member List                |
| money              | Gang Balance Formatted          |
| money_raw          | Gang Balance                    |
| name               | Gang Name                       |
| wins               | Gang Win Count                  |
| wlr                | Gang Win/Loss Ratio Formatted   |
| wlr_raw            | Gang Win/Loss Ratio             |



## MVdWPlaceholderAPI

<p class="error">MVdWPlaceholderAPI support was removed in Gangs+ 2.26.0. Use PlaceholderAPI placeholders above instead.</p>


Plugin versions required to use these placeholders:

| Plugin             | Version         |
|--------------------|-----------------|
| Gangs+             | 2.22.0 - 2.25.0 |
| MVdWPlaceholderAPI | 3.0.1 or newer  |

Placeholders list:

| Placeholder name                         | Description                                               |
|------------------------------------------|-----------------------------------------------------------|
| {gangsplus_2_in_gang}                    | Returns whether a player is in a gang                     |
| {gangsplus_2_gang_name}                  | Returns player's gang name                                |
| {gangsplus_gang_name_formatted}          | Returns formatted player's gang name                      |
| {gangsplus_2_gang_rank}                  | Returns name of player's in-gang rank                     |
| {gangsplus_2_gang_rank_number}           | Returns numeric representation of player's in-gang rank   |
| {gangsplus_2_gang_friendly_fire}         | Returns whether friendly fire is enabled in player's gang |
| {gangsplus_2_gang_online_members_list}   | Returns list of online players from player's gang         |
| {gangsplus_2_gang_online_members_count}  | Returns number of online players from player's gang       |
| {gangsplus_2_gang_offline_members_list}  | Returns list of offline players from player's gang        |
| {gangsplus_2_gang_offline_members_count} | Returns number of offline players from player's gang      |
| {gangsplus_2_gang_members_list}          | Returns list of all members of player's gang              |
| {gangsplus_2_gang_members_count}         | Returns number of all members of player's gang            |
| {gangsplus_2_gang_leader}                | Returns the name of player's gang leader                  |
| {gangsplus_2_gang_level}                 | Returns the player's gang level                           |
| {gangsplus_2_gang_wins}                  | Returns the player's gang fights won count                |
| {gangsplus_2_gang_losses}                | Returns the player's gang fights lost count               |
| {gangsplus_2_gang_wlr}                   | Returns the player's gang fight win/lose ratio            |
| {gangsplus_2_gang_kills}                 | Returns the player's gang kills                           |
| {gangsplus_2_gang_deaths}                | Returns the player's gang deaths                          |
| {gangsplus_2_gang_kdr}                   | Returns the player's gang fight kill/death ratio          |
| {gangsplus_2_gang_bank}                  | Returns the player's gang bank balance                    |
| {gangsplus_2_gang_money}                 | Returns the player's gang members balance sum             |

