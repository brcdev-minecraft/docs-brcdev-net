# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with ShopGUIPlus on some setups, along with provide additional behaviour to the plugin, that may be potentially dangerous.

## Click Cooldown
Using the `clickCooldown` option can change the time allowed between clicks in the GUI in milliseconds.

 **WARNING:** This setting is dangerous. This is used to prevent duplication bugs, and is set to 250ms to prevent this. Removing this cooldown can harm changes of duplication. 

 To make use of this option, insert the following anywhere in your configuration file:
 ```yaml
 gui:
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

**WARNING:** This setting can clash with the already existing `slot` option. Remove this entirely if you wish to use the `slots` option.

## Enforce Default Stack Size
If you would like to bypass Minecraft's default stack sizes for certain items (such as armour, tools and potions), you can make use of the `enforceDefaultStackSize` setting. This will allow purchased items in the shop to bypass the limit, allowing you to purchase more than one of these items, and keep them in the same inventory slot. 

**WARNING:** This setting circumvents typical Minecraft behavior. While this specific use-case has not seen any issues within servers, it cannot be guaranteed that changing this setting will not cause issues. 

To use this setting, insert the following anywhere within your configuration file:
```yaml
# The default value for this key is "true".
enforceDefaultStackSize: true
```

It is also worth noting that this is essentially the "stacked" option set to `true` for every shop as default. This can be seen [here.](https://docs.brcdev.net/#/shopgui/stack-size?id=stacked)

## Permission Cache
In order to aid server performance, permission nodes are cached temporarily within ShopGUIPlus. If you wind this causes issues with your price modifiers, you can try disabling it.

**WARNING:** Changing this setting can negatively affect server performance, as checks must be done as and when needed, instead of being retrieved from a cache. This setting also required ShopGUI+ version 1.87.0 or higher to be used.

To use this setting, insert the following anywhere within your configuration file:
```yaml
# The default value for this key is "false".
disablePermissionCache: false
```

## Number Formatting
We provide several options which allow you to change the way numbers are formatted in messages sent to players. These have been shown below:

### Decimal Separation
This setting can be used to change the character used for separating decimals in figures which may not be integers. This is useful for other languages, who may use different characters for decimal separation. (E.g: Spain uses the comma to separate decimals.)

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "."
  decimalSeparator: '.'
```

### Grouping Separation
This setting can be used to change the character used for separating groups of numbers for larger numbers. (E.g: 1,000,000) This is useful for other languages, who may use different characters for grouping separation. (E.g: Spain uses the decimal point to separate such groups.)

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is ","
  groupingSeparator: ','
```

### Maximum Integer Digits
This setting allows you to specify the maximum number of digits shown for integer numbers. This can help display larger amounts of currency, in cases where the economy may be more inflated. 

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "32"
  maximumIntegerDigits: 32
```

### Minimum Integer Digits
This setting allows you to specify the minimum number of digits shown for integer numbers. This can help display smaller amounts of currency, in cases where the economy may be more deflationary.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "1"
  minimumIntegerDigits: 1
```
### Maximum Fraction Digits
This setting allows you to specify the maximum number of decimal places shown for fractional numbers. This can help display currency amounts more precisely.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "8"
  maximumFractionDigits: 8
```

### Minimum Fraction Digits
This setting allows you to specify the minimum number of decimal places shown for fractional numbers. This can help display currency amounts less accurately, should the need arise. 

This can be changed by inserting the following setting in the ['config.yml'](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "1"
  minimumFractionDigits: 1
```

### Hide Fraction
This setting will allow you to specify whether you would like the ending decimal digits to be removed when not applicable. This will allow for messages to be displayed as $100, instead of $100.00.

This can be changed by inserting the following setting in the ['config.yml'](https://pastebin.com/KiM3PjU7):
```yaml
numberFormat:
  # The default value for this is "true".
  hideFraction: true
```