# FAQ

## Making weapons/armor/potions unstack

You can make multiple weapons/armor/potions unstack by adding `unstack: true` entry to the item. There is more detailed
instruction available [here](shopgui/stack-size).

Example:

```yaml
    2:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
      buyPrice: 1000
      sellPrice: 500
      slot: 1
      unstack: true
```

## Setting other item as a placeholder instead of the sold one

You can set another item as a placeholder in order to sell a different item (even with a different lore or name) by
adding additional a `placeholder` entry below specific item in the shop yaml.

Example:

```yaml
    2:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
      placeholder:
        material: SPONGE
        name: "Surprise!"
        quantity: 1
      buyPrice: 10
      sellPrice: 1
      slot: 1
```

## Making bought commands executed by the player instead the console

Simply add the `runAsBuyer: true` entry to your command item in the shop yml.

Example:

```yaml
    1:
      type: command
      item:
        material: WOOL
        quantity: 32
        damage: 0
      commands:
        - "say Hello, %PLAYER%!"
      runAsBuyer: true
      buyPrice: 500
      slot: 0
```

## Adding commands when player clicks/buys/sells an item

For commands executed by the player you can add any of following to an item: `commandsOnClick`, `commandsOnBuy`
, `commandsOnSell`<br />
For commands executed by the server console you can use: `commandsOnClickConsole`, `commandsOnBuyConsole`
, `commandsOnSellConsole`<br />
OnClick gets executed when a player clicks an item in the shop menu (can be used for linking to other
shops/plugins)<br />
OnBuy/OnSell get executed after a player buys/sells the item<br />

Example:

```yaml
  items:
    1:
      type: dummy
      item:
        material: GRASS
        quantity: 64
      commandsOnClick:
        - "shop wood"
      slot: 10
    2:
      type: item
      item:
        material: DIRT
        quantity: 64
      commandsOnBuy:
        - "shop"
      commandsOnSell:
        - "shop"
      commandsOnSellConsole:
        - "say Hey, %PLAYER%!"
      buyPrice: 30
      sellPrice: 3
      slot: 11
```

## Adding commands on item click to the main /shop menu

You can use both `commandsOnClick` and `commandsOnClickConsole` described above in the main menu as well. You can use it
both for an item actually opening a shop or a placeholder item with type `DUMMY`.

Example:

```yaml
shopMenuItems:
  # Has to be unique, value doesn't matter
  1:
    item:
      material: SADDLE
      quantity: 1
      name: "&3&lMiscellanous"
    commandsOnClick:
      - "say Example!"
    shop: "miscellanous"
    slot: 31
  2:
    type: dummy
    item:
      material: STONE
      quantity: 1
      name: "&3&lTest"
    commandsOnClickConsole:
      - "say Example console command!"
    slot: 32
```

## Changing the size of a shop

You can change the size of any of shop inventories in the shop yml. Simply add a size: x entry where x is the desired
size (it has to be either 9, 18, 27, 36, 45 or 54).

More information is available [here](shopgui/shops-items-setup?id=changing-sizesbuttons-of-shops).

Example:

```yaml
mining:
  name: "&2Mining Shop (page %page%)"
  size: 18
  items:
    1:
      type: item
      item:
        material: STONE_PICKAXE
        quantity: 1
        name: "&8Crappy Pickaxe"
        enchantments:
          - EFFICIENCY:1
      buyPrice: 50
      sellPrice: 25
      slot: 0
    2:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
      unstack: true
      buyPrice: 1000
      sellPrice: 500
      slot: 1
      page: 2
    3:
      type: item
      item:
        material: IRON_SPADE
        damage: 125
        quantity: 1
        enchantments:
          - EFFICIENCY:1
      buyPrice: 750
      sellPrice: 111.11
      slot: 2
```

## Making the buying/selling process faster

You can enable `quickBuySell` in your config.yml. This will result in the amount selection GUI not being closed after
buying or selling an item.

## Disabling direct access to a shop (using the GUI or /shop <name>) so it can be accessed only by having it open from the console/by another plugin

