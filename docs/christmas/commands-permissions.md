# Commands & permissions

The Christmas+ plugin comes with lots of useful commands with multiple aliases. If you would like to have a new command added please contact us, we are open for new feature suggestions.

## Commands

### Aliases

| Command aliases                          | Description                     |
|------------------------------------------|---------------------------------|
| /adventcalendar /ac /calendar /acalendar | Advent calendar command aliases |
| /christmas /ch /chr /christmasplus /xmas | Christmas command aliases       |
| /cracker /crackers                       | Crackers command aliases        |

### Commands list

| Command root    | Command                                | Description                                                                                                                                                                                                                | Required permission                                                                                       |
|-----------------|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| /adventcalendar |                                        | Open the advent calendar GUI                                                                                                                                                                                               | christmasplus.adventcalendar                                                                              |
| /adventcalendar | reset <player> <day number \| all>     | Resets the entire calendar or a specific day to a specific player                                                                                                                                                          | christmasplus.adventcalendar.reset                                                                        |
| /adventcalendar | test                                   | Toggles on/off the test mode for yourself allowing to claim all gifts regardless of day/month                                                                                                                              | christmasplus.adventcalendar.test                                                                         |
| /christmas      | snow                                   | Toggle the snow effect for yourself, snow must be enabled globally in order to use it                                                                                                                                      | christmasplus.christmas.snow                                                                              |
| /christmas      | start santa [time] [world] [x] [y] [z] | Start the Santa Claus event for specified time (time string is optional,  the default value is set in config.yml). Time string, world name and  coordinates are required when starting the event from the server  console. | christmasplus.christmas.start                                                                             |
| /christmas      | start santa [time] random              | Same as above but the location is random (see FAQ #4 to learn how to setup locations)                                                                                                                                      | christmasplus.christmas.start                                                                             |
| /christmas      | stop <santa>                           | Manually stop the Santa Claus event                                                                                                                                                                                        | christmasplus.christmas.stop                                                                              |
| /christmas      | reload                                 | Reload the configuration                                                                                                                                                                                                   | christmasplus.christmas.reload                                                                            |
| /cracker        | list                                   | List all available crackers                                                                                                                                                                                                | christmasplus.cracker.list                                                                                |
| /cracker        | give <player> <cracker> [amount]       | Give crackers to other player                                                                                                                                                                                              | christmasplus.cracker.give                                                                                |
| /cracker        | get <cracker> [amount]                 | Get certain amount of cracker                                                                                                                                                                                              | christmasplus.cracker.get + christmasplus.cracker.get.multiple to be able to specify amount higher than 1 |

### Permissions

All command permissions have been listed above.

Furthermore, there are some extra permissions:

| Permission node                         | Description                                                                                                            |
|-----------------------------------------|----------------------------------------------------------------------------|
| christmasplus.adventcalendar.test       | Allows to test the advent calendar setup without month or day restrictions |
| christmasplus.adventcalendar.claimpast  | Allows to claim gifts from past days                                       |
