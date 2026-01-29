# Commands & permissions

<p class="warn"><b>Tip:</b> Typically players need both <i>shopguiplus.shop</i> and <i>shopguiplus.shops.*</i
> permissions to access all shops.</p>

## Commands

| Command                                                                   | Description                                                          | Required permission                                       |
|---------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------------------------------------------|
| /shop                                                                     | Open the main shop menu                                              | shopguiplus.shop                                          |
| /sell hand [quantity]                                                     | Sell the item held in your hand                                      | shopguiplus.sell.hand                                     |
| /sell handall                                                             | Sell all inventory items the same as the one held in your hand       | shopguiplus.sell.hand.all                                 |
| /sell all [shop]                                                          | Sell all items from your inventory                                   | shopguiplus.sell.all                                      |
| /sell all [shop/all] [player]                                             | Sell all items from the player's inventory. Use 'all' for all shops. | shopguiplus.sell.all.others                               |
| /shop reload                                                              | Reload the configuration                                             | shopguiplus.reload                                        |
| /shop check                                                               | Get information on the item held in hand                             | shopguiplus.check                                         |
| /shop worth                                                               | Check the sale value of held item                                    | shopguiplus.worth                                         |
| /shop [shop name] [page]                                                  | Directly open the specified shop                                     | shopguiplus.shops.SHOP_ID (see **Permissions** paragraph) |
| /shop [player]                                                            | Directly open the main menu for the player                           | shopguiplus.others                                        |
| /shop [player] [shop name] [page]                                         | Open the specified shop to the specified player                      | shopguiplus.others                                        |
| /shop addmodifier item \<player\> \<shop\> \<item\> \<value\> [buy\|sell] | Add item-specific price modifier                                     | shopguiplus.shop.addmodifier                              |
| /shop addmodifier shop \<player\> \<shop\> \<value\> [buy\|sell]          | Add shop-specific price modifier                                     | shopguiplus.shop.addmodifier                              |
| /shop addmodifier global \<player\> \<value\> [buy\|sell]                 | Add global price modifier                                            | shopguiplus.shop.addmodifier                              |
| /shop resetmodifier item \<player\> \<shop\> \<item\> [buy\|sell]         | Reset player's item-specific price modifier                          | shopguiplus.shop.resetmodifier                            |
| /shop resetmodifier shop \<player\> \<shop\> [buy\|sell]                  | Reset player's shop-specific price modifier                          | shopguiplus.shop.resetmodifier                            |
| /shop resetmodifier global \<player\> [buy\|sell]                         | Reset player's global price modifier                                 | shopguiplus.shop.resetmodifier                            |
| /shop checkmodifiers \<player\>                                           | Check player's current price modifiers                               | shopguiplus.shop.checkmodifiers                           |

## Permissions

All command permissions have been listed above. However, players need additional permissions to access each shop.

You can give or revoke access to particular shops by using the `shopguiplus.shops.SHOP_ID` permission node (
eg. `shopguiplus.shops.food`, `shopguiplus.shops.armor` etc.).

Wildcard permission node `shopguiplus.shops.*` can be used only if you use LuckPerms, PEX or another permission 
plugin that supports it. Otherwise, you have to give explicit permissions to access each shop.

To ban players from accessing a particular shop, negate the corresponding permission node.

Additional permissions:

| Permission                 | Description                                       | Default for players |
|----------------------------|---------------------------------------------------|---------------------|
| shopguiplus.bypassgamemode | Allows to access the shop when in banned gamemode | false               |
| shopguiplus.bypassworld    | Allows to access the shop when in banned world    | false               |
| shopguiplus.buymore        | Allows to use the "Buy more" feature              | true                |
| shopguiplus.sellmore       | Allows to use the "Sell more" feature             | true                |