Simply add the `denyDirectAccess: true` entry to the shop in the shop yaml. Then the only way for players to access the
shop will be to have the /shop <player name> <shop name> executed by the console/another player/plugin.

Example:

```yaml
mining:
  name: "&2Mining Shop (page %page%)"
  #(Optional) Setting this to true will result in players being able to access the shop by having /shop <player name> <shop name> executed by the console/another player/plugin
  denyDirectAccess: true
  items:
    1:
      type: item
      item:
        material: STONE_PICKAXE
        quantity: 1
        name: "&8Crappy Pickaxe"
        enchantments:
          - EFFICIENCY:1
      buyPrice: 50
      sellPrice: 25
      slot: 0
    2:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
      unstack: true
      buyPrice: 1000
      sellPrice: 500
      slot: 1
    3:
      type: item
      item:
        material: IRON_SPADE
        damage: 125
        quantity: 1
        enchantments:
          - EFFICIENCY:1
      buyPrice: 750
      sellPrice: 111.11
      slot: 2
```

## Removing custom name/lore from the item bought by players

You can remove it by adding `stripItemMeta: true` entry to the item.

Example:

```yaml
    2:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
        name: "&aPickaxe"
      stripItemMeta: true
      buyPrice: 1000
      sellPrice: 500
      slot: 1
```

## Changing the maximal item stack size (regardless of global settings from config.yml)

Simply add a `maxStackSize` entry to desired item in the shop yaml.

Example:

```yaml
    2:
      type: item
      item:
        material: BUCKET
        quantity: 1
      maxStackSize: 10
      buyPrice: 200
      sellPrice: 20
      slot: 1
```

## Changing the format of displayed price and decimals

There are some additional secret settings available config.yml to change the format of displayed price.

Example:

```yaml
numberFormat:
  decimalSeparator: '.'
  groupingSeparator: ','
  minimumIntegerDigits: 1
  maximumIntegerDigits: 32
  minimumFractionDigits: 0
  maximumFractionDigits: 8
  hideFraction: true
```

## Changing the receipt message sent after buying/selling an item

You can define the custom messages at the bottom of the shop item (`messageBuy`, `messageSell`, `messageSellAll`). Same
placeholders apply as in the default messages from lang.yml.

Example:

```yaml
    1:
      type: item
      item:
        material: GRASS
        quantity: 64
      messageBuy: "You bought %amount% x %item% for $%price%."
      messageSell: "You sold %amount% x %item% for $%price%."
      messageSellAll: "You sold all %item% for $%price%."
      buyPrice: 50
      sellPrice: 5
      slot: 0
```

## Limiting the item stack size players are able to enchant at once

Simply add an entry named `enchantmentStackSizeLimit` with the value of the limit.

Example:

```yaml
    1:
      type: enchantment
      enchantment: SHARPNESS
      enchantmentLevel: 1
      item:
        material: DIAMOND_SWORD
        quantity: 1
        enchantments:
          - SHARPNESS:1
      enchantmentStackSizeLimit: 1
      buyPrice: 50
      sellPrice: 5
      slot: 0
```

## Adding more pages

Adding a new page is as simple as adding a `page: x` entry where `x` is the page number. When there's at least 1 item on
a page it will be automatically added to the GUI. Slot numbers start from 0 for every page.

Example:

```yaml
    1:
      type: item
      item:
        material: DIAMOND_PICKAXE
        quantity: 5
      buyPrice: 1000
      sellPrice: 500
      slot: 1
      page: 2
```

## Setting a different name of each page

Add an entry named `namePerPage` below `name` in the shop yaml. You can set as many names as you wish (the format
is `PAGE: NAME`)

Example:

```yaml
blocks:
  name: "&9&lBlocks (page %page%)"
  namePerPage:
    1: "&9&lRegular blocks"
    2: "&9&lNether blocks"
    3: "&9&lEnd blocks"
  items:
    1:
      type: item
      item:
        material: GRASS
        quantity: 64
      buyPrice: 50
      sellPrice: 5
      slot: 1
      page: 1
```

## Disallowing selling items with name/lore different from the shop item's ones

Simply add a `compareMeta: true` setting to your shop item in the shop yaml.

Example:

