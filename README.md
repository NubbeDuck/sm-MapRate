# sm-MapRate
Allow players to rate a map between 1-5, inclusive, and view the current rating.


Configuration
- maprate_db_config (default "default")
  Specifies what configuration in addons/sourcemod/configs/database.cfg to use to connect to a MySQL or SQLite DB.
- maprate_allow_revote (default "1")
  When non-zero, this allows players to change their existing map rating (recommended). When zero, players cannot rate a map more than once.
- maprate_autorate_time (default "0")
  When non-zero, this specifies the time to wait since the player started playing the map before automatically asking the player to rate the map when they die (and only   if they haven't rated the map before). For example, if maprate_autorate_time is 180, the plugin will start asking players who die to rate the map 3 minutes after the     player starts playing the map. The behavior of this cvar was changed in v0.10.
- maprate_autorate_delay (default "5")
  When maprate_autorate_time is enabled, Map Rate will wait maprate_autorate_delay seconds after a player dies before asking them to rate the map. This is useful if you   have another plugin that displays information to a player when they die (e.g. stats) that could interfere with Map Rate.
- maprate_table (default "map_ratings")
  The name of the database table to store map ratings in. If you run multiple servers, you may want to change this for different game types or for individual servers,     depending on whether you servers share databases and whether you want maprating data shared across multiple servers.
- maprate_dismiss (default "0")
  If non-zero, a "Dismiss" option will be added to the menu as option #1 (instead of "1 Star"). Changes to this cvar take effect on every map change, not instantly.
- maprate_autoresults (default "1")
  If non-zero, the graph of a map's rating are automatically displayed to a player after the player rates a map.

Commands
!maprate
  This in-game chat trigger will display the Rate Map menu.

  After rating the map, the current rating will be displayed, complete with a nice little histogram (new since v0.6):

!maprating
  This in-game chat trigger will display the in-game rating viewing tool (new since v0.6):

sm_maprate_resetratings (or !maprate_resetratings)
  Delete ratings for the current map. Requires the admin vote flag ("k").

Also accessible via the admin menu is the "Have All Players Rate This Map" command


Credits to this post https://forums.alliedmods.net/showthread.php?t=164455
I just updated the syntax and got it working after
