# Discord-Widget-API
A simple PHP library to create your own custom discord widget. You can do things like display your channel l ist, members online, members count, get a users mic status, and more! Create your own widget with this simple API! :)

Right click the server name in Discord at the top left and click "Copy ID". Paste it where it says SERVER_ID.

Requires:
- cURL Library

Usage:

```PHP
<?php
include 'class.discord.php';

$discord = new Discord("SERVER_ID");
$discord->fetch();

$server_title = $discord->getServerTitle();
$channel_list = $discord->getChannels();
$member_list = $discord->getMembers();
$member_count = $discord->getMemberCount();
```


#### How to get a channel list and the members in each channel:

```PHP
foreach ($channel_list as $channel) {
  $inChannel = $discord->getMembersInChannel($channel->id);
  echo '- '.$channel->name;
  foreach($inChannel as $member) {
    echo '--- '.$member->username;  
  }
}
```
#### Dumping data to get more detailed information:

```PHP
var_dump($discord->getRawData());
```