```yaml
    1:
      type: item
      item:
        material: GRASS
        quantity: 1
        lore:
          - "Test"
          - "Abc"
      compareMeta: true
      buyPrice: 50
      sellPrice: 5
      slot: 0
```

## Enabling compareMeta and/or stripItemMeta globally for all items

Add the following section to your config.yml and adjust it to your needs.

Example:

```yaml
# Choose predefined settings for all items (will be overriden when set explicitly for an item in shops.yml)
defaultItemSettings:
  # Choose whether item meta (name, lore etc.) should be compared when players attempt to sell an item
  compareMeta: false
  # Choose whether item meta should be removed from an item when it's purchased by a player from the shop
  stripItemMeta: false
```

## Changing the /shop command

You can't completely change it, you can only add aliases using Spigot's built-in commands.yml file, which can be found in the root directory of your server.

Example:

```yaml
# This is the commands configuration file for Bukkit.
# For documentation on how to make use of this file, check out the Bukkit Wiki at
# http://wiki.bukkit.org/Commands.yml
#
# If you need help on this file, feel free to join us on irc or leave a message
# on the forums asking for advice.
#
# IRC: #spigot @ irc.spi.gt
#    (If this means nothing to you, just go to http://www.spigotmc.org/pages/irc/ )
# Forums: http://www.spigotmc.org/
# Bug tracker: http://www.spigotmc.org/go/bugs

command-block-overrides: [ ]
aliases:
  market:
    - shop $1-
```

The above extract will allow players to make use of the /market command as if it was the /shop command, while accounting for any arguments that may be passed through. 
## Adding an alias /sellhand for /sell hand (with no space inbetween)

You can add it in commands.yml in the root folder of your server like shown below.

Example:

```yaml
aliases:
  sellhand:
    - "sell hand $1-"
```

## Adding "Owned"/"Not owned" tag to permission shop items

Simply add `%owned%` placeholder to `shopItemLoreFormat` -> `permission` in config.yml. It will be replaced with an
appropriate tag.

Example:

```yaml
#Format of item lores in shops, %buy% will be replaced with the buy price and %sell% with sell price
shopItemLoreFormat:
  #This lore will be applied to items
  item:
    - "&7Buy price: &c%buy%$"
    - "&7Sell price: &a%sell%$"
    - "&9Click with MMB to sell all"
  #This lore will be applied to items in the buy GUI (when enableBuyGUI is set to true)
  itemBuyGUI:
    - "&7Buy price: &c%buy%$"
  #This lore will be applied to items in the sell GUI (when enableSellGUI is set to true)
  itemSellGUI:
    - "&7Sell price: &a%sell%$"
  #This lore will be applied to the sell all button in the sell GUI (when enableSellGUI and enableSellGUISellAll are set to true)
  itemSellGUISellAll:
    - "&7Sell all for: &a%sell%$"
  #This one to permissions
  permission:
    - "&7Buy price: &c%buy%$"
    - "%owned%"
  #And this one to enchantments
  enchantment:
    - "&7Buy price: &c%buy%$"
  #And the last one to commands
  command:
    - "&7Buy price: &c%buy%$"
```

## Hiding only one of the "Owned"/"Not owned" tags from permission shop items

If you want to have only one of them displayed simply set the other one to blank in lang.yml. The example below shows
how to have only the "Owned" tag displayed.

Example:

```yaml
SHOP:
  PERMISSION:
    ALREADYOWNED: '&4(Already owned)'
    NOTOWNED: ''
```

## Allowing/disallowing access to particular shop in particular worlds

You can add either `worldsWhitelist` (to whitelist allowed worlds) or `worldsBlacklist` (to blacklist blocked worlds)
entry to shop yaml.

Example #1 (this will allow access in world_nether only):

```yaml
blocks:
  name: "&9&lBlocks (page %page%)"
  worldsWhitelist:
    - "world_nether"
```

Example #2 (this will allow access in any world except world_nether):

```yaml
blocks:
  name: "&9&lBlocks (page %page%)"
  worldsBlacklist:
    - "world_nether"
```

## Requiring players to have certain permissions to purchase an item

