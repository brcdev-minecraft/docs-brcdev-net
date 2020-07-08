# Price modifiers
The plugin supports two types of price modifiers - command- and permission-based. You can choose one of them or run
 both (in the `priceModifiersType` setting in your `config.yml`).


In case of using both the order of price modifier check is following:
1. Command modifiers - Global
1. Command modifiers - Shop
1. Command modifiers - Shop Item
1. Permission modifiers - Global
1. Permission modifiers - Shop
1. Permission modifiers - Shop Item

eg. when player has a shop command modifier and a global permission modifier, the second one overrides.

When using only one of the types the order is similar:
1. Global
1. Shop
1. Shop Item


## Command-based price modifiers 
Command-based price modifiers are entirely handled by commands. You can find them [here](shopgui/commands-permissions).

## Permission-based price modifiers 
The permission-based price modifiers can be configured inside the pricemodifiers.yml config file. 

Each price modifiers requires the player to have a permission in format of shopguiplus.pricemodifiers.<PRICE MODIFIER ID>, eg. shopguiplus.pricemodifiers.example1.

### Global modifiers 
```yaml
priceModifiers:
  #Global price modifier with ID example1, 200% of buy & sell price, permission: shopguiplus.pricemodifiers.example1
  example1:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: GLOBAL
    #Valid types: BOTH, BUY, SELL
    type: BOTH
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 2.0
```

### Shop modifiers 
```yaml
priceModifiers:
  #Food shop price modifier with ID example2, 150% of buy & sell price, permission: shopguiplus.pricemodifiers.example2
  example2:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: SHOP
    #Valid types: BOTH, BUY, SELL
    type: BOTH
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 1.5
    #Shop ID (from shops.yml, case insensitive)
    shop: food
```

### Shop item modifiers 
```yaml
  #Item "1" from food shop price modifier with ID example3, 300% of buy price, permission: shopguiplus.pricemodifiers.example3
  example3:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: ITEM
    #Valid types: BOTH, BUY, SELL
    type: BUY
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 3.0
    #Shop ID (from shops.yml, case insensitive)
    shop: food
    #Shop item ID (from shops.yml, case insensitive)
    shopItem: 1
```


## Example config file
Example `pricemodifiers.yml` file showing all three scopes combined: 
```yaml
priceModifiers:
  #Global price modifier with ID example1, 200% of buy & sell price, permission: shopguiplus.pricemodifiers.example1
  example1:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: GLOBAL
    #Valid types: BOTH, BUY, SELL
    type: BOTH
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 2.0
  #Food shop price modifier with ID example2, 150% of buy & sell price, permission: shopguiplus.pricemodifiers.example2
  example2:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: SHOP
    #Valid types: BOTH, BUY, SELL
    type: BOTH
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 1.5
    #Shop ID (from shops.yml, case insensitive)
    shop: food
  #Item "1" from food shop price modifier with ID example3, 300% of buy price, permission: shopguiplus.pricemodifiers.example3
  example3:
    #Valid scopes: GLOBAL, SHOP, ITEM
    scope: ITEM
    #Valid types: BOTH, BUY, SELL
    type: BUY
    #Modifier value, 1.0 = 100%, 2.0 = 200% etc.
    value: 3.0
    #Shop ID (from shops.yml, case insensitive)
    shop: food
    #Shop item ID (from shops.yml, case insensitive)
    shopItem: 1
```