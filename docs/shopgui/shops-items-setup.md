# Adding shops & items

## Adding new shops
First, head to the `/plugins/ShopGUIPlus/shops/` directory. You can find all default and previously added shops in there
. Each file is responsible for a single shop. 

This is an example of `armor.yml` file:
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
  items:
    1:
      type: item
      item:
        material: LEATHER_HELMET
        quantity: 1
      buyPrice: 40
      sellPrice: 8
      slot: 10
    2:
      type: item
      item:
        material: GOLD_HELMET
        quantity: 1
      buyPrice: 160
      sellPrice: 32
      slot: 11
```


As you can see, first of all you have to define the id of the shop (has to be unique, you will refer to it later in the main config). This name must also match the file's name (armor.yml and armor in here):
```yaml
armor:
```


Now you have to set the displayed name of the shop which will be visible in the GUI:
```yaml
armor:
  name: "&4&lArmor (page %page%)"
```

You can also set fill item for the entire shop, a gray glass pane in this case:
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
```


Then you can proceed to adding new items. You need '''items''' section with the same indentation as previously added '''name'''.
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
  items:
```


Now, to add an item you have to create another section with higher indentation. Name it whatever you want (only alphanumeric characters), just remember the names have to be unique for each item. Then you have to add the '''type''' of the shop item. Valid types are item, permission, enchantment, command or dummy.
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
  items:
    1:
      type: item
```


Next you have to add the item meta like material, quantity etc. For more information on item meta please refer to the [Item meta](item-meta) page.
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
  items:
    1:
      type: item
      item:
        material: LEATHER_HELMET
```


Finally, you can proceed to basic information like buy/sell price and GUI slot number. Setting buyPrice or sellPrice to -1 will result in unbuyable/unsellable item. Remember that slot numbers go from 0 to 53.
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: STAINED_GLASS_PANE
    damage: 15
    name: " "
  items:
    1:
      type: item
      item:
        material: LEATHER_HELMET
        quantity: 1
      buyPrice: 40
      sellPrice: 8
      slot: 10
```


Now you have to add the shop to the main menu, otherwise players couldn't access it. Open the config.yml and proceed to shopMenuItems section. You can see there all previously added shops. 

```yaml
shopMenuItems:
  # Has to be unique, value doesn't matter
  1:
    item:
      # The same rules apply for material, amount, damage and lore as for goBackButton
      material: DIAMOND_CHESTPLATE
      quantity: 1
      name: "&4&lArmor"
    # Shop ID from shop yaml
    shop: "armor"
    # Slot in shops menu, counting from 0 to 53
    slot: 15
``` 


We're done with our first shop. If you have any questions or errors please contact us at [our Discord server](https://discord.brcdev.net).

## Adding items to shops 

Now we want to add some more items to previously created shop. Let's start from what we've got at the end of the previous tutorial section.
```yaml
food:
  #Shop inventory name
  name: "&5Food Shop" 
  items:
    #Has to be unique for each of items, value doesn't matter
    1: 
      type: item
      item:
        #Material name, full list can be found here: https://docs.brcdev.net/#/materials
        material: BREAD 
        #(optional) Quantity of the item
        quantity: 32
        #(optional) Data value, for example 1 for WOOD:1 means spruce wood planks
        damage: 0 
        #(optional) Custom name
        name: "&aYummy bread"
        #(optional) Lore, can contain multiple lines
        lore: 
          - "&3<3"
      #Buy price, lower than 0 means you can't buy it, 0 mean free, higher than 0 is regular value
      buyPrice: -1
      #Same as above but sell price
      sellPrice: 25 
      #Slot in shop's inventory, counting from 0 to 53
      slot: 0
```


In order to add more items, you have to add more sections as section named '''1''' in this case. Remember all sections have to have unique names, so you can just call them 1, 2, 3, 4... etc.
```yaml
food:
  #Shop inventory name
  name: "&5Food Shop" 
  items:
    #Has to be unique for each of items, value doesn't matter
    1: 
      type: item
      item:
        #Material name, full list can be found here: https://docs.brcdev.net/#/materials
        material: BREAD 
        #(optional) Quantity of the item
        quantity: 32
        #(optional) Data value, for example 1 for WOOD:1 means spruce wood planks
        damage: 0 
        #(optional) Custom name
        name: "&aYummy bread"
        #(optional) Lore, can contain multiple lines
        lore: 
          - "&3<3"
      #Buy price, lower than 0 means you can't buy it, 0 mean free, higher than 0 is regular value
      buyPrice: -1
      #Same as above but sell price
      sellPrice: 25 
      #Slot in shop's inventory, counting from 0 to 53
      slot: 0
    2: 
```


