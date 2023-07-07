# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with PlayerShopGUI+ on some setups, along with provide additional behavior to the plugin, that may be potentially dangerous.

## Item Name Capitalization
By default, PlayerShopGUI+ will automatically capitalize the names of all items.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):

```yaml
# The default value for this key is "true". 
capitalizeItemNames: true
```

## Number Formatting
We provide several options which allow you to change the way numbers are formatted in messages sent to players. These have been shown below:

### Decimal Separation
This setting can be used to change the character used for separating decimals in figures which may not be integers. This is useful for other languages, who may use different characters for decimal separation. (E.g: Spain uses the comma to separate decimals.)

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "."
  decimalSeparator: '.'
```

### Grouping Separation
This setting can be used to change the character used for separating groups of numbers for larger numbers. (E.g: 1,000,000) This is useful for other languages, who may use different characters for grouping separation. (E.g: Spain uses the decimal point to separate such groups.)

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is ","
  groupingSeparator: ','
```

### Maximum Integer Digits
This setting allows you to specify the maximum number of digits shown for integer numbers. This can help display larger amounts of currency, in cases where the economy may be more inflated. 

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "32"
  maximumIntegerDigits: 32
```

### Minimum Integer Digits
This setting allows you to specify the minimum number of digits shown for integer numbers. This can help display smaller amounts of currency, in cases where the economy may be more deflationary.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "1"
  minimumIntegerDigits: 1
```
### Maximum Fraction Digits
This setting allows you to specify the maximum number of decimal places shown for fractional numbers. This can help display currency amounts more precisely.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "8"
  maximumFractionDigits: 8
```

### Minimum Fraction Digits
This setting allows you to specify the minimum number of decimal places shown for fractional numbers. This can help display currency amounts less accurately, should the need arise. 

This can be changed by inserting the following setting in the ['config.yml'](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "1"
  minimumFractionDigits: 1
```

### Hide Fraction
This setting will allow you to specify whether you would like the ending decimal digits to be removed when not applicable. This will allow for messages to be displayed as $100, instead of $100.00.

This can be changed by inserting the following setting in the ['config.yml'](https://pastebin.com/vFT034vE):
```yaml
numberFormat:
  # The default value for this is "true".
  hideFraction: true
```

## Cancel Word
This setting will allow you to change the word used when attempting to cancel the search of an item. This is especially useful for servers based in other languages, who may not use English as their primary language. 

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
# The default value for this is "cancel"
cancelWord: "cancel"
```

## Spawner Provider
If you make use of multiple spawner plugins (for whatever reason) then you can make use of this option to forcefully select a spawner plugin to handle spawners within PlayerShopGUIPlus. 

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):
```yaml
# You will need to insert the name of the spawner plugin/spawner provider within this key.
# No default value, as many servers will use many different spawner plugins. 
spawnerProvider: ""
```

<p class="error"><b>WARNING:</b> There is little to no need to make use of this option at all. Very few/no servers hold multiple spawner plugins and as such, PlayerShopGUIPlus will automatically handle this for you. You will typically not need to make use of this setting yourself and its use is not recommended. 