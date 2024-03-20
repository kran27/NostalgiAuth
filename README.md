# NostalgiAuth

A fork of SimpleAuth for NostalgiaCore that prevents people impersonating other accounts by requiring registration and login when connecting.


## Commands


* `/login <password>`
* `/register <password>`
* `/unregister <password>`
* For OPs: `/nostalgiauth <command: help|unregister> [parameters...]`


## Configuration

You can modify the _NostalgiAuth/config.yml_ file on the _plugins_ directory once the plugin has been run for at least one time.

| Configuration | Type | Default | Description |
| :---: | :---: | :---: | :--- |
| allowChat | boolean | false | Allows unauthenticated players to use the chat. They won't be able to use any command. |
| messageInterval | integer | 5 | Timelapse, in seconds, between the login/register message broadcast to unauthenticated players. |
| timeout | integer | 60 | Unauthenticated players will be kicked after this period of time. Set it to 0 to disable. |
| allowRegister | boolean | true | Allows registering and log in through commands. |
| forceSingleSession | boolean | true | New players won't kick an authenticated player if using the same name. |
| minPasswordLength | integer | 6 | Minimum length of the register password. |
| authenticateByLastIP | boolean | false | Enables authentication by last IP. |


## For developers


You can use the _login()_ method in the API to authenticate the player directly.

`boolean NostalgiAuthAPI::login(Player object)`

There are three _handle()_ events that you can use:

* nostalgiauth.login
* nostalgiauth.logout
* nostalgiauth.register

All the events carry the original Player object

More:

`boolean NostalgiAuthAPI::logout(Player object)`

`object NostalgiAuth NostalgiAuthAPI::get()`
