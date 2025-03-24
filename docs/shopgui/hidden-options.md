# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with ShopGUI+ on some setups, along with provide additional behavior to the plugin, that may be potentially dangerous.

## Click Cooldown
Using the `clickCooldown` option can change the time allowed between clicks in the GUI in milliseconds.

 <p class="error"><b>WARNING:</b> This setting is dangerous. This is used to prevent duplication bugs, and is set to 250ms to prevent this. Removing this cooldown can harm chances of duplication. </p>

 This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
 ```yaml
 gui:
   # The default value for this is "250".
   clickCooldown: 250
   ```
Any decimal number can be inserted into this value, as long as it lies within the bounds of $-2^{63}$ and $2^{63}-1$

## Button Slots
Using the `slots` option instead of the default `slot` option allows you to specify multiple slots for a single item. This can be used to add the same item to multiple slots within the GUI. 

It is also worth noting that such an option is only available for the `goBack`, `previousPage` and `nextPage` buttons within the [`config.yml`](https://pastebin.com/KiM3PjU7)

See below for an example of how this might be used:
```yaml
buttons:
  # "Go back button"
  goBack:
    item:
      # Material name, full list can be found here: https://docs.brcdev.net/#/materials
      material: BARRIER
      # Amount of the item
      amount: 1
      # (optional) Data value, for example 1 for WOOD:1 means spruce wood planks
      damage: 0
      # (optional) Custom name
      name: "&c&lGo back to categories"
      # (optional) Lore, can contain multiple lines
      lore:
        - "&7Click here to return"
        - "&7to the main menu"
    # Slot in each shop's GUI
    slots:
      - 49
      - 50
      - 51
```

<p class="error"><b>WARNING:</b> This setting can clash with the already existing `slot` option. Remove this entirely if you wish to use the `slots` option.</p>

## Enforce Default Stack Size
If you would like to bypass Minecraft's default stack sizes for certain items (such as armour, tools and potions), you can make use of the `enforceDefaultStackSize` setting. This will allow purchased items in the shop to bypass the limit, allowing you to purchase more than one of these items, and keep them in the same inventory slot. 

<p class="error"><b>WARNING:</b> This setting circumvents typical Minecraft behavior. While this specific use-case has not seen any issues within servers, it cannot be guaranteed that changing this setting will not cause issues. </p>

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
# The default value for this key is "true".
enforceDefaultStackSize: true
```

It is also worth noting that this is essentially the "stacked" option set to `true` for every shop as default. This can be seen [here.](https://docs.brcdev.net/#/shopgui/stack-size?id=stacked)

## Permission Cache
In order to aid server performance, permission nodes are cached temporarily within ShopGUIPlus. If you wind this causes issues with your price modifiers, you can try disabling it.

<p class="error"><b>WARNING:</b> Changing this setting can negatively affect server performance, as checks must be done as and when needed, instead of being retrieved from a cache. This setting also required ShopGUI+ version 1.87.0 or higher to be used.</p>

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
# The default value for this key is "false".
disablePermissionCache: false
```

## Close GUI On Click
This option can be used to close the GUI as soon as an item within the GUI is selected. It is worth noting that such an option is primarily intended for dummy items, but can be used on any item. 

This can be used within any shop item within any shop file, by inserting the following:
```yaml
armor:
  name: "&4&lArmor (page %page%)"
  fillItem:
    material: BLACK_STAINED_GLASS_PANE
    name: " "
  items:
    1:
      type: item
      item:
        material: LEATHER_HELMET
        quantity: 1
      buyPrice: 100
      sellPrice: 100
      slot: 10
      # There is no default value for this. This is a hidden option entirely.
      closeGuiOnClick: true
```

It is worth noting that the `closeGuiOnClick` option only needs to be suffixed within the shop item. There is no need to insert the entire section into your config file. This is only an exemplar.

This option has also been documented [here.](https://docs.brcdev.net/#/shopgui/faq?id=adding-buttons-to-close-currently-open-gui)