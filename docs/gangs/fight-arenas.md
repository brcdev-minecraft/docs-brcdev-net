# Adding new fight arenas

1. Open the `arenas.yml` file.
1. Set the arena name in your config to whatever you want.
1. Choose two opposite corners of the arena (players won't be able to leave it during the fight). I marked my corners
   with sea lanterns which will be destroyed later:
   <img src="https://i.imgur.com/OMWrLHv.png" />
1. Stand in the first corner and write down `x`, `y` and `z` values from the debug screen (toggle it with F3) to
   the `corner1`
   section your config. Yaw and pitch don't matter for corners so just set it both to zeros. You can round the decimal
   part down/up to .0 or .5.
   <img src="https://i.imgur.com/z21F4he.png" />
1. Go to the second (opposite) corner and repeat it but save it in your config as `corner2`.
   <img src="https://i.imgur.com/BbL823a.png" />
1. Now we will add team spawns. Stand where you want the first gang to spawn and write down `x`, `y`, `z`, `yaw` and
   `pitch` (yaw and pitch are marked on the screenshot, first one is yaw and the second one is pitch) to `spawn1`
   section in your config.
   <img src="https://i.imgur.com/jLyDF3e.png" />
1. Repeat it for the second spawn but save it as `spawn2`.
   <img src="https://i.imgur.com/RaeJStG.png" />
1. We're done with arena configuration, the arena will be ready to use after you restart the server. Here is our final
   arenas config:

```yaml
arenas:
#Each arena has to be a different section with unique ID so you can just name them 1, 2, 3 etc. This ID won't be shown anywhere.
  1:
    #Arena's name
    name: "Example arena"
    #Two corners of arena, players won't be able to go behind them, yaw and pitch don't matter
    corner1:
      world: "world"
      x: 423
      y: 3
      z: 761
      yaw: 0
      pitch: 0
    corner2:
      world: "world"
      x: 433
      y: 6
      z: 784
      yaw: 0
      pitch: 0
    #Spawn of players from the first gang
    spawn1:
      world: "world"
      x: 428.5
      y: 3
      z: 764.0
      yaw: 0
      pitch: 0
    #Spawn of players from the second gang
    spawn2:
      world: "world"
      x: 428.5
      y: 3
      z: 781.5
      yaw: 180
      pitch: 0
```