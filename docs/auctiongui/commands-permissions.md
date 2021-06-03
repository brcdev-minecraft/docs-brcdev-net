# Commands & permissions
## Commands
| Command                                              | Description                           | Required permission           |
|------------------------------------------------------|---------------------------------------|-------------------------------|
| /auc                                                 | Open the main auction menu            | auctionguiplus.auction        |
| /auc \<player\>                                        | Open the main auction menu for player | auctionguiplus.others         |
| /auc bid \<auction ID\> [amount]                     | Place a bid                           | auctionguiplus.auction.bid    |
| /auc reload                                          | Reload the configuration              | auctionguiplus.auction.reload |
| /auc start [quantity] [price] [increment] [duration] | Start an auction                      | auctionguiplus.auction.start  |
| /bid \<auction ID\> [amount]                         | Place a bid                           | auctionguiplus.auction.bid    |

## Permissions

All command permissions have been listed above. 

Furthermore, there are some extra permissions:

| Permission node                | Description                                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| auctionguiplus.cancelothers    | Allows to cancel other players' auctions with middle mouse button from auctions view |
| auctionguiplus.bypassgamemode  | Allows to access auctions when in one of the banned gamemodes                        |
| auctionguiplus.bypassworld     | Allows to access auctions when in one of the banned worlds                           |
