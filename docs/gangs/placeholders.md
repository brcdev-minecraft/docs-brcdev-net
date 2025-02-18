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

| Placeholder Name                                | Description                                             |
|------------------------------------------------|---------------------------------------------------------|
| %gangsplus_gangs_top_1_bank%                   | Returns the total bank balance of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_bank_raw%               | Returns the raw bank balance of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_deaths%                 | Returns the number of deaths of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_homes_count%            | Returns the number of homes owned by n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_kdr%                    | Returns the kill/death ratio of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_kdr_raw%                | Returns the raw kill/death ratio of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_kills%                  | Returns the number of kills by n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_leader%                 | Returns leader's name of n-th top gang (from 1 to ∞)   |
| %gangsplus_gangs_top_1_level%                  | Returns level of n-th top gang (from 1 to ∞)           |
| %gangsplus_gangs_top_1_loss%                   | Returns the number of losses of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_members_count%          | Returns the number of members in n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_members_list%           | Returns a list of members of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_money%                  | Returns the total money owned by n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_money_raw%              | Returns the raw money amount of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_name%                   | Returns name of n-th top gang (from 1 to ∞)            |
| %gangsplus_gangs_top_1_wins%                   | Returns the number of wins of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_wlr%                    | Returns the win/loss ratio of n-th top gang (from 1 to ∞) |
| %gangsplus_gangs_top_1_wlr_raw%                | Returns the raw win/loss ratio of n-th top gang (from 1 to ∞) |




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