Then just repeat steps from the previous tutorial section, add the type, item, prices and slot number:
```yaml
food:
  #Shop inventory name
  name: "&5Food Shop" 
  items:
    #Has to be unique for each of items, value doesn't matter
    1: 
      type: item
      item:
        #Material name, full list can be found here: https://docs.brcdev.net/#/materials
        material: BREAD 
        #(optional) Quantity of the item
        quantity: 32
        #(optional) Data value, for example 1 for WOOD:1 means spruce wood planks
        damage: 0 
        #(optional) Custom name
        name: "&aYummy bread"
        #(optional) Lore, can contain multiple lines
        lore: 
          - "&3<3"
      #Buy price, lower than 0 means you can't buy it, 0 mean free, higher than 0 is regular value
      buyPrice: -1
      #Same as above but sell price
      sellPrice: 25 
      #Slot in shop's inventory, counting from 0 to 53
      slot: 0
    2:
      type: item
      item:
        material: COOKED_RABBIT
        quantity: 10
        damage: 0
      buyPrice: 75.5
      sellPrice: -1
      slot: 1
```

We're done with the second item. You can add up to 54 items to each shop this way.

### Items
Pickaxe with custom name & Efficiency I
```yaml
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
```


Firework
```yaml
      1:
        type: item
        item:
          material: FIREWORK
          quantity: 32
          damage: 0
          fireworkPower: 2
          fireworkEffects:
            1:
              type: BALL_LARGE
              colors:
               - YELLOW
               - ORANGE
            2:
              type: CREEPER
              colors:
               - YELLOW
               - ORANGE
        buyPrice: 10
        sellPrice: -1
        slot: 0
```

### Custom items

#### HeadDatabase
Head from HeadDatabase with ID `1734`
```yaml
      1:
        type: item
        item:
          headDatabase: 1234
        buyPrice: 50
        sellPrice: 25
        slot: 0
```


### Mob spawners 

<p class="warn"><b>Note:</b> Remember to use valid material name corresponding to your Minecraft version (<i>SPAWNER
</i> or <i>MOB_SPAWNER</i>).</p> 

The `mob` entry has to represent a valid entity name. [List of all entity types](entity-types)

Pig spawner with a custom name
```yaml
      1:
        type: item
        item:
          material: SPAWNER
          mob: PIG
          name: "&dPig spawner"
          quantity: 1
        buyPrice: 10
        sellPrice: -1
        slot: 0
```

5 blaze spawners
```yaml
      2:
        type: item
        item:
          material: SPAWNER
          mob: BLAZE
          quantity: 5
        buyPrice: 10
        sellPrice: -1
        slot: 1
```

#### Enchantments
Fortune II
```yaml
      1:
        type: enchantment
        enchantment: FORTUNE
        enchantmentLevel: 2
        item:
          material: DIAMOND_PICKAXE
          quantity: 1
          name: "&8Fortune II"
          enchantments:
            - FORTUNE:2
        buyPrice: 50
        slot: 0
```

Knockback I
```yaml
      1:
        type: enchantment
        enchantment: KNOCKBACK
        enchantmentLevel: 1
        item:
          material: DIAMOND_SWORD
          quantity: 1
          name: "&6Knockback I"
        buyPrice: 1000
        slot: 1
```



### Permissions 
Single permission `essentials.msg` valid in all worlds
```yaml
      1:
        type: permission
        permission: "essentials.msg"
        item:
          material: STONE_PICKAXE
          quantity: 1
          name: "&8/msg permission"
          enchantments:
            - EFFICIENCY:1
            - FORTUNE:2
        buyPrice: 50
        sellPrice: 25
        slot: 0
```

Multiple permissions `essentials.msg` and `essentials.afk` valid in all worlds
```yaml
      2:
        type: permission
        permissions: 
          - "essentials.me"
          - "essentials.afk"
        item:
          material: DIAMOND_PICKAXE
          quantity: 1
          name: "&aPermission to use /me"
        buyPrice: 1000
        sellPrice: 500
        slot: 1
```

Multiple permissions `essentials.balance` and `essentials.balance.others` valid only in specific worlds
```yaml
      2:
        type: permission
        permissions: 
          1:
            permission: "essentials.balance"
            world: "world"
          2:
            permission: "essentials.balance.others"
            world: "world_nether"
        item:
          material: DIAMOND_PICKAXE
          quantity: 1
          name: "&aPermission to use /me"
        buyPrice: 1000
        sellPrice: 500
        slot: 1
```


### Commands 
/say Hello [player name]!
```yaml
    items:
      1:
        type: command
        item:
          material: WOOL
          quantity: 32
          damage: 0
        commands: 
          - "say Hello, %PLAYER%!"
        buyPrice: 500
        slot: 0
```


/say Good bye [player name]!
/msg [player name] See you later!
```yaml
      2:
        type: command
        item:
          material: WOOL
          quantity: 32
          damage: 1
        commands: 
          - "say Good bye, %PLAYER%!"
          - "msg %PLAYER% See you later!"
        buyPrice: 100
        slot: 1
```


## Amount selection GUI customization 
You can change every part of the amount selection GUI in the config. You can change items/slots, hide buttons etc.

All necessary settings are included in the `amountSelectionGUI` section of config.yml:

