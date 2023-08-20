# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with PlayerShopGUI+ on some setups, along with provide additional behavior to the plugin, that may be potentially dangerous.

## Item Name Capitalization
By default, PlayerShopGUI+ will automatically capitalize the names of all items.

This can be changed by inserting the following setting in the [`config.yml`](https://pastebin.com/vFT034vE):

```yaml
# The default value for this key is "true". 
capitalizeItemNames: true
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

<p class="error"><b>WARNING:</b> There is little to no need to make use of this option at all. Very few/no servers hold multiple spawner plugins and as such, PlayerShopGUIPlus will automatically handle this for you. You will typically not need to make use of this setting yourself and its use is not recommended. </p>