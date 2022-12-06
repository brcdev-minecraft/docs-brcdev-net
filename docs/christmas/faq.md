# FAQ

#### How do you give multiple gifts one day?

First, make sure you're using at least the 1.0.4 version. Now, in order to add multiple items you have to create a config section named `multiple` inside the type of the gift (in the example it's `default` and `donor`, I added it to `default` - you add it to both or just one of them). Then you can add the items inside the multiple sections, each of them has to have an unique ID (value doesn't matter, it isn't the number of the day, it just has to be unique). I set it to `1`, `2` and `3`. In the example it's an item, enchantment and command, though it can be as many items as you want.

Example:
```yaml
gifts:
  1:
    default:
      multiple:
        1:
          type: item
          item:
            material: STONE
            quantity: 16
        2:
          type: enchantment
          enchantment: FORTUNE
          enchantmentLevel: 1
        3:
          type: command
          commands:
              - "say Merry christmas, %PLAYER%!"
    donor:
      type: item
      item:
        material: GOLD_INGOT
        quantity: 32
```


#### How do you change the advent calendar's month?

You can change the month by adding a `month` entry to your adventcalendar.yml.

<p class="error"><b>Note:</b> Changing this value requires database reset!</p>

Example:
```yaml
# Number of the month the advent calendar will be enabled in. Note: Changing this value requires database reset
month: 11
```


#### How do you give a random gift each day in the advent calendar?

<p class="error"><b>Note:</b> You need at least 2.2.8 version to use this feature.</p>

It's similar to multiple gifts explained above first FAQ item, but the config section is named `random`. Furthermore, you have to add chance to each item. These are actually the weights of gifts, they don't have to sum up to 100%.

Example:
```yaml
1:
  default:
    random:
      1:
        type: item
        item:
          material: STONE
          quantity: 16
        chance: 0.5
      2:
        type: command
        commands:
            - "say Merry christmas, %PLAYER%!"
        chance: 0.3
      3:
        type: item
        item:
          material: GOLD_INGOT
          quantity: 16
        chance: 0.1
  donor:
    type: item
    item:
      material: GOLD_INGOT
      quantity: 32
```

#### How do you start the Santa event in random locations?

For performance and convenience reasons Santa can spawn randomly only in preconfigured locations. You can edit them in the `santaClausEvent` -> `locations` section of your config.yml. After adding some, you can start the event using the `/christmas start santa [time] random` command.

Example:
```yaml
# Locations of Santa's random spawns and their chances (optional). More info in the plugin description
locations:
  1:
    world: world
    x: -53
    y: 27
    z: -53
    yaw: 0.0
    pitch: 0.0
  2:
    world: world
    x: -5
    y: 27
    z: 5
```


#### How do you optimise the snow particles displaying?

When using the snow particles feature on bigger servers, you may experience minor performance issues. This is because the snow display task has a low interval value set by default for the best player experiences. Try increasing it with a hidden config.yml entry to 10 or 20 ticks to make it lighter for your server.

Example:
```yaml
snow:
  # Choose whether snow particle effect will be enabled
  enable: true
  # Choose the snow level. There are 5 levels (1-5)
  level: 1
  # Choose worlds to disable snow effect in (set to [] for none)
  disableInWorlds:
    - world_nether
  # Choose whether snow should be enabled only in WorldGuard regions listed below
  enableOnlyInRegions: false
  # List of WorldGuard regions where the snow should be enabled in
  regions: []
  # Interval of the snow display taks
  displayTaskInterval: 2L
```


#### How do you give crackers as gifts or add as Santa drops?

Simply add `cracker: <cracker id>` entry inside the item section to give cracker item. Other entries such as name, lore etc. aren't required and may result in item being not recognised as cracker, thus aren't recommended to be set.

Example (adventcalendar.yml):
```yaml
3:
  default:
    type: item
    item:
      cracker: example
```

Example (config.yml):
```yaml
gifts:
  # Gift ID, value doesn't matter but has to be unique
  1:
    # Chance to drop this gift (out of total of chances of all gifts listed below, it DOESN'T HAVE to sum up to 1.0)
    chance: 0.6
    # Gift item, more info: https://docs.brcdev.net/#/item-meta
    item:
      cracker: example
```
