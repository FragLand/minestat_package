# minestat_package
PHP/Packagist/composer package for [MineStat](https://github.com/FragLand/minestat)

### PHP example

**Note:** MineStat for PHP requires multi-byte string support to handle character encoding conversion. Enabling `mbstring` support can be as simple as installing the `php-mbstring` package for your platform. If building PHP from source, see https://www.php.net/manual/en/mbstring.installation.php. To validate, `phpinfo()` output will reference `mbstring` if the feature is enabled.

```php
<?php
require_once('minestat.php');

$ms = new MineStat("minecraft.frag.land", 25565);
printf("Minecraft server status of %s on port %s:<br>", $ms->get_address(), $ms->get_port());
if($ms->is_online())
{
  printf("Server is online running version %s with %s out of %s players.<br>", $ms->get_version(), $ms->get_current_players(), $ms->get_max_players());
  printf("Message of the day: %s<br>", $ms->get_motd());
  printf("Latency: %sms<br>", $ms->get_latency());
}
else
{
  printf("Server is offline!<br>");
}
?>
```
