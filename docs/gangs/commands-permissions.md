# Commands & permissions

The Gangs+ plugin comes with lots of useful commands with multiple aliases. If you would like to have a new command
added please contact us, we are open for new feature suggestions.

## Commands

### Aliases

| Command aliases              | Description               |
|------------------------------|---------------------------|
| /g or /gang                  | Gang command aliases      |
| /gc or /gchat or /gangchat   | Gang chat command aliases |
| /ac or /achat or /allychat   | Ally chat command aliases |
| /fight                       | Fight command aliases     |
| /ga or /gadmin or /gangadmin | Admin command aliases     |

### Commands list

| Command root | Command                                       | Description                                                                             | Required permission             |
|--------------|-----------------------------------------------|-----------------------------------------------------------------------------------------|---------------------------------|
| /g           | help                                          | List of all gang-related commands                                                       | gangsplus.gang.help           | gangsplus.gang.*      |
| /g           | list                                          | List of all gangs                                                                       | gangsplus.gang.list           |
| /g           | top                                           | Gangs leaderboard                                                                       | gangsplus.gang.top            |
| /g           | info [gang]                                   | Specified gang's statistics                                                             | gangsplus.gang.info           |
| /g           | create \<name\>                               | Create a new gang                                                                       | gangsplus.gang.create         |
| /g           | disband                                       | Disband your gang                                                                       | gangsplus.gang.disband        |
| /g           | invite \<player\>                             | Invite specified player to your gang                                                    | gangsplus.gang.invite         |
| /g           | join \<gang\><br/>accept \<gang\>             | Join specified gang                                                                     | gangsplus.gang.join           |
| /g           | uninvite \<player\>                           | Cancel player's invitation to your gang                                                 | gangsplus.gang.uninvite       |
| /g           | kick \<player\>                               | Kick player out of your gang                                                            | gangsplus.gang.kick           |
| /g           | leave                                         | Leave your gang                                                                         | gangsplus.gang.leave          |
| /g           | friendlyfire                                  | Toggle friendly fire in the gang                                                        | gangsplus.gang.friendlyfire   |
| /g           | levelup \<player\>                            | Level up to higher gang level                                                           | gangsplus.gang.levelup        |
| /g           | promote \<player\>                            | Promote specified player to higher rank                                                 | gangsplus.gang.promote        |
| /g           | demote \<player\>                             | Demote specified player to lower rank                                                   | gangsplus.gang.demote         |
| /g           | leader \<player\>                             | Give the gang leadership to specified player                                            | gangsplus.gang.leader         |
| /g           | deposit \<amount\>                            | Deposit money into your gang's bank account                                             | gangsplus.gang.deposit        |
| /g           | withdraw \<amount\>                           | Withdraw money from your gang's bank account                                            | gangsplus.gang.withdraw       |
| /g           | listhomes                                     | List of all gang homes                                                                  | gangsplus.gang.listhomes      |
| /g           | home [name]                                   | Teleport to specified gang home                                                        | gangsplus.gang.home           |
| /g           | sethome [name]                                | Set specified gang home location                                                        | gangsplus.gang.sethome        |
| /g           | delhome [name]                                | Delete specified gang home                                                              | gangsplus.gang.delhome        |
| /g           | player \<player\>  <br/>playerinfo \<player\> | Specified player's statistics                                                           | gangsplus.gang.playerinfo     |
| /g           | regroup \<home name\>                         | Send message to online gang members to regroup at specified home                        | gangsplus.gang.regroup        |
| /g           | ally \<gang\>                                 | Send alliance request to specified gang                                                 | gangsplus.gang.ally           |
| /g           | neutral \<gang\>                              | Set relation with an ally to neutral                                                    | gangsplus.gang.neutral        |
| /gc          | on                                            | Toggle gang chat on                                                                     | gangsplus.gangchat             | 
| /gc          | off                                           | Toggle gang chat off                                                                    | gangsplus.gangchat      |
| /gc          | \<message\>                                   | Send a single message on gang chat                                                      |gangsplus.gangchat      |
| /ac          | on                                            | Toggle ally chat on                                                                     | gangsplus.allychat             |
| /ac          | off                                           | Toggle ally chat off                                                                    | gangsplus.allychat      |
| /ac          | \<message\>                                   | Send a single message on ally chat                                                      | gangsplus.allychat      |
| /fight       | challenge \<players\> \<money\> \<gang\>      | Challenge specified gang for a fight                                                    | gangsplus.fight.challenge     | gangsplus.fight.*     |
| /fight       | accept \<gang\>                               | Accept fight challenge from specified gang                                              | gangsplus.fight.accept        |
| /fight       | decline \<gang\>                              | Decline fight challenge from specified gang                                             | gangsplus.fight.decline       |
| /fight       | join                                          | Join the fight your gang takes part in                                                  | gangsplus.fight.join          |
| /fight       | leave                                         | Leave the fight your gang takes part in                                                 | gangsplus.fight.leave         |
| /ga          | disband \<name\>                              | Disband specified gang                                                                  | gangsplus.gangadmin.disband   | gangsplus.gangadmin.* |
| /ga          | reload                                        | Disband specified gang                                                                  | gangsplus.gangadmin.reload    |
| /ga          | socialspy [player]                            | Toggle on gang chat social spy for specified player (or yourself if no name is given) | gangsplus.gangadmin.socialspy |

### Permissions

All command permissions have been listed above.

Furthermore, there are some extra permissions:

| Permission node         | Description                                                                                                  |
|-------------------------|--------------------------------------------------------------------------------------------------------------|
| gangsplus.fightcommands | Required to use specific commands set in the config during gang fight (useful for moderators/admins etc)     |
| gangsplus.checkbalance  | Required to see other gangs bank account balance (when `showGangBalanceToOthers` in the config set to false) |