```yaml
amountSelectionGUI:
  #Size of the GUI, valid values are 9, 18, 27, 36, 45 and 54
  size: 54
  #Slot of the item being bought/sold
  itemSlot: 22
  #Buttons
  buttons:
    #"Set to 1" button
    set1:
      item:
        material: STAINED_GLASS_PANE
        quantity: 1
        damage: 14
        name: "&c&lSet to 1"
      slot: 18
    #"Remove 10" button
    remove10:
      item:
        material: STAINED_GLASS_PANE
        quantity: 10
        damage: 14
        name: "&c&lRemove 10"
      slot: 19
    #"Remove 1" button
    remove1:
      item:
        material: STAINED_GLASS_PANE
        quantity: 1
        damage: 14
        name: "&c&lRemove 1"
      slot: 20
    #"Add 1" button
    add1:
      item:
        material: STAINED_GLASS_PANE
        quantity: 1
        damage: 5
        name: "&a&lAdd 1"
      slot: 24
    #"Add 10" button
    add10:
      item:
        material: STAINED_GLASS_PANE
        quantity: 10
        damage: 5
        name: "&a&lAdd 10"
      slot: 25
    #"Set to 64" button
    set64:
      item:
        material: STAINED_GLASS_PANE
        quantity: 64
        damage: 5
        name: "&c&lSet to 64"
      slot: 26
    #"Confirm" button
    confirm:
      item:
        material: STAINED_GLASS
        quantity: 1
        damage: 5
        name: "&a&lConfirm"   
      slot: 39
    #"Sell all" button
    sellAll:
      item:
        material: STAINED_GLASS
        quantity: 1
        damage: 5
        name: "&a&lSell all"      
      slot: 40
    #"Cancel" button      
    cancel:
      item:
        material: STAINED_GLASS
        quantity: 1
        damage: 14
        name: "&c&lCancel"  
      slot: 41
```


In order to change the button item you have to edit the appropriate entry. 

Setting the slot to `-1` will result in the button being hidden.


## Changing sizes/buttons of shops 
You can change the size of any shop as well as next/previous page/go back button slots. 

Just change/add the `size` entry to any of the shops yaml:
```yaml
food:
  #Shop inventory name
  name: "&5Food Shop (page %page%)" 
  #(Optional) Shop inventory size (valid values are 9, 18, 27, 36, 45 and 54)
  size: 45
```

<p class="warn"><b>Note:</b> Sometimes it might be necessary to adjust the button slots in each shop
 according to the instructions below, if the target inventory size is too small.</p> 

These global settings from `config.yml` apply to every shop unless you override the item/slot/both for a specific shop:
```yaml
buttons:
  #"Go back button"
  goBack:
    item:
      #Material name, full list can be found here: https://docs.brcdev.net/#/materials
      material: NETHER_STAR 
      #Amount of the item
      amount: 1 
      #(optional) Data value, for example 1 for WOOD:1 means spruce wood planks
      damage: 0 
      #(optional) Custom name
      name: "&cBack to categories" 
      #(optional) Lore, can contain multiple lines
      lore: 
        - "&aClick here to return to the main menu"
    #Slot in each shop's GUI
    slot: 49 
  #"Previous page" button
  previousPage:
    item:
      material: PAPER
      quantity: 1
      name: "&e&lPrevious page"
    slot: 45
  #"Next page" button
  nextPage:
    item:
      material: PAPER
      quantity: 1
      name: "&e&lNext page"
    slot: 53
```

You can edit them for any shop using the same entry names/indentation:
```yaml
food:
  #Shop inventory name
  name: "&5Food Shop (page %page%)" 
  #(Optional) Shop inventory size (valid values are 9, 18, 27, 36, 45 and 54)
  size: 45
  #(Optional) Changed button types/slots
  buttons:
    goBack:
      #Slot -1 means it's hidden
      slot: 40
    previousPage:
      #You can change the item as well
      item:
        material: INK_SACK
        quantity: 1
        damage: 15
      slot: 36
    nextPage:
      slot: 44
```


You can edit only the item or slot or both as well.

## Using per item permissions
First, you have to add the `enablePerItemPermissions: true` entry to your shop in the shop yaml:
```yaml
mining:
  name: "&2Mining Shop (page %page%)"
  enablePerItemPermissions: true
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
      buyPrice: 1000
      sellPrice: 500
      slot: 1
      unstack: true
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

Then you have to give your players appropriate permissions. The format of permissions is `shopguiplus.item.<shop id>.<item id>`.

The item ID is this number:
```yaml
    items:
      1:
```

For instance, permissions for these 3 items in shop above would be `shopguiplus.item.mining.1`, `shopguiplus.item.mining.2` and `shopguiplus.item.mining.3`.

You can use `shopguiplus.item.<shop id>.*` wildcard permission (eg. `shopguiplus.item.mining.*`) to give access to all items within particular shop.


## Setting per-shop economy
In order to use another economy within a single shop, set the economy field in shop's yml to the economy name:
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  economy: EXP
  fillItem:
    material: BLACK_STAINED_GLASS_PANE
    name: " "
  items:
    1:
      type: item
      item:
        material: LEATHER_HELMET
        quantity: 1
      buyPrice: 40
      sellPrice: 8
      slot: 10
``` 

Make sure all of used economies are enabled in config.yml:
```yaml
economyTypes:
  - VAULT
  - EXP
``` 