You can add `requiredPermissions` list to an item inside the shop yaml.

Example:

```yaml
    1:
      type: item
      item:
        material: GRASS
        quantity: 64
      requiredPermissions:
        - "example.permission1"
        - "example.permission2"
      buyPrice: 50
      sellPrice: 5
      slot: 10
```

## Adding decoration items to GUIs

You can add item with type `DUMMY` (since 1.18.2 version of the plugin). Such items can't be bought or sold, they can be
used for commands on click though.

Example:

```yaml
    1:
      type: dummy
      item:
        material: GRASS
        quantity: 64
      slot: 10
```

## Adding custom economy plugin support

You can use the EconomyProvider (see section API above for link) to implement your own economy handler. Then you need to
use the ShopGuiPlusApi#registerEconomyProvider method to register it and set the economyType in config.yml to CUSTOM.

## Changing the click cooldown inside GUIs

You can change it by adding a `clickCooldown` entry to `gui` section in config.yml. The value is click cooldown in
milliseconds (250 ms is default).

Example:

```yaml
gui:
  clickCooldown: 250
```

## Enabling/disabling amount selection GUI and bulk buy/sell GUI for specific shops or shop items 

You can override the default amount selection GUI and bulk buy/sell GUI settings (`enableBuyGUI`, `enableSellGUI`, `enableSellGUISellAll`)
from config.yml in each of shop yamls for specific shops and shop items.

Example:

```yaml
armor:
  name: "&4&lArmor (page %page%)"
  enableBuyGUI: false
  enableSellGUI: false
  enableBuyMoreGUI: false
  enableSellMoreGUI: false
  fillItem:
    material: BLACK_STAINED_GLASS_PANE
    name: " "
  items:
    1:
      type: item
      enableBuyGUI: false
      enableBuyMoreGUI: false
      enableSellGUI: false
      enableSellMoreGUI: false
      item:
        material: LEATHER_HELMET
        quantity: 1
      buyPrice: 40
      sellPrice: 8
      slot: 10
```

## Fixing previous/next page buttons opening buy menu instead

If you're experiencing this issue, it means you're running a really outdated configuration. We highly suggest to contact
its author with an inquiry to either update it or refund if it's a paid configuration - these changes were few years ago
and there was more than enough time to update.

However, if you want to fix them yourself, following steps must be performed:

1. Refactor your shop by merging all `blocks1`, `blocks2`, `blocks3` etc shops into one `blocks` with multiple pages
   according to the [instruction](shopgui/faq?id=adding-more-pages).
2. Remove the existing buttons with `-1` buy price and `commandsOnClick` added
3. Add buttons the correct way to the merged shop

Example of correct buttons setup:

Example:

```yaml
food:
  name: "&2&lFood (page %page%)"
  fillItem:
    material: BLACK_STAINED_GLASS_PANE
    name: " "
  buttons:
    goBack:
      slot: 49
    previousPage:
      slot: 39
    nextPage:
      slot: 41
  items:
    1:
      type: item
      item:
        material: MELON
        quantity: 10
      buyPrice: 30
      sellPrice: 6
      slot: 10
```

## Creating a NPC with shop

You can combine the ShopGUI+'s commands with NPC plugins such as i.e. Citizens.

Following commands can be used to set up a NPC shop with Citizens, so players have main shop menu opened when they click
the NPC:

```
/npc select
/npc cmd add -p shop
/citizens save
```

## Adding buttons to close currently open GUI

You can use the `closeGuiOnClick: true` option within both main menu and shops to add a button closing the currently
open GUI.

Example:

```yaml
  11:
    type: DUMMY
    item:
      material: BARRIER
      quantity: 1
      name: "&cClose"
    closeGuiOnClick: true
    slot: 32
 ```

## Disabling permission cache

For some reason, on some setups permission checks for price modifiers may not be working correctly. If it occurs on your
server, try disabling the cache. It may impact your server performance, but may fix issues with permission-based price
modifiers. This feature requires ShopGUI+ version 1.87.0 or newer.

Add following entry to the bottom of your `config.yml` file:

```yaml
disablePermissionCache: true
```
